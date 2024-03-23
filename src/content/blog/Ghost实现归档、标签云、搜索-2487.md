---
title: Ghost实现归档、标签云、搜索
date: 2017-07-26 04:52:00.0
updated: 2021-12-22 17:01:20.0
url: /archives/2487
categories: 
- 我的地盘
tags: 
- 随笔
- Ghost
---

<p>前面说过，Ghost本身并不自带类似文章归档、标签云，搜索等（后台不知道会不会改进），虽然官方没有给出，但这也不能阻止民间高手们，通过API就能实现上述这些功能。</p><h4>归档</h4><ul><li>首先得在后台的<code> 实验功能 </code>中启用<code> API </code>，如图:<br /><img src="https://cdn.uu126.cn/image/a/63/912947500d1432b9e4c07155674de.jpg" alt="" title=""></li><li>新建自定义页面：</li></ul><p>1.创建一个静态页面：在ghost后台新建页面，发布为 独立页面 ，标题为Archives，网址可以设置为<code> 域名/archives-post </code></p><p>2.接着创建一个自定义页面模板：该模板是第一步创建的静态页面的模板，创建一个page-url.hbs模板，如果第一步设置的页面网址为<code> 域名/archives-post </code>，那么模板即为<code> page-archives-post.hbs </code>。将该模板上传至主题根目录下即可，此时访问域名/archives-post，即会调用自定义的page-archives-post.hbs这个模板。</p><ul><li>在page-archives.hbs中调用Ghost API即可：</li></ul><pre><code class="lang-php">{{!&lt; default}}
/**
 * 调用ghost API，完成文章归档功能
 * 所需组件：jQuery、moment.js
 * @ldsun.com
 */
jQuery(document).ready(function() {
    //获取所有文章数据，按照发表时间排列
    $.get(ghost.url.api('posts', {
        limit: 'all',
        order: &quot;published_at desc&quot;
    })).done(function(data) {
        var posts = data.posts;
        var count = posts.length;
        for (var i = 0; i &lt; count; i++) {
            //调用comentjs对时间戳进行操作
            //由于ghost默认是CST时区，所以日期会有出入，这里消除时区差,如果不需要，把下面第二行后面8小时改为-00:00!!!
            var time = moment(posts[i].published_at).utcOffset(&quot;-08:00&quot;);
            var year = time.get('y');
            var month = time.get('M')+1;
            var date = time.get('D');
            if( date 0) {
                var pre_month = moment(posts[i - 1].published_at).utcOffset(&quot;-08:00&quot;).get('month')+1;
                //如果当前文章的发表月份与前篇文章发表月份相同，则在该月份ul下插入该文章，这里消除时区差,如果不需要，把下面第二行后面8小时改为-00:00!!!
                if (month == pre_month) {
                    var html = &quot;&quot;+date+&quot;日&quot;+title+&quot;&quot;;
                    $(html).appendTo(&quot;.archives .list-&quot;+year+&quot;-&quot;+month);
                }
                //当月份不同时，插入新的月份
                else{
                    var html = &quot; &quot;+year+&quot;-&quot;+month+&quot;&quot;+date+&quot;日&quot;+title+&quot;&quot;;
                    $(html).appendTo('.archives');
                }
            }else{
                var html = &quot; &quot;+year+&quot;-&quot;+month+&quot;&quot;+date+&quot;日&quot;+title+&quot;&quot;;
                $(html).appendTo('.archives');
            }
        }
    }).fail(function(err) {
        console.log(err);
    });
});
</code></pre><p>相应的CSS代码如下：</p><pre><code class="lang-css">.archives .item {
}
.archives h3 {
    font-size: 17px;
    font-weight: bold;
    margin: 0 0 15px 0;
}
.archives-list {
    list-style: none;
    font-size: 16px;
    line-height: 20px;
    padding-left: 25px;
}
.archives-list li {
    padding: 3px 0;
    overflow: hidden;
}
.archives-list time {
    margin-right: 5px;
    color: #999;
    display: inline-block;
    width: 35px;
    font-family: monospace;
}
.archives-list a {
    text-decoration: none;
}</code></pre><h4>标签云</h4><ul><li>介绍一下<code> tag_cloud </code></li></ul><p>这是中文版中增加的一个 handlebars 助手（helper），根据标签所关联的文章数量进行逆排序，也就是关联文章多的先输出；支持一个 limit 参数，用于限定输出的标签数量：all 表示输出所有标签；数字（例如 10）指定输出个数。调用方式如下：</p><pre><code class="lang-php">//输出所有标签
{{tag_cloud limit=&quot;all&quot;}}
或者
//输出前20个标签（标签按照对应的文章数量逆排序）
{{tag_cloud limit=20}}</code></pre><ul><li>使用方法</li></ul><p>在需要输出“标签云”的地方调用<code> tag_cloud </code>助手即可。我们以 casper 默认主题为例。打开<code> index.hbs </code>文件，在<code>  </code>标签后面添加<code> {{tag_cloud limit=10}} </code>，保存此文件、重启 Ghost、打开首页，看看是否输出了一堆标签。我是直接放在归档里的，具体放哪又或是新增页面就看各自喜好了，相应的css代码如下：</p><pre><code class="lang-css">.tag-cloud {
    padding-left: 25px;
}
.tag-cloud {
    padding-left: 1.725rem;
}
.tag-cloud a:hover {
    background: #eee;
    color: #4A4A4A;
}
.tag-cloud a {
    position: relative;
    display: inline-block;
    padding: .725rem;
    font-style: normal;
    line-height: 1.125rem;
    border-radius: .3rem;
    text-decoration: none;
    font-size: 16px;
    margin-bottom: 3px;
}</code></pre><h4>搜索</h4><p>使用<code> jQuery.gsearch.js </code>插件实现Ghost博客的搜索，gsearch是一款为Ghost量身打造的搜索插件，使Ghost轻松具有搜索功能。效果类似于SwifType，通过Ghost的RSS实现搜索功能，您可以点击右上角搜索图标体验效果。</p><ul><li><a href="https://github.com/itobee/gsearch/archive/master.zip">下载</a>最新版的gsearch，将<code> dist </code>文件夹下的<code> libs </code>和<code> partials </code>文件夹复制到当前主题的根目录下（如果遇到同名文件夹，覆盖即可），并在当前主题的<code> default.hbs </code>文件中添加如下代码：</li></ul><pre><code class="lang-html">
   ……
   ……
   ……
   {{&gt; &quot;gsearch&quot;}}
  </code></pre><ul><li>接下来，我们再通过如下代码调用插件即可使用：</li></ul><pre><code class="lang-python">
$(document).one('opening', '.remodal', function () {
    $('#search').gsearch();
});
  </code></pre><p>这段代码我是直接丢在后台的<code> 插入代码 </code>里<br />注：以上示例使用了<code> remodal </code>弹层插件显示搜索信息，可以用其他插件代替，但是需要注意一点：请勿对同一元素重复调用插件。示例中使用jQuery的<code> .one() </code>方法来委托事件。<br />关于搜索功能等信息，可详见原作者<a href="http://www.tobee.me/gsearch/">博客</a></p><p>实现了这三个功能，暂时可以让我消停一下了，要知道菜鸟要实现这些功能可也是花了好久功夫的，这个过程还是挺享受的，这不现地又得找点可以折腾的东西来……</p>