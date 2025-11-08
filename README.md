<html>
<head>
<meta charset="UTF-8">
<title>Security Warning</title>
<style>
  body { font-family: Arial, sans-serif; background: #fff0f0; margin: 20px; }
  h2 { color: red; animation: blink 1s infinite; }
  @keyframes blink { 0%, 50%, 100% { opacity: 1; } 25%, 75% { opacity: 0; } }
  .iframe-box { position: relative; width: 100%; max-width: 1024px; height: 600px; border: 3px solid red; box-shadow: 0 0 10px red; }
  iframe { width: 100%; height: 100%; border: none; }
  .overlay {
    position: absolute; top: 100px; left: 120px;
    width: 300px; height: 150px;
    background: rgba(255, 0, 0, 0.5);
    z-index: 2; pointer-events: none;
    font-weight: bold; text-align: center;
    padding-top: 55px; color: white; font-size: 18px;
    border: 2px dashed white;
    animation: blink 1s infinite;
  }
</style>
</head>
<body onload="playAlert()">
<audio id="alertSound" autoplay>
  <source src="https://actions.google.com/sounds/v1/alarms/alarm_clock.ogg" type="audio/ogg">
</audio>
<h2>  URGENT: Your Website Is Being Clickjacked Right Now</h2>
<p>Your website is currently embedded inside a malicious third-party site <strong>without your consent</strong>.<br>
This is not a simulation. A live attack is underway. Hidden overlays may be intercepting user actions, stealing data, or redirecting traffic.<br>
<strong>Immediate action is required</strong> to protect your users and your reputation.</p>
<div class="iframe-box">
  <div class="overlay">  Malicious Overlay Active</div>
  <iframe src="https://www.szabosarcades.com
"></iframe>
</div>
<p><strong>Risk:</strong> Your website is exposed to hijacking, phishing, and unauthorized manipulation.<br>
<strong>Recommended Action:</strong> Immediately implement security headers like <code>X-Frame-Options</code> or <code>Content-Security-Policy: frame-ancestors</code> to prevent unauthorized embedding.</p>
<script>
function playAlert() {
  var sound = document.getElementById("alertSound");
  sound.play().catch(function(e) {
    console.log("Autoplay blocked, sound will play on first click.");
  });
}
</script>
</body>
</html>
