
style.css


:root {
    --primary: #4361ee;
    --secondary: #3f37c9;
    --accent: #4895ef;
    --dark: #1b263b;
    --light: #f8f9fa;
    --success: #4cc9f0;
    --warning: #f8961e;
    --danger: #f72585;
    --gray: #6c757d;
    --light-gray: #e9ecef;
    --border-radius: 8px;
    --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    --transition: all 0.3s ease;
}

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    line-height: 1.6;
    color: #333;
    background-color: #f8fafc;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
}

.container {
    width: 90%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
}

/* Header */
header {
    background: var(--dark);
    color: white;
    padding: 1rem 0;
    box-shadow: var(--shadow);
    position: sticky;
    top: 0;
    z-index: 1000;
}

.header-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

header h1 {
    font-size: 1.8rem;
    font-weight: 700;
    color: white;
    margin: 0;
}

nav ul {
    display: flex;
    list-style: none;
    gap: 1.5rem;
}

nav ul li a {
    color: white;
    text-decoration: none;
    font-weight: 500;
    padding: 0.5rem 0;
    position: relative;
    transition: var(--transition);
}

nav ul li a:hover {
    color: var(--accent);
}

nav ul li a::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 0;
    height: 2px;
    background: var(--accent);
    transition: var(--transition);
}

nav ul li a:hover::after {
    width: 100%;
}

/* Buttons */
.btn {
    display: inline-block;
    padding: 0.75rem 1.5rem;
    background: var(--primary);
    color: white;
    border: none;
    border-radius: var(--border-radius);
    font-weight: 500;
    text-decoration: none;
    cursor: pointer;
    transition: var(--transition);
    text-align: center;
}

.btn:hover {
    background: var(--secondary);
    transform: translateY(-2px);
    box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
}

.btn-outline {
    background: transparent;
    border: 2px solid var(--primary);
    color: var(--primary);
}

.btn-outline:hover {
    background: var(--primary);
    color: white;
}

.btn-sm {
    padding: 0.5rem 1rem;
    font-size: 0.875rem;
}

/* Forms */
.form-container {
    max-width: 600px;
    margin: 2rem auto;
    background: white;
    padding: 2rem;
    border-radius: var(--border-radius);
    box-shadow: var(--shadow);
}

.form-group {
    margin-bottom: 1.5rem;
}

.form-label {
    display: block;
    margin-bottom: 0.5rem;
    font-weight: 500;
}

.form-control {
    width: 100%;
    padding: 0.75rem;
    border: 1px solid #ddd;
    border-radius: var(--border-radius);
    font-family: inherit;
    transition: var(--transition);
}

.form-control:focus {
    outline: none;
    border-color: var(--primary);
    box-shadow: 0 0 0 3px rgba(67, 97, 238, 0.2);
}

textarea.form-control {
    min-height: 120px;
    resize: vertical;
}

/* Alerts */
.alert {
    padding: 1rem;
    margin-bottom: 1.5rem;
    border-radius: var(--border-radius);
}

.alert-success {
    background: #d1fae5;
    color: #065f46;
    border: 1px solid #a7f3d0;
}

.alert-error {
    background: #fee2e2;
    color: #b91c1c;
    border: 1px solid #fca5a5;
}

/* Tables */
.table {
    width: 100%;
    border-collapse: collapse;
    margin: 2rem 0;
    background: white;
    box-shadow: var(--shadow);
    border-radius: var(--border-radius);
    overflow: hidden;
}

.table th, .table td {
    padding: 1rem;
    text-align: left;
    border-bottom: 1px solid var(--light-gray);
}

.table th {
    background: var(--dark);
    color: white;
    font-weight: 500;
}

.table tr:hover {
    background-color: #f8f9fa;
}

/* Status badges */
.badge {
    display: inline-block;
    padding: 0.35rem 0.65rem;
    border-radius: 50rem;
    font-size: 0.875rem;
    font-weight: 500;
}

.badge-new {
    background: #dbeafe;
    color: #1d4ed8;
}

.badge-in_progress {
    background: #fef3c7;
    color: #b45309;
}

.badge-completed {
    background: #dcfce7;
    color: #15803d;
}

/* Hero section */
.hero {
    background: linear-gradient(135deg, var(--dark), var(--secondary));
    color: white;
    padding: 4rem 0;
    text-align: center;
    border-radius: var(--border-radius);
    margin: 2rem 0;
}

