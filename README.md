# <h2 align="center">  МИНИСТЕРСТВО НАУКИ И ВЫСШЕГО ОБРАЗОВАНИЯ РОССИЙСКОЙ ФЕДЕРАЦИИ ФЕДЕРАЛЬНОЕ ГОСУДАРСТВЕННОЕ БЮДЖЕТНОЕ ОБРАЗОВАТЕЛЬНОЕ УЧРЕЖДЕНИЕ ВЫСШЕГО ОБРАЗОВАНИЯ «САХАЛИНСКИЙ ГОСУДАРСТВЕННЫЙ УНИВЕРСИТЕТ» </h2>
<div align="center">
<h3>Институт естественных наук и техносферной безопасности
<br>
Кафедра информатики
<br>
Половников Владислав Олегович</h3>

<br>
<h3>Лабораторная работа №8
<br>
“Введение в вэб-разработку”
<br>
01.03.02 Прикладная математика и информатика</h3>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<h3 align="right">Научный руководитель
<br>
Соболев Евгений Игоревич
</h3>

<h3 align="center">Южно-Сахалинск
<br>
2022г.
</h3>
<hr>
</div>
<p>
HTML (HyperText Markup Language) - язык разметки гипертекста - предназначен для создания Web-страниц.
Под гипертекстом в этом случае понимается текст, связанный с другими текстами указателями-ссылками.
HTML представляет собой достаточно простой набор кодов, которые описывают структуру документа. HTML позволяет выделить в тексте отдельные логические части (заголовки, абзацы, списки и т.д.), поместить на Web-страницу подготовленную фотографию или картинку, организовать на странице ссылки для связи с другими документами.
HTML не задает конкретные и точные атрибуты форматирования документа. Конкретный вид документа окончательно определяет только программа-браузер на компьютере пользователя Интернета. 
HTML также не является языком программирования, но web-страницы могут включать в себя встроенные программы-скрипты на языкахJavascript и Visual Basic Script и программы-апплеты на языке Java.
</p>

<h3 align="center">Задание</h3>

Задачи:
1.Создать базу данных «university» в программе-дизайнере MySQL Workbench.
2.В базе данных «university» создать таблицу «students» с полями:
id тип int – ключ (PK), счетчик (AI);name тип varchar, ненулевое (NN);d_id тип int.
3.Заполнить таблицу «students» произвольными записями (вкладка Inserts) - 5 строк (поле id следует заполнять нулями).
4.Сохранить созданную в программе-дизайнере схему базы данных на локальный компьютер.
5.Запустить генерацию базы данных на сервере MySQL (Пункт меню: Database->Forward Engineer. В опциях необходимо поставить галки против пунктов: DROP Objects Before Each CREATE Object и Generate INSERT
Statements for Tables).
6.Подключиться к базе данных MySQL (команда mysql –u root –p).
7.Активизировать базу данных «university» (команда use).
8.Выполнить SQL команду: SELECT * FROM students; результаты записать в отчет.
9.Выполнить SQL команды:
UPDATE students SET name = ‘Ivan’ WHERE id = 2;
SELECT * FROM students WHERE id = 2; результаты записать в отчет.
10. Выполнить SQL команды:
DELETE FROM students WHERE id = 2;
SELECT * FROM students; результаты записать в отчет.
11. Проанализировать полученные результаты.

