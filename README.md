
`portfolio.html`
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>My Portfolio - Cool & Modern</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap');
    /* Reset */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      scroll-behavior: smooth;
    }

    body {
      font-family: 'Poppins', sans-serif;
      background: #121212;
      color: #f0f0f0;
      line-height: 1.6;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    header {
      background: #1f1f1f;
      padding: 1.2rem 2rem;
      position: fixed;
      width: 100%;
      top: 0;
      z-index: 999;
      box-shadow: 0 2px 8px rgb(0 0 0 / 0.5);
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    header .logo {
      font-weight: 700;
      font-size: 1.5rem;
      color: #6c63ff;
      letter-spacing: 2px;
    }

    nav {
      display: flex;
      gap: 1.5rem;
    }

    nav a {
      font-weight: 500;
      padding: 0.3rem 0.6rem;
      border-radius: 5px;
      transition: background-color 0.3s, color 0.3s;
      color: #ddd;
    }

    nav a:hover,
    nav a.active {
      background-color: #6c63ff;
      color: white;
    }

    main {
      margin-top: 80px;
      width: 90%;
      max-width: 900px;
      margin-left: auto;
      margin-right: auto;
      padding-bottom: 3rem;
    }

    section {
      margin-bottom: 4rem;
      scroll-margin-top: 90px;
    }

    /* Hero */
    #hero {
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
      padding: 4rem 1rem 6rem;
    }

    #hero img {
      border-radius: 50%;
      width: 160px;
      height: 160px;
      object-fit: cover;
      border: 5px solid #6c63ff;
      box-shadow: 0 0 15px #6c63ffa8;
      margin-bottom: 1.5rem;
      transition: transform 0.4s ease;
    }

    #hero img:hover {
      transform: scale(1.05) rotate(5deg);
    }

    #hero h1 {
      font-weight: 700;
      font-size: 2.7rem;
      color: #6c63ff;
      margin-bottom: 0.5rem;
    }

    #hero p {
      font-weight: 300;
      font-size: 1.2rem;
      max-width: 400px;
      color: #ddd;
    }

    /* About */
    #about h2,
    #skills h2,
    #projects h2,
    #contact h2 {
      font-weight: 700;
      font-size: 2rem;
      margin-bottom: 1rem;
      color: #6c63ff;
      border-bottom: 3px solid #6c63ff;
      display: inline-block;
      padding-bottom: 0.3rem;
    }

    #about p {
      font-size: 1.1rem;
      color: #ccc;
      line-height: 1.8;
    }

    /* Skills */
    #skills .skill {
      margin-bottom: 1rem;
    }

    #skills .skill-name {
      font-weight: 600;
      margin-bottom: 0.3rem;
    }

    #skills .skill-bar {
      background: #333;
      border-radius: 25px;
      overflow: hidden;
      height: 20px;
    }

    #skills .skill-level {
      height: 100%;
      background: #6c63ff;
      width: 0;
      border-radius: 25px 0 0 25px;
      transition: width 1.5s ease;
    }

    /* Projects */
    #projects .project-list {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 1.6rem;
    }

    #projects .project-card {
      background: #1f1f1f;
      border-radius: 10px;
      box-shadow: 0 0 10px #6c63ff66;
      padding: 1rem;
      display: flex;
      flex-direction: column;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    #projects .project-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 10px 25px #6c63ffcc;
    }

    #projects .project-image {
      width: 100%;
      height: 140px;
      border-radius: 8px;
      object-fit: cover;
      margin-bottom: 0.8rem;
      filter: brightness(0.9);
      transition: filter 0.3s ease;
      background: #333;
      display: flex;
      justify-content: center;
      align-items: center;
      color: #666;
      font-size: 1rem;
      font-style: italic;
    }

    #projects .project-image img {
      width: 100%;
      height: 100%;
      border-radius: 8px;
      object-fit: cover;
    }

    #projects .project-title {
      font-weight: 600;
      font-size: 1.3rem;
      margin-bottom: 0.4rem;
      color: #ddd;
    }

    #projects .project-desc {
      flex-grow: 1;
      font-size: 1rem;
      color: #bbb;
      margin-bottom: 0.6rem;
    }

    #projects .project-links a {
      color: #6c63ff;
      font-weight: 600;
      margin-right: 1rem;
    }

    /* Contact */
    #contact form {
      background: #1f1f1f;
      padding: 2rem;
      border-radius: 10px;
      box-shadow: 0 0 15px #6c63ff77;
      max-width: 600px;
      margin: 0 auto;
    }

    #contact form label {
      display: block;
      font-weight: 600;
      margin-bottom: 0.5rem;
      color: #ccc;
    }

    #contact form input,
    #contact form textarea {
      width: 100%;
      padding: 0.75rem;
      border-radius: 6px;
      border: none;
      margin-bottom: 1.2rem;
      font-size: 1rem;
      background: #333;
      color: #eee;
      resize: none;
      font-family: 'Poppins', sans-serif;
    }

    #contact form input:focus,
    #contact form textarea:focus {
      outline: 2px solid #6c63ff;
      background: #2a2a2a;
    }

    #contact form button {
      background: #6c63ff;
      border: none;
      color: white;
      padding: 0.9rem 2rem;
      font-size: 1.1rem;
      font-weight: 700;
      cursor: pointer;
      border-radius: 30px;
      transition: background-color 0.3s ease;
      width: 100%;
    }

    #contact form button:hover {
      background: #574de8;
    }

    /* Footer */
    footer {
      text-align: center;
      padding: 1.5rem 1rem;
      background: #1f1f1f;
      font-size: 0.9rem;
      color: #555;
      margin-top: auto;
    }

    /* Responsive */
    @media (min-width: 768px) {
      #hero {
        flex-direction: row;
        text-align: left;
        gap: 3rem;
      }

      #hero img {
        margin-bottom: 0;
      }
    }
  </style>
