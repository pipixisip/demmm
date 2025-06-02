/* Полное содержимое файла style.css */
body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 0;
    color: #333;
}

.container {
    width: 80%;
    margin: 0 auto;
    padding: 20px;
}

header {
    background: #0056b3;
    color: #fff;
    padding: 10px 0;
}

header h1 {
    margin: 0;
    padding: 10px 0;
}

nav ul {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
}

nav ul li {
    margin-right: 20px;
}

nav ul li a {
    color: #fff;
    text-decoration: none;
}

nav ul li a:hover {
    text-decoration: underline;
}

footer {
    background: #f4f4f4;
    text-align: center;
    padding: 10px 0;
    margin-top: 20px;
}

form {
    max-width: 500px;
    margin: 20px auto;
    padding: 20px;
    background: #f4f4f4;
    border-radius: 5px;
}

form div {
    margin-bottom: 15px;
}

form label {
    display: block;
    margin-bottom: 5px;
}

form input[type="text"],
form input[type="password"],
form input[type="email"],
form input[type="date"],
form select,
form textarea {
    width: 100%;
    padding: 8px;
    border: 1px solid #ddd;
    border-radius: 4px;
}

form button {
    background: #0056b3;
    color: #fff;
    border: 0;
    padding: 10px 15px;
    cursor: pointer;
    border-radius: 4px;
}

form button:hover {
    background: #003d82;
}

.alert {
    padding: 10px;
    margin-bottom: 20px;
    border-radius: 4px;
}

.alert-success {
    background: #d4edda;
    color: #155724;
}

.alert-error {
    background: #f8d7da;
    color: #721c24;
}

table {
    width: 100%;
    border-collapse: collapse;
    margin: 20px 0;
}

table, th, td {
    border: 1px solid #ddd;
}

th, td {
    padding: 12px;
    text-align: left;
}

th {
    background-color: #0056b3;
    color: white;
}

tr:nth-child(even) {
    background-color: #f2f2f2;
}

tr:hover {
    background-color: #ddd;
}

.status-new {
    color: #007bff;
}

.status-in_progress {
    color: #ffc107;
}

.status-completed {
    color: #28a745;
}

.welcome-section {
    text-align: center;
    padding: 40px 20px;
    background: linear-gradient(135deg, #0056b3, #003d82);
    color: white;
    margin-bottom: 40px;
    border-radius: 8px;
}

.welcome-section h2 {
    font-size: 2.2em;
    margin-bottom: 20px;
}

.welcome-section p {
    font-size: 1.2em;
    max-width: 800px;
    margin: 0 auto 30px;
}

.auth-links {
    display: flex;
    justify-content: center;
    gap: 20px;
}

.auth-links .button {
    padding: 12px 30px;
    background: white;
    color: #0056b3;
    text-decoration: none;
    border-radius: 4px;
    font-weight: bold;
    transition: all 0.3s;
}

.auth-links .button:hover {
    background: #f0f0f0;
    transform: translateY(-2px);
}

.courses-section {
    margin: 40px 0;
}

.courses-section h3 {
    text-align: center;
    font-size: 1.8em;
    margin-bottom: 30px;
    color: #0056b3;
}

.courses-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 25px;
    padding: 0 20px;
}

.course-card {
    background: white;
    border-radius: 8px;
    padding: 25px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s, box-shadow 0.3s;
    border: 1px solid #e0e0e0;
}

.course-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.15);
}

.course-icon {
    font-size: 2.5em;
    margin-bottom: 15px;
}

.course-card h4 {
    color: #0056b3;
    margin-bottom: 15px;
    font-size: 1.3em;
}

.course-card p {
    margin-bottom: 15px;
    color: #555;
}

.course-card ul {
    margin-top: 15px;
    padding-left: 20px;
    color: #666;
}

.course-card ul li {
    margin-bottom: 8px;
}

.benefits-section {
    margin: 60px 0;
    padding: 0 20px;
}

.benefits-section h3 {
    text-align: center;
    font-size: 1.8em;
    margin-bottom: 30px;
    color: #0056b3;
}

.benefits-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 30px;
    max-width: 1200px;
    margin: 0 auto;
}

.benefit-item {
    text-align: center;
    padding: 25px;
    background: #f9f9f9;
    border-radius: 8px;
    transition: all 0.3s;
}

.benefit-item:hover {
    background: #f0f0f0;
    transform: translateY(-3px);
}

.benefit-icon {
    font-size: 2.5em;
    margin-bottom: 15px;
    color: #0056b3;
}

.benefit-item h4 {
    color: #333;
    margin-bottom: 15px;
}

.benefit-item p {
    color: #666;
    line-height: 1.5;
}
