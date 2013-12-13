<h1>Smile Pack</h1>

<p>приложение на js для удобной передачи смайликов на форумы и сайты с поддержкой BBCode.</p>

<hr>

<p>В приложении задействованы JS API:
  <br>
	<a href="http://caniuse.com/#feat=x-doc-messaging">Cross-document messaging</a>
	<br>
	<a href="http://caniuse.com/#feat=namevalue-storage">WebStorage</a>
	<br>
	<a href="http://caniuse.com/#feat=json">JSON parsing</a>
</p>

<h2>Файлы приложения:</h2>

<h3>сайт:</h3>
<dl>
	<dt>index.html</dt>
		<dd>Главная и единственная страничка приложения. Подгружает стили и скрипт программы.</dd>
	<dt>SmilePack.js</dt>
		<dd>
			Главный скрипт приложения. В нем происходят основные рабочие процессы:
			создание пользовательских наборов из смайликов,
			кеширование, AJAX-запросы на сервер, работа с WebStorage и т.д.
		</dd>
	<dt>style.css</dt>
		<dd>Стили приложения для full-версии сайта. Нагружает CPU, поэтому рекомендован для мощных ПК.</dd>
	<dt>style_lite.css</dt>
		<dd>
			Стили приложения для lite-версии сайта. Сделан специально для маломощный ПК.
			Результаты тестирования показали, что gif-анимация и некоторые свойства css
			(box-shadow, border-radius, transition и т.д.)
			создают серьезную нагрузку на процессор пользователя.
			Данные стили позволяют снизить нагрузку более, чем в 4 раза (safari).
			Переключить версии можно под копирайтом приложения.
		</dd>
</dl>

<h3>сервер:</h3>
<dl>
	<dt>check.php</dt>
		<dd>
			Обрабатывает запрос от клиента. Проверяет запрашиваемую директорию на наличие gif-анимации,
			собирает информацию в JSON. Запрашивается единственный раз (при первой загрузке),
			при повторном запросе JSON берется из локального хранилища браузера пользователя.
		</dd>
</dl>

<h3>букмарклет:</h3>
<dl>
	<dt>sp.html</dt>
		<dd>HTML-разметка фрейма на стороннем ресурсе при вызове букмарклета.</dd>
	<dt>sp.css</dt>
		<dd>Стили для букмарклета.</dd>
	<dt>bookmarklet.js</dt>
		<dd>
			Скрипт на стороне букмарклета. На основе созданных директорий заполняет его содержимое.
			Отправляет сообщение скрипту message.js с информацией о картинке.
		</dd>
	<dt>message.js</dt>
		<dd>Скрипт на стороннем сайте. Получает сообщение из букмарклета и вставляет BBCode в указанное место.</dd>
</dl>

<h2>Как это работает:</h2>

<p>
	Пользователь составляет из понравившихся изображений собственные наборы (директории).
	На стороннем сайте открывает букмарклет, выбирает нужную картинку кликая на нее.
	Если следующий клик приходится на текстовую область (textarea или input c типом text),
	то в этой области создается bbCode с ссылкой на эту картинку. <br>
	Посмотреть как работает приложение можно на <a href="http://youtu.be/yKRrWsKcD7s">видео</a>.
</p>

<hr>

<p>
	&copy; 2012 lgick. Email: <a href="mailto:lgick@yandex.ru">lgick@yandex.ru</a><br>
</p>
