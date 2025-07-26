<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Your Name - Homepage</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    /* -- Reset and Base Styles -- */
    body {
      font-family: Arial, sans-serif;
      margin: 0; padding: 0;
      background: #f9f9f9;
    }
    header {
      background: #222;
      color: #fff;
      padding: 2rem 0 1rem 0;
      text-align: center;
    }
    header img {
      max-width: 130px;
      border-radius: 50%;
      margin-bottom: 1rem;
    }
    h1 {
      margin: 0.2em 0 0.1em 0;
    }
    nav {
      background: #333;
      display: flex;
      justify-content: center;
      border-bottom: 2px solid #444;
    }
    nav button {
      background: none;
      border: none;
      color: #fff;
      padding: 1em 2em;
      font-size: 1em;
      cursor: pointer;
      transition: background 0.2s;
    }
    nav button.active,
    nav button:hover {
      background: #444;
    }
    main {
      max-width: 800px;
      margin: 32px auto;
      background: #fff;
      padding: 2em;
      border-radius: 0.5em;
      box-shadow: 0 2px 10px rgba(0,0,0,0.07);
      min-height: 350px;
    }
    /* -- Photos and Lists Styles -- */
    .people-list {
      display: flex;
      flex-wrap: wrap;
      gap: 1.5em;
    }
    .person {
      background: #f2f2f2;
      border-radius: 0.5em;
      padding: 1em;
      flex: 1 1 220px;
      min-width: 180px;
      max-width: 220px;
      text-align: center;
    }
    .person img {
      border-radius: 50%;
      width: 80px;
      height: 80px;
      object-fit: cover;
      margin-bottom: 0.5em;
    }
    ul.publications { list-style: disc inside; }
    .publication { margin-bottom: 0.8em; }
    @media (max-width: 600px) {
      main { padding: 1em; }
      nav button { padding: 0.7em 1em; font-size: 0.9em; }
      .people-list { flex-direction: column; gap: 1em; }
    }
  </style>
</head>
<body>
  <!-- ===== Header & Landing Page ===== -->
  <header>
    <!-- Add your profile photo here -->
    <img src="YOUR_PHOTO.jpg" alt="Your Name photo">
    <h1>Your Name</h1>
    <p>Your tagline or a short description goes here.</p>
    <!-- You can add more landing content below if desired -->
  </header>
  
  <!-- ===== Navigation Tabs ===== -->
  <nav>
    <button class="active" onclick="showTab('about')">About Me</button>
    <button onclick="showTab('research')">Research</button>
    <button onclick="showTab('publications')">Publications</button>
    <button onclick="showTab('people')">People</button>
    <button onclick="showTab('outreach')">Outreach & Media</button>
    <button onclick="showTab('contact')">Contact</button>
  </nav>
  
  <!-- ===== Tab Contents ===== -->
  <main>
    <!-- ===== About Me Tab ===== -->
    <section id="about" class="tab-content">
      <h2>About Me</h2>
      <img src="YOUR_PHOTO.jpg" alt="Your Name headshot" style="max-width:120px; float:right; margin-left:1em; border-radius:50%;">
      <p>
        <!-- Write your bio here -->
        Hi! I am [Your Name], a [position, e.g., physicist] at [your institution]. My research explores [your main research topics]. I'm passionate about [other interests or outreach].
      </p>
      <div style="clear:both"></div>
    </section>
    <!-- ===== Research Tab ===== -->
    <section id="research" class="tab-content" style="display:none">
      <h2>Research</h2>
      <p>
        <!-- Describe your research topics -->
        My research focuses on high-energy physics, particularly at the Large Hadron Collider (LHC).
      </p>
      <div>
        <!-- Add images related to your research -->
        <img src="lhc.jpg" alt="LHC" style="max-width:300px; margin:1em 0; width:100%;">
        <p>
          <!-- Short description of image -->
          The ATLAS detector at CERN's LHC, where we search for new particles and phenomena.
        </p>
      </div>
      <!-- Add more paragraphs and images as needed -->
    </section>
    <!-- ===== Publications Tab ===== -->
    <section id="publications" class="tab-content" style="display:none">
      <h2>Publications</h2>
      <ul class="publications">
        <li class="publication">
          <strong>Title of Paper One</strong> <br>
          <em>Journal Name</em>, 2023. <br>
          <!-- Add optional summary or link -->
          <span>Short summary or <a href="#">paper link</a>.</span>
        </li>
        <li class="publication">
          <strong>Title of Paper Two</strong> <br>
          <em>Journal Name</em>, 2022. <br>
          <span>Short summary or <a href="#">paper link</a>.</span>
        </li>
        <!-- Add more publications here -->
      </ul>
    </section>
    <!-- ===== People Tab ===== -->
    <section id="people" class="tab-content" style="display:none">
      <h2>People</h2>
      <div class="people-list">
        <!-- Example person -->
        <div class="person">
          <img src="person1.jpg" alt="Person 1">
          <strong>Dr. Collaborator One</strong>
          <p>
            Short bio or research interests.
          </p>
        </div>
        <div class="person">
          <img src="person2.jpg" alt="Person 2">
          <strong>Ms. Student A</strong>
          <p>
            PhD Student. Focus: Data analysis.
          </p>
        </div>
        <!-- Add more people as needed -->
      </div>
    </section>
    <!-- ===== Outreach & Media Tab ===== -->
    <section id="outreach" class="tab-content" style="display:none">
      <h2>Outreach & Media</h2>
      <ul>
        <li><a href="https://your-article-link.com" target="_blank">"Title of Public Article"</a> (Publication, 2022)</li>
        <li><a href="https://youtube.com/your-talk" target="_blank">Conference Talk Video</a></li>
        <!-- Add more outreach/media links here -->
      </ul>
    </section>
    <!-- ===== Contact Tab ===== -->
    <section id="contact" class="tab-content" style="display:none">
      <h2>Contact</h2>
      <p>
        <!-- Add your contact info here. For anti-spam, you can encode your email like: name [at] domain [dot] edu -->
        Email: your.email [at] domain [dot] edu <br>
        Office: Room 101, Physics Building<br>
        <!-- You can also add a contact form (requires additional setup) -->
      </p>
    </section>
  </main>
  

  <!-- ===== Tab Switcher Script ===== -->
  <script>
    function showTab(tabId) {
      var tabs = document.querySelectorAll('.tab-content');
      tabs.forEach(tab => tab.style.display = 'none');
      document.getElementById(tabId).style.display = '';
      var navButtons = document.querySelectorAll('nav button');
      navButtons.forEach(btn => btn.classList.remove('active'));
      navButtons[
        ['about', 'research', 'publications', 'people', 'outreach', 'contact']
        .indexOf(tabId)
      ].classList.add('active');
    }
  </script>
</body>
</html>
