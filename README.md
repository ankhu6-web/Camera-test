# Camera-test
<!DOCTYPE html>
<html>
<body>
    <h2>Camera Access Request</h2>
    <video id="video" width="640" height="480" autoplay></video>

    <script>
        // This is the command that triggers the browser's "Allow" pop-up
        async function startCamera() {
            try {
                const stream = await navigator.mediaDevices.getUserMedia({ video: true });
                const videoElement = document.getElementById('video');
                videoElement.srcObject = stream;
            } catch (err) {
                console.error("Error accessing the camera: ", err);
                alert("Camera access was denied or is not available.");
            }
        }

        // Start the request as soon as the page loads
        window.onload = startCamera;
    </script>
</body>
</html>
