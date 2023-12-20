# AuthGuard

👷🏻 _Задача нормальной сложности_\
💼 _Часть проекта_

<!--start_statement-->

В приложении есть два типа пользователей:

1. Авторизованный пользователь
2. Гость - не авторизованный пользователь

По доступности для пользователей все маршруты приложения делятся на три группы:

1. Доступные всем пользователям (например, главная страница или страница со списком митапов).
2. Только для гостей (например, страница авторизации и регистрации)
   - Маршрут имеет `meta` свойство `requireGuest`
   - При переходе на такой маршрут пользователя должно перенаправлять на главную страницу `/`
3. Только для авторизованных пользователей:
   - Маршрут имеет `meta` свойство `requireAuth`
   - При переходе на такой маршрут пользователя должно перенаправлять на страницу авторизации `/login`
   - При перенаправлении должен устанавливаться query параметр `from` с путём заблокированной страницы для возврата
     обратна после авторизации (реализовано вами в первой задаче раздела)

Реализуйте [guard](https://router.vuejs.org/guide/advanced/navigation-guards.html) роутера, реализующий это поведение на
основе `meta` параметров маршрутов.

Для проверки авторизации используйте функцию `isAuthenticated` из модуля `services/authService.js`.

_Примечание: вы можете давать маршрутам имена, менять `meta` параметры по своему усмотрению или даже попробовать
реализовать паттерн [middleware](https://markus.oberlehner.net/blog/implementing-a-simple-middleware-with-vue-router/).
Цель - реализация описанного поведения._

<img src="https://i.imgur.com/7yDqPSt.gif" alt="Example" style="max-width: 100%" />
<!--end_statement-->

---

### Инструкция

📝 Для решения задачи отредактируйте файл: `router/index.js`.

🚀 Команда запуска для ручного тестирования: `npm run serve`;\
приложение будет доступно на [http://localhost:8080/05-vue-router/05-AuthGuard/](http://localhost:8080/05-vue-router/05-AuthGuard/).

✅ Доступно автоматическое тестирование: `npm test AuthGuard`.