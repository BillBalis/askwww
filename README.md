# askwww

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Michael Jackson App</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1>Michael Jackson </h1>
  </header>
  
  <nav>
    <ul>
      <li><a href="#" id="bio">Βιογραφια</a></li>
      <li><a href="#" id="photos">Φωτογραφιες</a></li>
      <li><a href="#" id="discography">Δισκογραφια</a></li>
      <li><a href="#" id="links">Συνδεσμοι</a></li>
      <li><a href="#" id="management">Διαχειριση</a></li>
    </ul>
  </nav>
  
  <aside id="sidebar">
    
  </aside>
  
  <main id="main-content">
   
  </main>
  
  <footer>
    <p>&copy; 2024 Michael Jackson App</p>
  </footer>

  <script src="script.js"></script>
  
</body>
</html>






body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
}

header, footer {
  background-color: #333;
  color: #fff;
  padding: 10px;
}

nav {
  background-color: #666;
  padding: 10px;
}

nav ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

nav ul li {
  display: inline;
  margin-right: 20px;
}

nav ul li a {
  color: #fff;
  text-decoration: none;
}

/* Πλευρικό μενού */
#sidebar {
  float: left;
  width: 20%;
  padding: 20px;
}


#main-content {
  float: left;
  width: 80%;
  padding: 20px;
}


nav ul li a:hover {
  color: #ccc;
}


@media screen and (max-width: 600px) {
  #sidebar, #main-content {
    width: 100%;
    float: none;
  }
}




document.addEventListener('DOMContentLoaded', function () {
  const navLinks = document.querySelectorAll('nav ul li a');
  const sidebar = document.getElementById('sidebar');

  navLinks.forEach(link => {
    link.addEventListener('click', function (event) {
      event.preventDefault();
      const sectionId = this.getAttribute('id');
      fetchSidebarContent(sectionId);
    });
  });

  function fetchSidebarContent(sectionId) {
    fetch(`sidebar/${sectionId}.html`)
      .then(response => response.text())
      .then(data => {
        sidebar.innerHTML = data;
      })
      .catch(error => console.error('Error fetching sidebar content:', error));
  }

 
  const loginForm = document.getElementById('login-form');
  loginForm.addEventListener('submit', function (event) {
    event.preventDefault();
    const username = document.getElementById('username').value;
    const password = document.getElementById('password').value;
    if (username === 'Bill' && password === '01634') {
      alert('Συνδεθηκατε επιτυχως!');
    } else {
      alert('Λαθος ονομα χρηστη η κωδικος.');
    }
  });
});
