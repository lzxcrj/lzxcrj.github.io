<!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>访问摄像头</title>
   </head>
   <body>
       <h1>访问摄像头</h1>
       <video id="webcam" autoplay playsinline></video>

       <script>
           const video = document.getElementById('webcam');
           async function accessCamera() {
               try {
                   const stream = await navigator.mediaDevices.getUserMedia({ video: true });
                   video.srcObject = stream;
               } catch (error) {
                   console.error('无法访问摄像头:', error);
               }
           }
           accessCamera();
       </script>
   </body>
   </html>