</head>
<body>
  <header>
    <div class="logo">MyPortfolio</div>
    <nav>
      <a href="#hero" class="active">Home</a>
      <a href="#about">About</a>
      <a href="#skills">Skills</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <main>
    <section id="hero">
      <img src=https://lh3.googleusercontent.com/a/ACg8ocKpaz2a5ZYsaVkwCWQbhQfcrggfI8Qpn4Pe1Yl4PgMc6TmDazF7=s288-c-no alt="Profile Picture" />
      <div>
        <h1>Hello, I'm Aby</h1>
        <p>Hi, I am a student who has an interest in the world of coding and I will continue to develop my coding skills.</p>
      </div>
    </section>

    <section id="about">
      <h2>About Me</h2>
      <p>
       
I am a beginner programmer who learns through social media such as YouTube, 
TikTok and Instagram and I have skills in photography, videography and sound system management. I want to continue to develop my skills
      </p>
    </section>

    <section id="skills">
      <h2>My Skills</h2>
      <div class="skill">
        <div class="skill-name">HTML & CSS</div>
        <div class="skill-bar"><div class="skill-level" data-level="90%"></div></div>
      </div>
      <div class="skill">
        <div class="skill-name">Manage Sound system</div>
        <div class="skill-bar"><div class="skill-level" data-level="85%"></div></div>
      </div>
      <div class="skill">
        <div class="skill-name">Photography</div>
        <div class="skill-bar"><div class="skill-level" data-level="80%"></div></div>
      </div>
      <div class="skill">
        <div class="skill-name">Videography</div>
        <div class="skill-bar"><div class="skill-level" data-level="65%"></div></div>
      </div>

    

    <section id="contact">
      <h2>Contact Me</h2>
      <form id="contact-form" onsubmit="return handleSubmit(event)">
        <label for="name">Name</label>
        <input type="text" id="name" name="name" placeholder="Your name" required />

        <label for="email">Email</label>
        <input type="email" id="email" name="email" placeholder="you@example.com" required />

        <label for="message">Message</label>
        <textarea id="message" name="message" rows="5" placeholder="Write your message here..." required></textarea>

        <button type="submit">Send Message</button>
      </form>
    </section>
  </main>

  <footer>
    &copy; 2025 Aby - Designed with passion &amp; code
  </footer>

  <script>
    // Animate skill bars on scroll
    function animateSkillBars() {
      const skillLevels = document.querySelectorAll('.skill-level');
      const triggerPoint = window.innerHeight * 0.9;

      skillLevels.forEach(bar => {
        const barTop = bar.getBoundingClientRect().top;
        if (barTop < triggerPoint) {
          bar.style.width = bar.getAttribute('data-level');
        }
      });
    }

    window.addEventListener('scroll', animateSkillBars);
    window.addEventListener('load', animateSkillBars);

    // Highlight nav link on scroll
    const sections = document.querySelectorAll('section');
    const navLinks = document.querySelectorAll('nav a');

    function highlightNav() {
      let index = sections.length;

      while(--index && window.scrollY + 100 < sections[index].offsetTop) {}
      
      navLinks.forEach(link => link.classList.remove('active'));
      navLinks[index].classList.add('active');
    }

    window.addEventListener('scroll', highlightNav);

    // Contact form submit handler (dummy)
    function handleSubmit(e) {
      e.preventDefault();
      alert('Thank you for your message! I will get back to you soon.');
      e.target.reset();
      return false;
    }
  </script>
</body>
</html>

```
