# EDUMATE
ITS A APP FOR COLLEGE FRESHERS FOR MAKE EVERYTHING EASY
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Simple Citation Generator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f6f9;
      color: #333;
      margin: 0;
      padding: 0;
    }
    .container {
      max-width: 600px;
      margin: 50px auto;
      background: #fff;
      padding: 25px;
      border-radius: 12px;
      box-shadow: 0 6px 12px rgba(0,0,0,0.1);
    }
    h1 {
      text-align: center;
      margin-bottom: 20px;
      color: #2c3e50;
    }
    label {
      display: block;
      margin: 10px 0 5px;
      font-weight: bold;
    }
    input, select {
      width: 100%;
      padding: 10px;
      margin-bottom: 15px;
      border-radius: 8px;
      border: 1px solid #ccc;
      font-size: 14px;
    }
    button {
      width: 100%;
      padding: 12px;
      background: #007bff;
      color: white;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      cursor: pointer;
    }
    button:hover {
      background: #0056b3;
    }
    .output {
      margin-top: 20px;
      background: #f1f1f1;
      padding: 15px;
      border-radius: 8px;
      font-size: 15px;
      border: 1px solid #ccc;
      word-wrap: break-word;
    }
    .copy-btn {
      margin-top: 10px;
      background: #28a745;
    }
    .copy-btn:hover {
      background: #1e7e34;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>📚 Simple Citation Generator</h1>
    
    <label for="type">Source Type</label>
    <select id="type">
      <option value="book">Book</option>
      <option value="website">Website</option>
      <option value="article">Article</option>
    </select>

    <label for="author">Author</label>
    <input type="text" id="author" placeholder="e.g., Smith, J.">

    <label for="title">Title</label>
    <input type="text" id="title" placeholder="Title of source">

    <label for="year">Year</label>
    <input type="text" id="year" placeholder="2025">

    <div id="extraFields"></div>

    <button onclick="generateCitation()">Generate Citation</button>

    <div id="output" class="output" style="display:none;"></div>
    <button id="copyBtn" class="copy-btn" style="display:none;" onclick="copyCitation()">Copy to Clipboard</button>
  </div>

  <script>
    const typeSelect = document.getElementById("type");
    const extraFields = document.getElementById("extraFields");
    const output = document.getElementById("output");
    const copyBtn = document.getElementById("copyBtn");

    function renderExtraFields() {
      extraFields.innerHTML = "";
      if (typeSelect.value === "book") {
        extraFields.innerHTML = `
          <label for="publisher">Publisher</label>
          <input type="text" id="publisher" placeholder="Oxford University Press">
        `;
      } else if (typeSelect.value === "website") {
        extraFields.innerHTML = `
          <label for="url">URL</label>
          <input type="text" id="url" placeholder="https://example.com">
        `;
      } else if (typeSelect.value === "article") {
        extraFields.innerHTML = `
          <label for="journal">Journal / Publisher</label>
          <input type="text" id="journal" placeholder="Science Journal">
        `;
      }
    }

    function generateCitation() {
      const author = document.getElementById("author").value.trim();
      const title = document.getElementById("title").value.trim();
      const year = document.getElementById("year").value.trim();
      let citation = "";

      if (typeSelect.value === "book") {
        const publisher = document.getElementById("publisher")?.value.trim();
        citation = `${author}. (${year}). <i>${title}</i>. ${publisher}.`;
      } else if (typeSelect.value === "website") {
        const url = document.getElementById("url")?.value.trim();
        citation = `${author}. (${year}). ${title}. Retrieved from ${url}`;
      } else if (typeSelect.value === "article") {
        const journal = document.getElementById("journal")?.value.trim();
        citation = `${author}. (${year}). ${title}. <i>${journal}</i>.`;
      }

      output.innerHTML = citation;
      output.style.display = "block";
      copyBtn.style.display = "block";
    }

    function copyCitation() {
      navigator.clipboard.writeText(output.innerText).then(() => {
        alert("Citation copied!");
      });
    }

    typeSelect.addEventListener("change", renderExtraFields);
    renderExtraFields();
  </script>
</body>
</html>

<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Simple Citation Generator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f6f9;
      color: #333;
      margin: 0;
      padding: 0;
    }
    .container {
      max-width: 600px;
      margin: 50px auto;
      background: #fff;
      padding: 25px;
      border-radius: 12px;
      box-shadow: 0 6px 12px rgba(0,0,0,0.1);
    }
    h1 {
      text-align: center;
      margin-bottom: 20px;
      color: #2c3e50;
    }
    label {
      display: block;
      margin: 10px 0 5px;
      font-weight: bold;
    }
    input, select {
      width: 100%;
      padding: 10px;
      margin-bottom: 15px;
      border-radius: 8px;
      border: 1px solid #ccc;
      font-size: 14px;
    }
    button {
      width: 100%;
      padding: 12px;
      background: #007bff;
      color: white;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      cursor: pointer;
    }
    button:hover {
      background: #0056b3;
    }
    .output {
      margin-top: 20px;
      background: #f1f1f1;
      padding: 15px;
      border-radius: 8px;
      font-size: 15px;
      border: 1px solid #ccc;
      word-wrap: break-word;
    }
    .copy-btn {
      margin-top: 10px;
      background: #28a745;
    }
    .copy-btn:hover {
      background: #1e7e34;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>📚 Simple Citation Generator</h1>
    
    <label for="type">Source Type</label>
    <select id="type">
      <option value="book">Book</option>
      <option value="website">Website</option>
      <option value="article">Article</option>
    </select>

    <label for="author">Author</label>
    <input type="text" id="author" placeholder="e.g., Smith, J.">

    <label for="title">Title</label>
    <input type="text" id="title" placeholder="Title of source">

    <label for="year">Year</label>
    <input type="text" id="year" placeholder="2025">

    <div id="extraFields"></div>

    <button onclick="generateCitation()">Generate Citation</button>

    <div id="output" class="output" style="display:none;"></div>
    <button id="copyBtn" class="copy-btn" style="display:none;" onclick="copyCitation()">Copy to Clipboard</button>
  </div>

  <script>
    const typeSelect = document.getElementById("type");
    const extraFields = document.getElementById("extraFields");
    const output = document.getElementById("output");
    const copyBtn = document.getElementById("copyBtn");

    function renderExtraFields() {
      extraFields.innerHTML = "";
      if (typeSelect.value === "book") {
        extraFields.innerHTML = `
          <label for="publisher">Publisher</label>
          <input type="text" id="publisher" placeholder="Oxford University Press">
        `;
      } else if (typeSelect.value === "website") {
        extraFields.innerHTML = `
          <label for="url">URL</label>
          <input type="text" id="url" placeholder="https://example.com">
        `;
      } else if (typeSelect.value === "article") {
        extraFields.innerHTML = `
          <label for="journal">Journal / Publisher</label>
          <input type="text" id="journal" placeholder="Science Journal">
        `;
      }
    }

    function generateCitation() {
      const author = document.getElementById("author").value.trim();
      const title = document.getElementById("title").value.trim();
      const year = document.getElementById("year").value.trim();
      let citation = "";

      if (typeSelect.value === "book") {
        const publisher = document.getElementById("publisher")?.value.trim();
        citation = `${author}. (${year}). <i>${title}</i>. ${publisher}.`;
      } else if (typeSelect.value === "website") {
        const url = document.getElementById("url")?.value.trim();
        citation = `${author}. (${year}). ${title}. Retrieved from ${url}`;
      } else if (typeSelect.value === "article") {
        const journal = document.getElementById("journal")?.value.trim();
        citation = `${author}. (${year}). ${title}. <i>${journal}</i>.`;
      }

      output.innerHTML = citation;
      output.style.display = "block";
      copyBtn.style.display = "block";
    }

    function copyCitation() {
      navigator.clipboard.writeText(output.innerText).then(() => {
        alert("Citation copied!");
      });
    }

    typeSelect.addEventListener("change", renderExtraFields);
    renderExtraFields();
  </script>
</body>
</html>
  <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Simple Website</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        header {
            background-color: #4CAF50;
            color: white;
            padding: 20px 0;
            text-align: center;
        }
        nav {
            background-color: #333;
        }
        nav ul {
            margin: 0;
            padding: 0;
            display: flex;
            list-style: none;
            justify-content: center;
        }
        nav ul li {
            margin: 0 15px;
        }
        nav ul li a {
            color: white;
            text-decoration: none;
            padding: 14px 20px;
            display: block;
        }
        nav ul li a:hover {
            background-color: #575757;
            border-radius: 4px;
        }
        main {
            padding: 20px;
            text-align: center;
        }
        footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 10px 0;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
        .button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            margin-top: 15px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>

    <header>
        <h1>Welcome to My Website</h1>
    </header>

    <nav>
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <main>
        <section id="home">
            <h2>Home Page</h2>
            <p>This is a simple fully working website you can open in VS Code.</p>
            <button class="button">Click Me</button>
        </section>

        <section id="about">
            <h2>About</h2>
            <p>This website is created as a simple example to get you started.</p>
        </section>

        <section id="services">
            <h2>Services</h2>
            <p>We provide amazing services to our clients.</p>
        </section>

        <section id="contact">
            <h2>Contact</h2>
            <p>Email: example@example.com</p>
            <p>Phone: +91 1234567890</p>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 My Simple Website. All rights reserved.</p>
    </footer>

</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Simple Website</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        header {
            background-color: #4CAF50;
            color: white;
            padding: 20px 0;
            text-align: center;
        }
        nav {
            background-color: #333;
        }
        nav ul {
            margin: 0;
            padding: 0;
            display: flex;
            list-style: none;
            justify-content: center;
        }
        nav ul li {
            margin: 0 15px;
        }
        nav ul li a {
            color: white;
            text-decoration: none;
            padding: 14px 20px;
            display: block;
        }
        nav ul li a:hover {
            background-color: #575757;
            border-radius: 4px;
        }
        main {
            padding: 20px;
            text-align: center;
        }
        footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 10px 0;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
        .button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            margin-top: 15px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>

    <header>
        <h1>Welcome to My Website</h1>
    </header>

    <nav>
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <main>
        <section id="home">
            <h2>Home Page</h2>
            <p>This is a simple fully working website you can open in VS Code.</p>
            <button class="button">Click Me</button>
        </section>

        <section id="about">
            <h2>About</h2>
            <p>This website is created as a simple example to get you started.</p>
        </section>

        <section id="services">
            <h2>Services</h2>
            <p>We provide amazing services to our clients.</p>
        </section>

        <section id="contact">
            <h2>Contact</h2>
            <p>Email: example@example.com</p>
            <p>Phone: +91 1234567890</p>
      
  
    </style>
</head>
<body>

    <!-- Header -->
    <header>
        <h1>Edumate</h1>
        <p>Your Educational Companion</p>
    </header>

    <!-- Navigation -->
    <nav>
        <ul>
            <li><a href="#home"><i class="fas fa-home"></i>Home</a></li>
            <li><a href="#about"><i class="fas fa-user"></i>About</a></li>
            <li><a href="#features"><i class="fas fa-cogs"></i>Features</a></li>
            <li><a href="#contact"><i class="fas fa-envelope"></i>Contact</a></li>
        </ul>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <h2>Welcome to Edumate</h2>
        <p>Edumate helps students with citation generation, notes management, and more. Simple, fast, and professional.</p>
        <button class="button">Get Started</button>
    </section>

    <!-- About Section -->
    <section id="about">
        <h2>About Edumate</h2>
        <p>Edumate is designed to simplify educational tasks for students. With an easy-to-use interface and professional design, it’s your perfect study companion.</p>
    </section>

    <!-- Features Section -->
    <section id="features">
        <h2>Features</h2>
        <div class="features">
            <div class="feature">
                <i class="fas fa-book"></i>
                <h3>Citation Generator</h3>
                <p>Generate citations in APA, MLA, Chicago, and more within seconds.</p>
            </div>
            <div class="feature">
                <i class="fas fa-file-alt"></i>
                <h3>Notes Management</h3>
                <p>Organize your study notes efficiently for quick access and review.</p>
            </div>
            <div class="feature">
                <i class="fas fa-lightbulb"></i>
                <h3>Smart Tips</h3>
                <p>Receive study tips and resources curated to improve learning.</p>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contact">
        <h2>Contact Us</h2>
        <form>
            <input type="text" placeholder="Your Name" required>
            <input type="email" placeholder="Your Email" required>
            <textarea rows="5" placeholder="Your Message" required></textarea>
            <button type="submit">Send Message</button>
        </form>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2025 Edumate. All rights reserved.</p>
        <div class="social">
            <i class="fab fa-facebook"></i>
            <i class="fab fa-twitter"></i>
            <i class="fab fa-instagram"></i>
            <i class="fab fa-linkedin"></i>
        </div>
    </footer>

</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Edumate - Your Educational Companion</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <!-- Font Awesome for icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Roboto', sans-serif; }
        body { background-color: #f0f2f5; line-height: 1.6; }

        /* Fixed Header */
        header {
            position: fixed;
            width: 100%;
            top: 0;
            left: 0;
            background: linear-gradient(90deg, #4CAF50, #45a049);
            color: white;
            padding: 20px 0;
            text-align: center;
            z-index: 1000;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        header h1 { font-size: 2.5em; }

        /* Navigation */
        nav {
            position: fixed;
            width: 100%;
            top: 80px; /* below header */
            left: 0;
            background-color: #333;
            z-index: 999;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        nav ul { list-style: none; display: flex; justify-content: center; flex-wrap: wrap; }
        nav ul li { margin: 0 15px; }
        nav ul li a {

