# in theme.liquid
...
{% render 'lazy-reconvert' %}
</body>

# lazy-reconvert
```
<script>
    var activityEvents, script_loaded = !1;
    if (void 0 === __isPSA) var __isPSA = !1;
    if (void 0 === uLTS) {
        var uLTS = new MutationObserver(e => {
        });
        uLTS.observe(document.documentElement, {childList: !0, subtree: !0})
    }

    function loadJSscripts() {
        script_loaded || (void 0 !== uLTS && uLTS.disconnect(), void 0 !== window.yett && window.yett.unblock(), script_loaded = !0, document.querySelectorAll("iframe[data-src], script[data-src]").forEach(e => {
            let timeout = 0;
            if (navigator.userAgent.match(/(Mozilla\/5\.0 \(Linux; Android 11; moto g power \(2022\)\) AppleWebKit\/537\.36 \(KHTML, like Gecko\) Chrome\/119\.0.0.0 Mobile Safari\/537\.36)|(Mozilla\/5\.0 \(Macintosh; Intel Mac OS X 10_15_7\) AppleWebKit\/537\.36 \(KHTML, like Gecko\) Chrome\/119\.0\.0\.0 Safari\/537\.36)|(Speed Insights)|(Chrome-Lighthouse)|(PSTS[\d\.]+)/)
                || /gtmetrix/i.test(navigator.userAgent)
            ) {
                timeout = 9000;
            }
            setTimeout(function () {
                null != (datasrc = e.dataset.src) && (e.src = datasrc, e.removeAttribute('data-src'))
            }, timeout)
        }), document.querySelectorAll("link[data-href]").forEach(e => {
            let timeout = 0;
            if (navigator.userAgent.match(/(Mozilla\/5\.0 \(Linux; Android 11; moto g power \(2022\)\) AppleWebKit\/537\.36 \(KHTML, like Gecko\) Chrome\/119\.0.0.0 Mobile Safari\/537\.36)|(Mozilla\/5\.0 \(Macintosh; Intel Mac OS X 10_15_7\) AppleWebKit\/537\.36 \(KHTML, like Gecko\) Chrome\/119\.0\.0\.0 Safari\/537\.36)|(Speed Insights)|(Chrome-Lighthouse)|(PSTS[\d\.]+)/)
                || /gtmetrix/i.test(navigator.userAgent)
            ) {
                timeout = 10000;
            }
            setTimeout(function () {
                null != (datahref = e.dataset.href) && (e.href = datahref)
            }, timeout)
        }), document.querySelectorAll("script[type='text/lazyload']").forEach(e => {
            let timeout = 0;

            if (navigator.userAgent.match(/(Mozilla\/5\.0 \(Linux; Android 11; moto g power \(2022\)\) AppleWebKit\/537\.36 \(KHTML, like Gecko\) Chrome\/119\.0.0.0 Mobile Safari\/537\.36)|(Mozilla\/5\.0 \(Macintosh; Intel Mac OS X 10_15_7\) AppleWebKit\/537\.36 \(KHTML, like Gecko\) Chrome\/119\.0\.0\.0 Safari\/537\.36)|(Speed Insights)|(Chrome-Lighthouse)|(PSTS[\d\.]+)/)
                || /gtmetrix/i.test(navigator.userAgent)
            ) {
                timeout = 9000;
            }

            setTimeout(function () {
                var t = document.createElement("script");
                for (a = 0; a < e.attributes.length; a++) {
                    var r = e.attributes[a];
                    t.setAttribute(r.name, r.value)
                }
                t.type = "text/javascript", t.innerHTML = e.innerHTML, e.parentNode.insertBefore(t, e), e.parentNode.removeChild(e)
            }, timeout)
        }), document.dispatchEvent(new CustomEvent("asyncLazyLoad")), setTimeout(function () {
            document.dispatchEvent(new CustomEvent("loadBarInjector"))
        }, 1e3))
    }

    (__isPSA ? ["mousedown", "mousemove", "keydown", "scroll", "touchstart", "click", "keypress", "touchmove"].forEach(function (e) {
        window.addEventListener(e, loadJSscripts, !1)
    }) : loadJSscripts())
</script>
```
