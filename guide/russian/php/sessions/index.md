---
title: Sessions
localeTitle: сессии
---
## сессии

Сессии - это функция PHP, которая позволяет хранить сервер данных на стороне пользователя. Когда сеанс настроен, устанавливается cookie-браузер браузера, который идентифицирует пользователя на PHP, поэтому PHP знает, к каким переменным на стороне сервера требуется доступ.

### Начало сеанса

На каждой странице, к которой вы хотите получить доступ к сеансу, необходимо запустить (или загрузить) сеанс. Для этого запустите функцию `session_start()` которая загружает систему сеансов PHP.

```PHP
<?php 
 session_start(); 
```

Обратите внимание, что при использовании сеансов на основе файлов cookie необходимо вызывать session\_start () перед выводом чего-либо в браузер. все остальное приведет к ошибке.

### Доступ и установка данных на сеансе

Переменная `$_SESSION['key']` - это особый тип массива (с помощью cookie браузера для определения того, для какой сессии требуется доступ).

В приведенном ниже примере вы видите, что тема выбора пользователя выбрана для темы номер один.

```PHP
<?php 
 session_start(); 
 $_SESSION['themechoice'] = 1; 
```

Доступ к переменной сеанса аналогичен настройке. Просто включите переменную, в которой она должна быть доступна. Например, повторите это, как показано в приведенном ниже примере кода.

```PHP
<?php 
 session_start(); 
 echo $_SESSION['themechoice']; 
```

### Удаление сеанса

Чтобы удалить сеанс из системы, запустите следующий код PHP. Он отключит переменные сеанса и удалит их из системы.

```PHP
<?php 
 session_unset(); 
 session_destroy(); 
```

### Сессии временны

Важно не рассматривать сеанс как постоянное хранилище. Они время от времени очищаются разработчиком, когда приложение перемещается на новый хост-сервер, самим приложением (например, кнопкой выхода) и даже во время обслуживания сервера. Для долговременного хранения данных обязательно используйте базу данных.

### Безопасность

Последнее, но не менее важное, важно безопасно использовать сеансы php. Прочтите нашу статью о [приобретении идентификатора сеанса](/php/security/session-identifier-acquirement) и [захвате](/php/security/session-identifier-acquirement) [сеанса](/php/security/session-hijacking) для получения дополнительной информации.

#### Дополнительная информация:

*   [Руководство пользователя php.net](https://secure.php.net/manual/en/book.session.php)