.hero h2 {
    font-size: 2.5rem;
    margin-bottom: 1.5rem;
}

.hero p {
    font-size: 1.25rem;
    max-width: 800px;
    margin: 0 auto 2rem;
    opacity: 0.9;
}

/* Cards */
.card {
    background: white;
    border-radius: var(--border-radius);
    overflow: hidden;
    box-shadow: var(--shadow);
    transition: var(--transition);
}

.card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
}

.card-header {
    padding: 1.5rem;
    border-bottom: 1px solid var(--light-gray);
}

.card-body {
    padding: 1.5rem;
}

.card-footer {
    padding: 1rem 1.5rem;
    border-top: 1px solid var(--light-gray);
    background: #f8f9fa;
}

/* Course cards */
.course-card {
    height: 100%;
    display: flex;
    flex-direction: column;
}

.course-img {
    height: 160px;
    background: var(--primary);
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-size: 3rem;
}

.course-body {
    flex: 1;
    padding: 1.5rem;
}

.course-title {
    margin-bottom: 1rem;
    color: var(--dark);
}

.course-meta {
    display: flex;
    justify-content: space-between;
    margin-top: 1.5rem;
    color: var(--gray);
    font-size: 0.9rem;
}

/* Utility classes */
.text-center {
    text-align: center;
}

.text-gray {
    color: var(--gray);
}

.mb-2 {
    margin-bottom: 0.5rem;
}

.mb-3 {
    margin-bottom: 0.75rem;
}

.mb-4 {
    margin-bottom: 1rem;
}

.mb-5 {
    margin-bottom: 1.5rem;
}

.mt-2 {
    margin-top: 0.5rem;
}

.mt-3 {
    margin-top: 0.75rem;
}

.mt-4 {
    margin-top: 1rem;
}

.mt-5 {
    margin-top: 1.5rem;
}

.my-2 {
    margin: 0.5rem 0;
}

.my-3 {
    margin: 0.75rem 0;
}

.my-4 {
    margin: 1rem 0;
}

.my-5 {
    margin: 1.5rem 0;
}

.p-6 {
    padding: 1.5rem;
}

.flex {
    display: flex;
}

.flex-col {
    flex-direction: column;
}

.gap-2 {
    gap: 0.5rem;
}

.gap-3 {
    gap: 0.75rem;
}

.gap-4 {
    gap: 1rem;
}

.grid {
    display: grid;
}

.grid-cols-1 {
    grid-template-columns: repeat(1, minmax(0, 1fr));
}

.grid-cols-2 {
    grid-template-columns: repeat(2, minmax(0, 1fr));
}

.grid-cols-3 {
    grid-template-columns: repeat(3, minmax(0, 1fr));
}

.grid-cols-4 {
    grid-template-columns: repeat(4, minmax(0, 1fr));
}

.gap-6 {
    gap: 1.5rem;
}

/* Dashboard */
.user-dashboard {
    margin: 2rem 0;
}

.user-info {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
    margin-top: 2rem;
}

.info-card {
    background: white;
    padding: 1.5rem;
    border-radius: var(--border-radius);
    box-shadow: var(--shadow);
}

/* Footer */
footer {
    background: var(--dark);
    color: white;
    padding: 3rem 0 1.5rem;
    margin-top: auto;
}

.footer-content {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 2rem;
    margin-bottom: 2rem;
}

.footer-section h3 {
    margin-bottom: 1rem;
    font-size: 1.2rem;
}

.footer-section ul {
    list-style: none;
}

.footer-section ul li {
    margin-bottom: 0.5rem;
}

.footer-section ul li a {
    color: #dee2e6;
    text-decoration: none;
    transition: var(--transition);
}

.footer-section ul li a:hover {
    color: var(--accent);
}

.copyright {
    text-align: center;
    padding-top: 1.5rem;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
    color: #adb5bd;
    font-size: 0.9rem;
}

/* Responsive */
@media (max-width: 768px) {
    .header-content {
        flex-direction: column;
        gap: 1rem;
    }
    
    nav ul {
        flex-wrap: wrap;
        justify-content: center;
    }
    
    .hero h2 {
        font-size: 2rem;
    }
    
    .hero p {
        font-size: 1.1rem;
    }
    
    .grid-cols-2, .grid-cols-3, .grid-cols-4 {
        grid-template-columns: 1fr;
    }
}
