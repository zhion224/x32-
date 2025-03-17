<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WiFi Auto Connect</title>
    <script>
        function generateWiFiQR() {
            var ssid = "audio 2.4G";  // 와이파이 SSID 입력
            var password = "aa112233!";  // 와이파이 비밀번호 입력
            var wifiURL = "WIFI:T:WPA;S:" + ssid + ";P:" + password + ";;";
            
            var qrCodeUrl = "https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=" + encodeURIComponent(wifiURL);
            document.getElementById("wifiQR").src = qrCodeUrl;
        }

        function redirectToLink() {
            setTimeout(function() {
                window.location.href = "http://192.168.10.26:8000/tablet";  // 이동할 링크 입력
            }, 5000);  // 5초 후 이동
        }

        window.onload = function() {
            generateWiFiQR();
            redirectToLink();
        }
    </script>
</head>
<body>
    <h1>WiFi 연결을 위해 QR 코드를 스캔하세요</h1>
    <img id="wifiQR" src="" alt="WiFi QR Code">
    <p>5초 후 자동으로 페이지가 이동합니다...</p>
</body>
</html>
