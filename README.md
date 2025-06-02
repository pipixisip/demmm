Вот методичка для вашего проекта "Портал дополнительного профессионального образования":

# Портал дополнительного профессионального образования

## Содержание
1. [Файл стилей (CSS)](#stylescss)
2. [PHP файлы](#php-файлы)
   - [admin.php](#adminphp)
   - [applications.php](#applicationsphp)
   - [create_application.php](#create_applicationphp)
   - [dashboard.php](#dashboardphp)
   - [index.php](#indexphp)
   - [login.php](#loginphp)
   - [logout.php](#logoutphp)
   - [register.php](#registerphp)
3. [Вспомогательные файлы](#вспомогательные-файлы)
   - [auth.php](#authphp)
   - [db.php](#dbphp)
   - [header.php](#headerphp)
   - [footer.php](#footerphp)
4. [SQL файл](#education_portalsql)

---

## styles.css {#stylescss}

```css
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

/* Основные стили для главной страницы */
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

/* Стили для секции курсов */
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

/* Стили для секции преимуществ */
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

.button {
    display: inline-block;
    padding: 10px 20px;
    background: #0056b3;
    color: white;
    text-decoration: none;
    border-radius: 4px;
    margin: 10px 0;
}

.button:hover {
    background: #003d82;
}

.actions {
    margin: 20px 0;
    display: flex;
    gap: 15px;
}
```

---

## PHP файлы

### admin.php {#adminphp}

```php
<?php
require_once 'includes/auth.php';
redirectIfNotLoggedIn();
redirectIfNotAdmin();
require_once 'includes/db.php';

// Обработка изменения статуса заявки
if ($_SERVER['REQUEST_METHOD'] === 'POST' && isset($_POST['status'])) {
    $application_id = $_POST['application_id'];
    $status = $_POST['status'];

    $stmt = $pdo->prepare("UPDATE applications SET status = ? WHERE id = ?");
    $stmt->execute([$status, $application_id]);
    $_SESSION['success_message'] = 'Статус заявки успешно обновлен!';
    header('Location: admin.php');
    exit();
}

// Получаем все заявки
$stmt = $pdo->query("
    SELECT a.*, u.full_name, u.login, c.name as course_name 
    FROM applications a 
    JOIN users u ON a.user_id = u.id 
    JOIN courses c ON a.course_id = c.id 
    ORDER BY a.created_at DESC
");
$applications = $stmt->fetchAll(PDO::FETCH_ASSOC);

require_once 'includes/header.php';

if (isset($_SESSION['success_message'])) {
    echo '<div class="alert alert-success">' . htmlspecialchars($_SESSION['success_message']) . '</div>';
    unset($_SESSION['success_message']);
}
?>

<h2>Панель администратора</h2>

<?php if (empty($applications)): ?>
    <p>Нет заявок</p>
<?php else: ?>
    <table>
        <thead>
            <tr>
                <th>Пользователь</th>
                <th>Логин</th>
                <th>Курс</th>
                <th>Дата начала</th>
                <th>Способ оплаты</th>
                <th>Статус</th>
                <th>Дата создания</th>
                <th>Отзыв</th>
                <th>Действия</th>
            </tr>
        </thead>
        <tbody>
            <?php foreach ($applications as $app): ?>
                <tr>
                    <td><?php echo htmlspecialchars($app['full_name']); ?></td>
                    <td><?php echo htmlspecialchars($app['login']); ?></td>
                    <td><?php echo htmlspecialchars($app['course_name']); ?></td>
                    <td><?php echo htmlspecialchars($app['start_date']); ?></td>
                    <td><?php echo $app['payment_method'] == 'cash' ? 'Наличные' : 'Банковский перевод'; ?></td>
                    <td class="status-<?php echo str_replace('_', '-', $app['status']); ?>">
                        <?php 
                        switch ($app['status']) {
                            case 'new': echo 'Новая'; break;
                            case 'in_progress': echo 'Идет обучение'; break;
                            case 'completed': echo 'Обучение завершено'; break;
                            default: echo $app['status'];
                        }
                        ?>
                    </td>
                    <td><?php echo htmlspecialchars($app['created_at']); ?></td>
                    <td><?php echo !empty($app['feedback']) ? htmlspecialchars($app['feedback']) : 'Нет отзыва'; ?></td>
                    <td>
                        <form method="post">
                            <input type="hidden" name="application_id" value="<?php echo $app['id']; ?>">
                            <select name="status">
                                <option value="new" <?php echo $app['status'] == 'new' ? 'selected' : ''; ?>>Новая</option>
                                <option value="in_progress" <?php echo $app['status'] == 'in_progress' ? 'selected' : ''; ?>>Идет обучение</option>
                                <option value="completed" <?php echo $app['status'] == 'completed' ? 'selected' : ''; ?>>Обучение завершено</option>
                            </select>
                            <button type="submit">Обновить</button>
                        </form>
                    </td>
                </tr>
            <?php endforeach; ?>
        </tbody>
    </table>
<?php endif; ?>

<?php
require_once 'includes/footer.php';
?>
```

### applications.php {#applicationsphp}

```php
<?php
require_once 'includes/auth.php';
redirectIfNotLoggedIn();
require_once 'includes/db.php';

$user_id = $_SESSION['user_id'];

// Обработка отправки отзыва
if ($_SERVER['REQUEST_METHOD'] === 'POST' && isset($_POST['feedback'])) {
    $application_id = $_POST['application_id'];
    $feedback = trim($_POST['feedback']);

    if (!empty($feedback)) {
        $stmt = $pdo->prepare("UPDATE applications SET feedback = ? WHERE id = ? AND user_id = ?");
        $stmt->execute([$feedback, $application_id, $user_id]);
        $_SESSION['success_message'] = 'Отзыв успешно сохранен!';
        header('Location: applications.php');
        exit();
    }
}

// Получаем заявки пользователя
$stmt = $pdo->prepare("
    SELECT a.*, c.name as course_name 
    FROM applications a 
    JOIN courses c ON a.course_id = c.id 
    WHERE a.user_id = ? 
    ORDER BY a.created_at DESC
");
$stmt->execute([$user_id]);
$applications = $stmt->fetchAll(PDO::FETCH_ASSOC);

require_once 'includes/header.php';

if (isset($_SESSION['success_message'])) {
    echo '<div class="alert alert-success">' . htmlspecialchars($_SESSION['success_message']) . '</div>';
    unset($_SESSION['success_message']);
}
?>

<h2>Мои заявки</h2>

<?php if (empty($applications)): ?>
    <p>У вас пока нет заявок. <a href="create_application.php">Создать новую заявку</a></p>
<?php else: ?>
    <table>
        <thead>
            <tr>
                <th>Курс</th>
                <th>Дата начала</th>
                <th>Способ оплаты</th>
                <th>Статус</th>
                <th>Дата создания</th>
                <th>Отзыв</th>
            </tr>
        </thead>
        <tbody>
            <?php foreach ($applications as $app): ?>
                <tr>
                    <td><?php echo htmlspecialchars($app['course_name']); ?></td>
                    <td><?php echo htmlspecialchars($app['start_date']); ?></td>
                    <td><?php echo $app['payment_method'] == 'cash' ? 'Наличные' : 'Банковский перевод'; ?></td>
                    <td class="status-<?php echo str_replace('_', '-', $app['status']); ?>">
                        <?php 
                        switch ($app['status']) {
                            case 'new': echo 'Новая'; break;
                            case 'in_progress': echo 'Идет обучение'; break;
                            case 'completed': echo 'Обучение завершено'; break;
                            default: echo $app['status'];
                        }
                        ?>
                    </td>
                    <td><?php echo htmlspecialchars($app['created_at']); ?></td>
                    <td>
                        <?php if ($app['status'] == 'completed'): ?>
                            <?php if (!empty($app['feedback'])): ?>
                                <p><?php echo htmlspecialchars($app['feedback']); ?></p>
                            <?php else: ?>
                                <form method="post">
                                    <input type="hidden" name="application_id" value="<?php echo $app['id']; ?>">
                                    <textarea name="feedback" placeholder="Оставьте ваш отзыв" required></textarea>
                                    <button type="submit">Отправить отзыв</button>
                                </form>
                            <?php endif; ?>
                        <?php else: ?>
                            <p>Доступно после завершения обучения</p>
                        <?php endif; ?>
                    </td>
                </tr>
            <?php endforeach; ?>
        </tbody>
    </table>
<?php endif; ?>

<?php
require_once 'includes/footer.php';
?>
```

### create_application.php {#create_applicationphp}

```php
<?php
require_once 'includes/auth.php';
redirectIfNotLoggedIn();
require_once 'includes/db.php';

$errors = [];
$course_id = $start_date = $payment_method = '';

// Получаем список курсов
$courses = $pdo->query("SELECT * FROM courses")->fetchAll(PDO::FETCH_ASSOC);

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $course_id = $_POST['course_id'];
    $start_date = $_POST['start_date'];
    $payment_method = $_POST['payment_method'];

    // Валидация
    if (empty($course_id)) {
        $errors[] = 'Необходимо выбрать курс';
    }

    if (empty($start_date)) {
        $errors[] = 'Необходимо указать дату начала обучения';
    } elseif (strtotime($start_date) < strtotime('today')) {
        $errors[] = 'Дата начала обучения не может быть в прошлом';
    }

    if (empty($payment_method)) {
        $errors[] = 'Необходимо выбрать способ оплаты';
    }

    if (empty($errors)) {
        $stmt = $pdo->prepare("INSERT INTO applications (user_id, course_id, start_date, payment_method) VALUES (?, ?, ?, ?)");
        $stmt->execute([$_SESSION['user_id'], $course_id, $start_date, $payment_method]);

        $_SESSION['success_message'] = 'Заявка успешно создана!';
        header('Location: applications.php');
        exit();
    }
}

require_once 'includes/header.php';
?>

<h2>Создание новой заявки</h2>

<?php if (!empty($errors)): ?>
    <div class="alert alert-error">
        <ul>
            <?php foreach ($errors as $error): ?>
                <li><?php echo htmlspecialchars($error); ?></li>
            <?php endforeach; ?>
        </ul>
    </div>
<?php endif; ?>

<form method="post">
    <div>
        <label for="course_id">Курс:</label>
        <select id="course_id" name="course_id" required>
            <option value="">-- Выберите курс --</option>
            <?php foreach ($courses as $course): ?>
                <option value="<?php echo $course['id']; ?>" <?php echo ($course_id == $course['id']) ? 'selected' : ''; ?>>
                    <?php echo htmlspecialchars($course['name']); ?>
                </option>
            <?php endforeach; ?>
        </select>
    </div>
    <div>
        <label for="start_date">Желаемая дата начала обучения:</label>
        <input type="date" id="start_date" name="start_date" value="<?php echo htmlspecialchars($start_date); ?>" required>
    </div>
    <div>
        <label>Способ оплаты:</label>
        <div>
            <input type="radio" id="cash" name="payment_method" value="cash" <?php echo ($payment_method == 'cash') ? 'checked' : ''; ?> required>
            <label for="cash">Наличные</label>
        </div>
        <div>
            <input type="radio" id="bank_transfer" name="payment_method" value="bank_transfer" <?php echo ($payment_method == 'bank_transfer') ? 'checked' : ''; ?> required>
            <label for="bank_transfer">Перевод на банковский счет</label>
        </div>
    </div>
    <div>
        <button type="submit">Отправить заявку</button>
    </div>
</form>

<?php
require_once 'includes/footer.php';
?>
```

### dashboard.php {#dashboardphp}

```php
<?php
require_once 'includes/auth.php';
redirectIfNotLoggedIn();

require_once 'includes/db.php';
require_once 'includes/header.php';

$user_id = $_SESSION['user_id'];
$stmt = $pdo->prepare("SELECT full_name FROM users WHERE id = ?");
$stmt->execute([$user_id]);
$user = $stmt->fetch();
?>

<h2>Добро пожаловать, <?php echo htmlspecialchars($user['full_name']); ?>!</h2>
<p>Вы вошли в систему как <?php echo htmlspecialchars($_SESSION['login']); ?></p>

<div class="actions">
    <a href="create_application.php" class="button">Создать новую заявку</a>
    <a href="applications.php" class="button">Мои заявки</a>
</div>

<?php
require_once 'includes/footer.php';
?>
```

### index.php {#indexphp}

```php
<?php
require_once 'includes/auth.php';
require_once 'includes/header.php';
?>

<div class="welcome-section">
    <h2>Добро пожаловать на портал дополнительного профессионального образования</h2>
    <p>Повышайте квалификацию с нашими экспертами. Выберите курс и начните обучение уже сегодня!</p>
    
    <?php if (!isLoggedIn()): ?>
        <div class="auth-links">
            <a href="register.php" class="button">Зарегистрироваться</a>
            <a href="login.php" class="button">Войти</a>
        </div>
    <?php endif; ?>
</div>

<div class="courses-section">
    <h3>Наши курсы</h3>
    <div class="courses-grid">
        <div class="course-card">
            <div class="course-icon">📊</div>
            <h4>Программирование на Python</h4>
            <p>Освойте один из самых популярных языков программирования с нуля до профессионального уровня.</p>
            <ul>
                <li>Длительность: 3 месяца</li>
                <li>Формат: Онлайн</li>
                <li>Стоимость: 15,000 руб.</li>
            </ul>
        </div>
        
        <div class="course-card">
            <div class="course-icon">💻</div>
            <h4>Веб-разработка</h4>
            <p>Полный курс по созданию современных веб-приложений с использованием HTML, CSS, JavaScript и PHP.</p>
            <ul>
                <li>Длительность: 4 месяца</li>
                <li>Формат: Онлайн</li>
                <li>Стоимость: 20,000 руб.</li>
            </ul>
        </div>
        
        <div class="course-card">
            <div class="course-icon">📈</div>
            <h4>Анализ данных</h4>
            <p>Научитесь работать с большими данными, визуализировать информацию и принимать решения на основе анализа.</p>
            <ul>
                <li>Длительность: 2.5 месяца</li>
                <li>Формат: Онлайн</li>
                <li>Стоимость: 18,000 руб.</li>
            </ul>
        </div>
        
        <div class="course-card">
            <div class="course-icon">🎨</div>
            <h4>Графический дизайн</h4>
            <p>Освойте Adobe Photoshop и Illustrator, научитесь создавать профессиональный дизайн.</p>
            <ul>
                <li>Длительность: 2 месяца</li>
                <li>Формат: Онлайн</li>
                <li>Стоимость: 12,000 руб.</li>
            </ul>
        </div>
        
        <div class="course-card">
            <div class="course-icon">📢</div>
            <h4>Маркетинг и реклама</h4>
            <p>Современные инструменты digital-маркетинга и стратегии продвижения бизнеса.</p>
            <ul>
                <li>Длительность: 3 месяца</li>
                <li>Формат: Онлайн</li>
                <li>Стоимость: 16,000 руб.</li>
            </ul>
        </div>
        
        <div class="course-card">
            <div class="course-icon">🤖</div>
            <h4>Основы искусственного интеллекта</h4>
            <p>Введение в машинное обучение и нейронные сети для начинающих.</p>
            <ul>
                <li>Длительность: 3.5 месяца</li>
                <li>Формат: Онлайн</li>
                <li>Стоимость: 22,000 руб.</li>
            </ul>
        </div>
    </div>
</div>

<div class="benefits-section">
    <h3>Почему выбирают нас?</h3>
    <div class="benefits-grid">
        <div class="benefit-item">
            <div class="benefit-icon">🏆</div>
            <h4>Профессиональные преподаватели</h4>
            <p>Наши преподаватели - практикующие специалисты с многолетним опытом.</p>
        </div>
        
        <div class="benefit-item">
            <div class="benefit-icon">📅</div>
            <h4>Гибкий график</h4>
            <p>Возможность обучаться в удобное для вас время.</p>
        </div>
        
        <div class="benefit-item">
            <div class="benefit-icon">📜</div>
            <h4>Официальный диплом</h4>
            <p>По окончании курса вы получаете диплом установленного образца.</p>
        </div>
        
        <div class="benefit-item">
            <div class="benefit-icon">💼</div>
            <h4>Помощь с трудоустройством</h4>
            <p>Лучшим выпускникам помогаем найти работу.</p>
        </div>
    </div>
</div>

<?php
require_once 'includes/footer.php';
?>
```

### login.php {#loginphp}

```php
<?php
require_once 'includes/db.php';
require_once 'includes/auth.php';

if (isLoggedIn()) {
    header('Location: dashboard.php');
    exit();
}

$errors = [];
$login = '';

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $login = trim($_POST['login']);
    $password = $_POST['password'];

    if (empty($login) || empty($password)) {
        $errors[] = 'Логин и пароль обязательны для заполнения';
    } else {
        $stmt = $pdo->prepare("SELECT * FROM users WHERE login = ?");
        $stmt->execute([$login]);
        $user = $stmt->fetch();

        if ($user && $password === $user['password']) {
            $_SESSION['user_id'] = $user['id'];
            $_SESSION['login'] = $user['login'];
            $_SESSION['is_admin'] = ($user['login'] === 'admin');
            
            header('Location: dashboard.php');
            exit();
        } else {
            $errors[] = 'Неверный логин или пароль';
        }
    }
}

require_once 'includes/header.php';

if (isset($_SESSION['success_message'])) {
    echo '<div class="alert alert-success">' . htmlspecialchars($_SESSION['success_message']) . '</div>';
    unset($_SESSION['success_message']);
}
?>

<h2>Вход в систему</h2>

<?php if (!empty($errors)): ?>
    <div class="alert alert-error">
        <ul>
            <?php foreach ($errors as $error): ?>
                <li><?php echo htmlspecialchars($error); ?></li>
            <?php endforeach; ?>
        </ul>
    </div>
<?php endif; ?>

<form method="post">
    <div>
        <label for="login">Логин:</label>
        <input type="text" id="login" name="login" value="<?php echo htmlspecialchars($login); ?>" required>
    </div>
    <div>
        <label for="password">Пароль:</label>
        <input type="password" id="password" name="password" required>
    </div>
    <div>
        <button type="submit">Войти</button>
    </div>
</form>

<p>Еще не зарегистрированы? <a href="register.php">Зарегистрируйтесь</a></p>

<?php
require_once 'includes/footer.php';
?>
```

### logout.php {#logoutphp}

```php
<?php
require_once 'includes/auth.php';

session_destroy();
header('Location: login.php');
exit();
?>
```

### register.php {#registerphp}

```php
<?php
require_once 'includes/db.php';
require_once 'includes/auth.php';

if (isLoggedIn()) {
    header('Location: dashboard.php');
    exit();
}

$errors = [];
$full_name = $phone = $email = $login = $password = '';

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $full_name = trim($_POST['full_name']);
    $phone = trim($_POST['phone']);
    $email = trim($_POST['email']);
    $login = trim($_POST['login']);
    $password = $_POST['password'];

    // Валидация
    if (empty($full_name)) {
        $errors[] = 'ФИО обязательно для заполнения';
    } elseif (!preg_match('/^[А-Яа-яЁё\s]+$/u', $full_name)) {
        $errors[] = 'ФИО должно содержать только кириллические символы и пробелы';
    }

    if (empty($phone)) {
        $errors[] = 'Телефон обязателен для заполнения';
    } elseif (!preg_match('/^\+7\(\d{3}\)-\d{3}-\d{2}-\d{2}$/', $phone)) {
        $errors[] = 'Телефон должен быть в формате +7(XXX)-XXX-XX-XX';
    }

    if (empty($email)) {
        $errors[] = 'Email обязателен для заполнения';
    } elseif (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
        $errors[] = 'Некорректный формат email';
    }

    if (empty($login)) {
        $errors[] = 'Логин обязателен для заполнения';
    } elseif (strlen($login) < 6) {
        $errors[] = 'Логин должен содержать не менее 6 символов';
    } elseif (!preg_match('/^[А-Яа-яЁё0-9_]+$/u', $login)) {
        $errors[] = 'Логин должен содержать только кириллические символы, цифры и подчеркивания';
    }

    if (empty($password)) {
        $errors[] = 'Пароль обязателен для заполнения';
    } elseif (strlen($password) < 6) {
        $errors[] = 'Пароль должен содержать не менее 6 символов';
    }

    // Проверка уникальности логина
    if (empty($errors)) {
        $stmt = $pdo->prepare("SELECT id FROM users WHERE login = ?");
        $stmt->execute([$login]);
        if ($stmt->fetch()) {
            $errors[] = 'Этот логин уже занят';
        }
    }

    if (empty($errors)) {
        $hashed_password = password_hash($password, PASSWORD_DEFAULT);
        $stmt = $pdo->prepare("INSERT INTO users (full_name, phone, email, login, password) VALUES (?, ?, ?, ?, ?)");
        $stmt->execute([$full_name, $phone, $email, $login, $hashed_password]);

        $_SESSION['success_message'] = 'Регистрация прошла успешно! Теперь вы можете войти.';
        header('Location: login.php');
        exit();
    }
}

require_once 'includes/header.php';
?>

<h2>Регистрация</h2>

<?php if (!empty($errors)): ?>
    <div class="alert alert-error">
        <ul>
            <?php foreach ($errors as $error): ?>
                <li><?php echo htmlspecialchars($error); ?></li>
            <?php endforeach; ?>
        </ul>
    </div>
<?php endif; ?>

<form method="post">
    <div>
        <label for="full_name">ФИО:</label>
        <input type="text" id="full_name" name="full_name" value="<?php echo htmlspecialchars($full_name); ?>" required>
    </div>
    <div>
        <label for="phone">Телефон:</label>
        <input type="text" id="phone" name="phone" placeholder="+7(XXX)-XXX-XX-XX" value="<?php echo htmlspecialchars($phone); ?>" required>
    </div>
    <div>
        <label for="email">Email:</label>
        <input type="email" id="email" name="email" value="<?php echo htmlspecialchars($email); ?>" required>
    </div>
    <div>
        <label for="login">Логин:</label>
        <input type="text" id="login" name="login" value="<?php echo htmlspecialchars($login); ?>" required>
    </div>
    <div>
        <label for="password">Пароль:</label>
        <input type="password" id="password" name="password" required>
    </div>
    <div>
        <button type="submit">Зарегистрироваться</button>
    </div>
</form>

<p>Уже зарегистрированы? <a href="login.php">Войдите</a></p>

<?php
require_once 'includes/footer.php';
?>
```

---

## Вспомогательные файлы

### auth.php {#authphp}

```php
<?php
session_start();

function isLoggedIn() {
    return isset($_SESSION['user_id']);
}

function isAdmin() {
    return isset($_SESSION['is_admin']) && $_SESSION['is_admin'];
}

function redirectIfNotLoggedIn() {
    if (!isLoggedIn()) {
        header('Location: login.php');
        exit();
    }
}

function redirectIfNotAdmin() {
    if (!isAdmin()) {
        header('Location: dashboard.php');
        exit();
    }
}
?>
```

### db.php {#dbphp}

```php
<?php
$host = 'localhost';
$dbname = 'education_portal';
$username = 'root';
$password = '';

try {
    $pdo = new PDO("mysql:host=$host;dbname=$dbname;charset=utf8", $username, $password);
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
} catch (PDOException $e) {
    die("Ошибка подключения к базе данных: " . $e->getMessage());
}
?>
```

### header.php {#headerphp}

```php
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Портал ДПО</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <header>
        <div class="container">
            <h1>Корочки.есть</h1>
            <nav>
                <ul>
                    <?php if (isLoggedIn()): ?>
                        <li><a href="dashboard.php">Главная</a></li>
                        <li><a href="create_application.php">Новая заявка</a></li>
                        <li><a href="applications.php">Мои заявки</a></li>
                        <?php if (isAdmin()): ?>
                            <li><a href="admin.php">Панель администратора</a></li>
                        <?php endif; ?>
                        <li><a href="logout.php">Выйти</a></li>
                    <?php else: ?>
                        <li><a href="index.php
