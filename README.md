<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Fox Reader Scroll Demo</title>

<style>
  body {
    margin: 0;
    font-family: system-ui, sans-serif;
    background: #fff7e6;
  }

  .container {
    max-width: 700px;
    margin: auto;
    padding: 60px 20px 200px;
  }

  /* Fox */
  .fox {
  position: fixed;
  bottom: 20px;
  right: 20px;
  font-size: 64px;
  animation: bob 2s infinite ease-in-out;
  pointer-events: none;
}

  .fox img {
    width: 100%;
  }

  @keyframes bob {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-6px); }
  }

  /* Progress bar */
  .progress {
    position: fixed;
    top: 0;
    left: 0;
    height: 6px;
    background: orange;
    width: 0%;
    z-index: 10;
  }

  article p {
    font-size: 1.1rem;
    line-height: 1.7;
    margin-bottom: 40px;
  }
</style>
</head>

<body>

<div class="progress" id="progress"></div>

<div class="container">
  <article>
    <h1>🦊 Fox Reading Demo</h1>

    <p>Scroll down and watch the fox react while you read.</p>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
    <p>Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
    <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris.</p>
    <p>Duis aute irure dolor in reprehenderit in voluptate velit esse.</p>
    <p>Excepteur sint occaecat cupidatat non proident.</p>
    <p>End of article — the fox is proud of you 🦊✨</p>
  </article>
</div>

<div class="fox" id="fox">
  🦊
</div>

<script>
  const progress = document.getElementById("progress");
  const fox = document.getElementById("fox");

  window.addEventListener("scroll", () => {
    const scrollTop = window.scrollY;
    const docHeight = document.body.scrollHeight - window.innerHeight;
    const percent = (scrollTop / docHeight) * 100;

    progress.style.width = percent + "%";

    // Fox reacts to reading
    fox.style.transform = translateY(${percent / 20}px) rotate(${percent / 25}deg);
  });
</script>

</body>
</html>
