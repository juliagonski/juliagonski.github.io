<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0; padding: 0;
      background: #f9f9f9;
    }
    header {
      background: #8C1515; /* Stanford red */
      color: #fff;
      padding: 2rem 0 1rem 0;
    /* Updated: Use flex to place h1 left and image right */
    display: flex;
    align-items: center;
    justify-content: space-between;
    max-width: 900px;
    margin: 0 auto;
    }
  header h1 {
    margin: 0 0 0 1.5em;
    font-size: 2.7em;         /* Larger font */
    text-align: left;
    flex: 1;                  /* Take up remaining space */
  }
  header img {
    max-width: 60px;
    height: auto;
    border-radius: 50%;
    margin-right: 2.5em;
    box-shadow: 0 2px 8px rgba(0,0,0,.1);
  }
  @media (max-width: 200px) {
    header {
      flex-direction: column;
      text-align: center;
      padding: 1em 0;
    }
    header h1 {
      margin: 0.5em 0 0.2em 0;
      text-align: center;
      font-size: 2em;
    }
    header img {
      margin: 0 auto 1em auto;
      display: block;
    }
  }
    nav {
      background: #8C1515; /* Stanford red */
      display: flex;
      justify-content: center;
      border-bottom: 2px solid #A62626;
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
      background: #A62626; /* lighter Stanford red */
    }
    main {
      max-width: 800px;
      margin: 32px auto;
      background: #fff;
      padding: 2em;
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
    <h1>Julia Gonski</h1>
    <img src="SLAC_LogoSD.svg.png" alt="Your Name photo">
  </header>
  <p style="text-align:center; margin-top:-1.em;"> Particle physics  | Machine learning | Microelectronics </p>
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
    <!-- All tabs start empty except for About Me (shown by default) -->
    <section id="about" class="tab-content">
      <div id="about-content">Loading...</div>
    </section>
    <section id="research" class="tab-content" style="display:none">
      <div id="research-content">Loading...</div>
    </section>
    <section id="publications" class="tab-content" style="display:none">
      <div id="publications-content">Loading...</div>
    </section>
    <section id="people" class="tab-content" style="display:none">
      <div id="people-content">Loading...</div>
    </section>
    <section id="outreach" class="tab-content" style="display:none">
      <div id="outreach-content">Loading...</div>
    </section>
    <section id="contact" class="tab-content" style="display:none">
      <div id="contact-content">Loading...</div>
    </section>
  </main>
  
  <!-- ===== Tab Switcher & Content Loader Script ===== -->
  <script>
    // Map tab names to content file names
    const TAB_FILES = {
      about: "about.txt",
      research: "research.txt",
      publications: "publications.txt",
      people: "people.txt",
      outreach: "outreach.txt",
      contact: "contact.txt"
    };

    // Load content for a tab from its corresponding file
    function loadTabContent(tabId) {
      const fileName = TAB_FILES[tabId];
      const contentDiv = document.getElementById(tabId + "-content");
      fetch(fileName)
        .then(resp => {
          if (!resp.ok) throw new Error("File not found");
          return resp.text();
        })
        .then(text => {
          contentDiv.innerHTML = text;
        })
        .catch(e => {
          contentDiv.innerHTML = "<p style='color:#8C1515'>Content coming soon or not found.</p>";
        });
    }

    // Tab switching logic
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
      // Load content for selected tab
      loadTabContent(tabId);
    }

    // On page load, load default tab content
    document.addEventListener('DOMContentLoaded', function() {
      loadTabContent('about');
    });
  </script>
</body>
</html>