Задание. Гостевая книга. JavaScript и работа с файлами.
К базовой функциональности, следует добавить следующие возможности:
▪	К сообщению пользователь может добавить картинку или текстовый файл
▪	Изображение должно быть не более 320х240 пикселей, при попытке залить изображение большего размера, картинка должна быть пропорционально уменьшена до заданных размеров, допустимые форматы файлов: JPG, GIF, PNG
▪	Текстовый файл не должен быть больше чем 100кб, формат TXT
▪	Просмотр файлов должен сопровождаться визуальными эффектами (для примера можно посмотреть http://www.huddletogether.com/projects/lightbox/ )






<h1 align="center">Решение</h1>

<h2 align="center">Задания 1-11</h2>

![img4](/images/4.png)

![img5](/images/5.png)

![img6](/images/6.png)

![img7](/images/7.png)

<h2 align="center">Гостевая книга</h2>

![img1](/images/1.png)

![img2](/images/2.png)

![img3](/images/3.png)

<h3>Главная папка index.php</h3>

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-Zenh87qX5JnK2Jl0vWa8Ck2rdkQ2Bzep5IDxbcnCeuOxjzrPF/et3URy9Bv1WTRi" crossorigin="anonymous">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-OERcA2EqjJCMA+/3y+gxIOqMEjwtxJY7qPCqsdltbNJuaOe923+mo//f6V8Qbsw3" crossorigin="anonymous"></script>
    <style>
    body{
        background-image: url("bg.png");
        background-size: 100% 100%;
        background-repeat: no-repeat;
    }
div{
    width: auto;
    padding: 75px;
}
table,
th,
td {
    border: 1px solid;
    padding: 3px;
    padding-left: 5px;
    padding-right: 5px;
}
a{
    width: 100%;
    height: 50px;
    font-size: 10px;
}
    </style>
    <title>Гостевая книга</title>
</head>
<body class="d-flex justify-content-md-center align-items-center vh-100">
            <div class="d-grid gap-3">
                <a class="btn btn-primary fs-4" href="./create/">Ввести сообщение</a>
                <a class="btn btn-primary fs-4" href="./messages/">Просмотреть сообщения</a>
            </div>
</body>
</html>
```
<h3>Файл create/index.php</h3>

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-Zenh87qX5JnK2Jl0vWa8Ck2rdkQ2Bzep5IDxbcnCeuOxjzrPF/et3URy9Bv1WTRi" crossorigin="anonymous">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-OERcA2EqjJCMA+/3y+gxIOqMEjwtxJY7qPCqsdltbNJuaOe923+mo//f6V8Qbsw3" crossorigin="anonymous"></script>
    <script src='https://www.google.com/recaptcha/api.js'></script>
    <script src="./jquery-3.6.1.min.js"></script>
    <script src="loadfile.js"></script>
    <style>
    body{
        background-image: url("../bg.png");
        background-size: 100% 100%;
        background-repeat: repeat-y;
    }
    form{
        background: linear-gradient(0deg, #7fc7ff, white);
        -webkit-border-radius: 50px;
        -moz-border-radius: 50px;
        border-radius: 50px;
        border: none;
    }
    div .form{
        width: auto;
        padding: 75px;
    }
    a{
        width: 100%;
        height: 50px;
        font-size: 10px;
    }
    </style>
    <title>Гостевая книга</title>
</head>
<body class="d-flex justify-content-md-center align-items-center vh-100">
            <div class="d-grid gap-3" style="width: 650px; padding: 75px">
                <form  enctype="multipart/form-data" action="./script.php" method="post">
                <div class="form">
                    <input type="text" class="form-control" placeholder="Ваше имя (обязательно)" id="name" name="name"required>
                    <br>
                    <input type="email" class="form-control" placeholder="Ваш email (обязательно)" id="email" name="email" required>
                    <br>
                    <input type="text" class="form-control" placeholder="Homepage (необязательно)" id="homepage" name="homepage">
                    <br>
                    <div class="g-recaptcha" data-sitekey="6LetvG4jAAAAAINAJN3snODSprVUyVEYMk4LOKq2" style="padding: 0px; width: auto" id="captcha" name="captcha" required></div>
                    <br>
                    <input type="file" class="form-control" id="file" name="userfile" accept=".jpg,.gif,.png,.txt" onchange="check(this)">
                    <br>
                    <textarea class="form-control" placeholder="Оставьте комментарий здесь" id="textarea" name="textarea" required></textarea>
                    <br>
                    <input type="submit" class="form-control" onclick="fl()">
                </div>
                </form>
            </div>
            
</body>
</html>
```

<h3>Файл create/script.php</h3>

```php
<?php

if (isset($_POST['g-recaptcha-response'])) $captcha_response = $_POST['g-recaptcha-response'];
else die('На форме нет капчи! Обратитесь к администратору!');
$url = 'https://www.google.com/recaptcha/api/siteverify';
$params = [
	'secret' => '6LetvG4jAAAAABmlA6YXWqfgwHAj-qZhL85MOur3',
	'response' => $captcha_response,
	'remoteip' => $_SERVER['REMOTE_ADDR']
];

$ch = curl_init($url);
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS, $params);
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, 1);
curl_setopt($ch, CURLOPT_HEADER, 0);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);

$response = curl_exec($ch);
if (!empty($response)) $decoded_response = json_decode($response);

$success = false;

if ($decoded_response && $decoded_response->success) {
	$success = $decoded_response->success;
}

$result = $success ? 'Капча пройдена успешно!' : 'Неверная капча!';
if ($result == 'Капча пройдена успешно!') {
	$servername = "localhost";
	$username = "root";
	$password = "";
	$dbname = "messages";

	$conn = new mysqli($servername, $username, $password);
	if ($conn->connect_error) {
		die("Ошибка в подключении: " . $conn->connect_error);
	}

	$conn = new mysqli($servername, $username, $password, $dbname);

	$name = strip_tags($_POST["name"]);
	$email = strip_tags($_POST["email"]);
	if (!empty($_POST["homepage"])) $homepage = strip_tags($_POST["homepage"]);
	else $homepage = "";
	if ($_FILES["userfile"]["name"] != "") {
		$filename = $_FILES["userfile"]["tmp_name"];
		if (strpos($_FILES["userfile"]["name"], ".txt") == false) {
			if($_FILES["userfile"]["type"] == "image/jpeg") $type = ".jpg";
			if($_FILES["userfile"]["type"] == "image/png") $type = ".png";
			if($_FILES["userfile"]["type"] == "image/gif") $type = ".gif";
			$path = time().$type;
			move_uploaded_file($filename,"../assets/images/".$path);
		}
		else{
			$path = time().".txt";
			move_uploaded_file($filename,"../assets/text/".$path);
		}
	} else $path= "";
	$textarea = strip_tags($_POST["textarea"]);
	$IP = $_SERVER['REMOTE_ADDR'];
	$temp = get_browser(null, true);
	$Browser = $_SERVER['HTTP_USER_AGENT'];
	$sql = "INSERT INTO `message`(`name`, `email`, `homepage`, `IP`, `Browser`, `text`,`filename`) VALUES ('$name','$email','$homepage','$IP','$Browser','$textarea','$path')";
	$conn->query($sql);

	header('Location: ../messages');
} else {
	header('Location: ./error');
}

```

<h3>Файл messages/index.php</h3>

```php
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-Zenh87qX5JnK2Jl0vWa8Ck2rdkQ2Bzep5IDxbcnCeuOxjzrPF/et3URy9Bv1WTRi" crossorigin="anonymous">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-OERcA2EqjJCMA+/3y+gxIOqMEjwtxJY7qPCqsdltbNJuaOe923+mo//f6V8Qbsw3" crossorigin="anonymous"></script>
    <script src='https://www.google.com/recaptcha/api.js'></script>

    <link rel="stylesheet" href="css/lightbox.css" type="text/css" media="screen" />
    <script type="text/javascript" src="lightbox/prototype.js"></script>
    <script type="text/javascript" src="lightbox/scriptaculous.js?load=effects,builder"></script>
    <script type="text/javascript" src="lightbox/lightbox.js"></script>

    <style>
        body {
            background-image: url("../bg.png");
            background-size: 100% 100%;
            background-repeat: repeat-y;

        }

        table {
            background: linear-gradient(0deg, #7fc7ff, white);
            margin-bottom: 0px;
            text-align: center;
            width: auto;
        }

        tr,
        tbody,
        thead,
        td {
            border: solid 2px black;
            height: 50px;
            padding: 10px;
        }

        td {
            height: 75px;
        }

        a {
            width: 100%;
            height: 50px;
            font-size: 20px;
            text-decoration: none;
            color: black;
        }

        #id {
            width: 3%;
        }

        #name {
            width: 10%;
        }

        #email {
            width: 10%;
        }

        #homepage {
            width: 10%;
        }

        #IP {
            width: 10%;
        }

        #Browser {
            width: 20%;
        }

        #text {
            width: 20%;
        }
        #file{
            width: 350px;
        }
    </style>
    <title>Гостевая книга</title>
</head>

<body class="d-flex flex-row vh-100">
    <div>
        <?php
        $sort_list = array(
            'id_desc'  => '`id` DESC',
            'id_asc'   => '`id`',
            'name_asc'  => '`name`',
            'name_desc' => '`name` DESC',
            'email_asc'   => '`email`',
            'email_desc'  => '`email` DESC',
            'homepage_asc'   => '`homepage`',
            'homepage_desc'  => '`homepage` DESC',
            'IP_asc'   => '`IP`',
            'IP_desc'  => '`IP` DESC',
            'Browser_asc'   => '`Browser`',
            'Browser_desc'  => '`Browser` DESC',
            'text_asc'   => '`text`',
            'text_desc'  => '`text` DESC',
        );

        $sort = @$_GET['sort'];
        if (array_key_exists($sort, $sort_list)) {
            $sort_sql = $sort_list[$sort];
        } else {
            $sort_sql = reset($sort_list);
        }

        $servername = "localhost";
        $username = "root";
        $password = "";
        $dbname = "messages";

        $conn = new mysqli($servername, $username, $password);
        if ($conn->connect_error) {
            die("Ошибка в подключении: " . $conn->connect_error);
        }
        $conn = new mysqli($servername, $username, $password, $dbname);
        $sql = "SELECT * FROM `message` ORDER BY $sort_sql LIMIT 25";
        $result =  $conn->query($sql);
        function sort_link_th($title, $a, $b)
        {
            $sort = @$_GET['sort'];

            if ($sort == $a) {
                return '<a class="active" href="?sort=' . $b . '">' . $title . ' <i>▲</i></a>';
            } elseif ($sort == $b) {
                return '<a class="active" href="?sort=' . $a . '">' . $title . ' <i>▼</i></a>';
            } else {
                return '<a href="?sort=' . $a . '">' . $title . '</a>';
            }
        }
        ?>

        <table>
            <thead>
                <tr>
                    <th id="id"><?php echo sort_link_th('id', 'id_asc', 'id_desc'); ?></th>
                    <th id="name"><?php echo sort_link_th('Имя', 'name_asc', 'name_desc'); ?></th>
                    <th id="email"><?php echo sort_link_th('Почта', 'email_asc', 'email_desc'); ?></th>
                    <th id="homepage"><?php echo sort_link_th('Домашнаяя страница', 'homepage_asc', 'homepage_desc'); ?></th>
                    <th id="homepage"><?php echo sort_link_th('IP', 'IP_asc', 'IP_desc'); ?></th>
                    <th id="homepage"><?php echo sort_link_th('Браузер', 'Browser_asc', 'Browser_desc'); ?></th>
                    <th id="text"><?php echo sort_link_th('Текст', 'text_asc', 'text_desc'); ?></th>
                    <th id="file">Файл</th>
                </tr>
            </thead>
            <tbody>
                <?php foreach ($result as $row) : ?>
                    <tr>
                        <td id="id"><?php echo htmlspecialchars($row['id']); ?></td>
                        <td id="name"><?php echo htmlspecialchars($row['name']); ?></td>
                        <td id="email"><?php echo htmlspecialchars($row['email']); ?></td>
                        <td id="homepage"><?php echo htmlspecialchars($row['homepage']); ?></td>
                        <td id="IP"><?php echo htmlspecialchars($row['IP']); ?></td>
                        <td id="Browser"><?php echo htmlspecialchars($row['Browser']); ?></td>
                        <td id="text"><?php echo htmlspecialchars($row['text']); ?></td>
                            <?php

                            if ($row['filename'] != "") {
                                if (strpos($row['filename'], ".txt") == true) {
                                    $path = "../assets/text/".$row['filename'];
                                    echo "<td id=\"file\"><a href=\"" . $path . "\" target=\"_blank\" class=\"btn btn-primary btn-lg active\" role=\"button\">Файл</a></td>";
                                } else {
                                    $path = "../assets/images/".$row['filename'];
                                    echo "<td id=\"file\"><a href=\"" . $path . "\" rel=\"lightbox\" title=\"Картинка пользователя " . $row["name"] . "\"><img src=\"" . $path . "\" width=\"320\" height=\"240\"></a></td>";
                                }
                            } else {
                                echo "<td id=\"file\"></td>";
                            }
                            ?>
                    </tr>
                <?php endforeach; ?>
            </tbody>
        </table>

        <a class="btn btn-primary fs-4" href="../" style="width:200px">Меню</a>
    </div>
</body>

</html>
```

<h4>Вывод: Вспомнил PHP.</h4>

