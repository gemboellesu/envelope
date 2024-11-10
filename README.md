<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>wkwkwk</title>
  <!-- Bootstrap CSS -->
  <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet">
  <style>
    /* Memusatkan container */
    .container {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
    }

    /* Styling dasar amplop */
    .envelope {
      position: relative;
      width: 600px;
      height: 400px;
      background-color: #f8f9fa;
      border: 2px solid #FFC0CB;
      border-radius: 5px;
      overflow: hidden;
      transition: transform 1s ease;
    }

    /* Tutup amplop */
    .envelope .flap {
      position: absolute;
      top: 0;
      width: 100%;
      height: 50%;
      background-color: #FFC0CB;
      clip-path: polygon(0 0, 100% 0, 50% 100%);
      transform-origin: top;
      transition: transform 1s ease;
    }

    /* Pita penutup */
    .ribbon {
      position: absolute;
      top: 50%;
      left: 0;
      width: 100%;
      height: 10px;
      background-color: #FFC0CB;
      transition: opacity 0.5s ease;
      z-index: 1;
    }

    .ribbon::before, .ribbon::after {
      content: "";
      position: absolute;
      top: -10px;
      width: 10px;
      height: 30px;
      background-color: pink;
    }

    .ribbon::before {
      left: 30%;
    }

    .ribbon::after {
      right: 30%;
    }

    /* Isi amplop (surat cinta) */
    .envelope .content {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      height: 100%;
      opacity: 0;
      transition: opacity 0.5s ease;
      color: #343a40;
    }

    .envelope .love-letter {
      position: absolute;
      bottom: 20px;
      width: 90%;
      padding: 15px;
      background-color: #ffebec;
      border-radius: 5px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      transform: translateY(100px);
      opacity: 0;
      transition: transform 0.5s ease, opacity 0.5s ease;
      text-align: center;
      z-index: 0;
    }

    /* Animasi amplop saat dibuka */
    .envelope.open .flap {
      transform: rotateX(-180deg);
    }

    .envelope.open .content {
      opacity: 1;
    }

    .envelope.open .love-letter {
      opacity: 1;
      transform: translateY(-50px);
    }

    .envelope.open .ribbon {
      opacity: 0; /* Menghilangkan pita saat amplop dibuka */
    }

    /* Button styling */
    .btn-open {
      margin-top: 20px;
    }
  </style>
</head>
<body>

  <div class="container">
    <h1 class="my-4">Only the two of us know</h1>
    <!-- Amplop -->
    <div class="envelope" id="envelope">
      <div class="flap"></div>
      <div class="ribbon"></div> <!-- Penutup pita -->
      <div class="content">
        <div class="love-letter">
          <h5></h5>
          <p>Hey, Thank you yaa udah mau ngobrol sama gua dan thank you juga udah mau ladenin chat freak gua, and I'm really sorry kalo misalkan gua buat lu ilfeel, terlalu melakukan hal berlebihan ke lu. gua cuman mau bilang itu aja ke lu, thank youu.
            <p> ⚡︎Si Teknik⚡︎
          </p>
        </div>
      </div>
    </div>
    <!-- Tombol untuk membuka amplop -->
    <button class="btn btn-primary btn-open" onclick="openEnvelope()">Open</button>
  </div>

  <script>
    function openEnvelope() {
      document.getElementById("envelope").classList.toggle("open");
    }
  </script>
</body>
</html>
