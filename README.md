<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>MR__BARNAPAUL.R | Portfolio</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; font-family: Arial, sans-serif; }
    body { line-height: 1.6; background: #f9f9f9; color: #333; }

    /* Navbar */
    header { background: #333; color: #fff; padding: 1rem; }
    .navbar { display: flex; justify-content: space-between; align-items: center; }
    .navbar ul { list-style: none; display: flex; }
    .navbar ul li { margin: 0 10px; }
    .navbar ul li a { color: white; text-decoration: none; padding: 0.5rem; }
    .navbar ul li a:hover { background: #555; border-radius: 5px; }

    /* Sections */
    section { padding: 40px 20px; }
    h2 { margin-bottom: 20px; text-align: center; }

    /* Hero */
    .hero { background: #444; color: white; text-align: center; padding: 80px 20px; }
    .hero h1 span { color: #ffd700; }
    .btn { display: inline-block; background: #ffd700; color: #333; padding: 10px 20px; border-radius: 5px; text-decoration: none; margin-top: 15px; }

    /* About */
    .about-content { display: flex; flex-wrap: wrap; align-items: center; justify-content: center; gap: 20px; }
    .about-content img { width: 200px; border-radius: 10px; }
    .about-content p { max-width: 500px; }

    /* Projects */
    .project-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 20px; }
    .project-card { background: white; padding: 15px; border-radius: 8px; box-shadow: 0 0 5px rgba(0,0,0,0.1); text-align: center; }

    /* Quiz */
    .quiz-container { background: white; padding: 20px; border-radius: 10px; max-width: 500px; margin: auto; box-shadow: 0 0 10px rgba(0,0,0,0.2); }
    ul { list-style: none; }
    ul li { margin: 10px 0; }
    .quiz-container button { background: #333; color: white; padding: 10px; border: none; border-radius: 5px; cursor: pointer; }
    .quiz-container button:hover { background: #555; }

    /* Blog */
    .post { background: white; padding: 15px; margin-bottom: 20px; border-radius: 8px; box-shadow: 0 0 5px rgba(0,0,0,0.1); }

    /* Contact */
    form { max-width: 400px; margin: auto; display: flex; flex-direction: column; gap: 10px; }
    form input, form textarea { padding: 10px; border-radius: 5px; border: 1px solid #ccc; }
    form button { background: #333; color: white; padding: 10px; border: none; border-radius: 5px; cursor: pointer; }
    form button:hover { background: #555; }

    /* Footer */
    footer { text-align: center; background: #333; color: white; padding: 1rem; margin-top: 1rem; }

  </style>
</head>
<body>

  <!-- Navbar -->
  <header>
    <nav class="navbar">
      <div class="logo">MyPortfolio</div>
      <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <!-- Hero -->
  <section id="home" class="hero">
    <h1>Hello, I'm <span>MR__BARNAPAUL.R</span></h1>
    <p>I am the veti officer</p>
    <a href="#projects" class="btn">View My Work</a>
  </section>

  <!-- About -->
  <section id="about">
    <h2>About Me</h2>
    <div class="about-content">
      <img src="DSC_8330 copy.jpg" alt="Profile Photo">
      <p>I am a student enthusiastic about technology and design. I love building interactive,
        user-friendly web applications and exploring new tools in the tech world.</p>
    </div>
  </section>

  <!-- Projects -->
  <section id="projects">
    <h2>My Projects</h2>
    <div class="project-grid">

      <!-- Responsive Layout -->
      <div class="project-card">
        <h3>Responsive Layout Demo</h3>
        <p>This section shows a simple two-column responsive design.</p>
      </div>

      <!-- Quiz App -->
      <div class="project-card">
        <h3>Quiz App</h3>
        <div class="quiz-container" id="quiz">
          <h2 id="question">Question text</h2>
          <ul>
            <li><label><input type="radio" name="answer" class="answer" id="a"> <span id="a_text"></span></label></li>
            <li><label><input type="radio" name="answer" class="answer" id="b"> <span id="b_text"></span></label></li>
            <li><label><input type="radio" name="answer" class="answer" id="c"> <span id="c_text"></span></label></li>
            <li><label><input type="radio" name="answer" class="answer" id="d"> <span id="d_text"></span></label></li>
          </ul>
          <button id="submit">Submit</button>
          <div class="result" id="result"></div>
        </div>
      </div>

      <!-- Blog -->
      <div class="project-card">
        <h3>My Blog</h3>
        <div id="postsContainer"></div>
      </div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact">
    <h2>Contact Me</h2>
    <form id="contact-form">
      <input type="text" name="user_name" placeholder="Your Name" required>
      <input type="email" name="user_email" placeholder="Your Email" required>
      <textarea name="message" placeholder="Your Message" required></textarea>
      <button type="submit">Send</button>
    </form>
    <p id="form-status"></p>
  </section>

  <!-- Footer -->
  <footer>
    <p>&copy; 2025 MR__BARNAPAUL.R | All Rights Reserved</p>
  </footer>

  <!-- Scripts -->
  <script>
    // QUIZ APP
    const quizData = [
      { question: "What does HTML stand for?", a: "Hyper Text Markup Language", b: "High Text Markup Language", c: "Hyperlinks and Text Markup Language", d: "Home Tool Markup Language", correct: "a" },
      { question: "Which language is used for styling web pages?", a: "HTML", b: "JQuery", c: "CSS", d: "XML", correct: "c" },
      { question: "Which is not a JavaScript Framework?", a: "React", b: "Angular", c: "Vue", d: "Django", correct: "d" },
      { question: "Which is used for database?", a: "PHP", b: "MySQL", c: "HTML", d: "CSS", correct: "b" }
    ];
    const quiz = document.getElementById("quiz");
    const answerEls = document.querySelectorAll(".answer");
    const questionEl = document.getElementById("question");
    const a_text = document.getElementById("a_text");
    const b_text = document.getElementById("b_text");
    const c_text = document.getElementById("c_text");
    const d_text = document.getElementById("d_text");
    const submitBtn = document.getElementById("submit");
    let currentQuiz = 0, score = 0;
    loadQuiz();
    function loadQuiz() {
      deselectAnswers();
      const currentQuizData = quizData[currentQuiz];
      questionEl.innerText = currentQuizData.question;
      a_text.innerText = currentQuizData.a;
      b_text.innerText = currentQuizData.b;
      c_text.innerText = currentQuizData.c;
      d_text.innerText = currentQuizData.d;
    }
    function deselectAnswers() { answerEls.forEach(el => el.checked = false); }
    function getSelected() { let answer; answerEls.forEach(el => { if (el.checked) answer = el.id; }); return answer; }
    submitBtn.addEventListener("click", () => {
      const answer = getSelected();
      if (answer) {
        if (answer === quizData[currentQuiz].correct) score++;
        currentQuiz++;
        if (currentQuiz < quizData.length) loadQuiz();
        else quiz.innerHTML = `<h2>You answered correctly ${score}/${quizData.length} questions.</h2><button onclick="location.reload()">Restart</button>`;
      }
    });

    // BLOG
    function loadPosts() {
      const postsContainer = document.getElementById("postsContainer");
      const posts = JSON.parse(localStorage.getItem("blogPosts")) || [
        { title: "Welcome Post", content: "This is my first blog entry!", date: new Date() }
      ];
      postsContainer.innerHTML = "";
      posts.reverse().forEach(post => {
        const postEl = document.createElement("div");
        postEl.classList.add("post");
        postEl.innerHTML = `<h4>${post.title}</h4><small>${new Date(post.date).toLocaleString()}</small><p>${post.content}</p>`;
        postsContainer.appendChild(postEl);
      });
    }
    loadPosts();

    // CONTACT FORM (EmailJS)
    (function(){ emailjs.init("YOUR_PUBLIC_KEY"); })();
    document.getElementById("contact-form").addEventListener("submit", function(e){
      e.preventDefault();
      emailjs.sendForm("YOUR_SERVICE_ID", "YOUR_TEMPLATE_ID", this)
        .then(() => document.getElementById("form-status").innerText = "Message sent!")
        .catch(() => document.getElementById("form-status").innerText = "Failed to send.");
    });
  </script>
  <script src="https://cdn.emailjs.com/dist/email.min.js"></script>
</body>
</html>
