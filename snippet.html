<!-- ═══ PWA (DataForge PWA 빌더) ═══ -->
<link rel="manifest" href="./manifest.json">
<meta name="theme-color" content="#2563eb">
<link rel="icon" type="image/png" sizes="32x32" href="./icons/favicon-32.png">
<!-- iOS 홈 화면 추가 대응 -->
<link rel="apple-touch-icon" href="./icons/apple-touch-icon.png">
<meta name="mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="default">
<meta name="apple-mobile-web-app-title" content="내앱">
<!-- 서비스 워커 등록 -->
<script>
if ('serviceWorker' in navigator) {
  window.addEventListener('load', function () {
    navigator.serviceWorker.register('./sw.js');
  });
}
</script>
<!-- 고해상도 화면 보정: pdf.js 렌더링에 devicePixelRatio 자동 적용 -->
<script>
(function () {
  var dpr = Math.min(window.devicePixelRatio || 1, 3);
  if (dpr <= 1) return;
  function patchPage(page) {
    if (page.__dfDprPatched) return page;
    page.__dfDprPatched = true;
    var origRender = page.render.bind(page);
    page.render = function (ctx) {
      try {
        // 앱이 transform을 직접 지정했다면(자체 DPR 처리) 건드리지 않음
        if (ctx && ctx.canvasContext && ctx.viewport && !ctx.transform) {
          var canvas = ctx.canvasContext.canvas;
          var w = ctx.viewport.width, h = ctx.viewport.height;
          canvas.width = Math.floor(w * dpr);
          canvas.height = Math.floor(h * dpr);
          canvas.style.width = Math.floor(w) + 'px';
          canvas.style.height = Math.floor(h) + 'px';
          ctx.transform = [dpr, 0, 0, dpr, 0, 0];
        }
      } catch (err) {}
      return origRender(ctx);
    };
    return page;
  }
  function patchDoc(doc) {
    if (doc.__dfDprPatched) return doc;
    doc.__dfDprPatched = true;
    var origGetPage = doc.getPage.bind(doc);
    doc.getPage = function (n) { return origGetPage(n).then(patchPage); };
    return doc;
  }
  function patchLib(lib) {
    if (!lib || lib.__dfDprPatched || typeof lib.getDocument !== 'function') return;
    lib.__dfDprPatched = true;
    var origGetDocument = lib.getDocument;
    lib.getDocument = function () {
      var task = origGetDocument.apply(lib, arguments);
      var patched = task.promise.then(patchDoc);
      try {
        Object.defineProperty(task, 'promise', { get: function () { return patched; } });
      } catch (err) {}
      return task;
    };
  }
  // pdf.js가 나중에 로드되는 경우까지 대기 (최대 10초, 없으면 아무 동작 안 함)
  if (window.pdfjsLib) { patchLib(window.pdfjsLib); }
  else {
    var n = 0, t = setInterval(function () {
      if (window.pdfjsLib) { patchLib(window.pdfjsLib); clearInterval(t); }
      else if (++n > 100) { clearInterval(t); }
    }, 100);
  }
})();
</script>
<!-- ═══════════════════════════════ -->