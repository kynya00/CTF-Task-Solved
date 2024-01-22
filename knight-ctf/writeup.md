# Gain Access 1

## Описание
```
 The web challenges are very much similar to real life application bugs. 
 This is going to be a series of Gain Access with 3 challenges unlocks upon solving one by one. 
 By solving these challenges, you'll gain a practical knowledge of Authentication Bypass Vulnerabilites as well as business logic error. 
 The only difference is you'll not get any bounty but you'll get flags. Give it a try. 
 And keep in mind, Don't make it hard, keep it simple. 
 All the best. Solve the challenges & be a cyber knight.
```
## Writeup
1. Нас встречает форма авторизации.

![1](https://github.com/kynya00/CTF-Task-Solved/assets/101522045/a481919f-0e98-4b58-88e9-4b9f7a6840d0)

2. Посетим веб-сайт и посмотрим исходный код, найдем здесь "случайно" оставленную почту.

![2](https://github.com/kynya00/CTF-Task-Solved/assets/101522045/7d3be406-3141-465d-9568-c61d166d2a01)

3. Проверим роботов (база, /robots.txt), видим скрытую страницу /r3s3t_pa5s.php

![3](https://github.com/kynya00/CTF-Task-Solved/assets/101522045/ef5eace4-8c76-4bda-9601-91f1a44f8638)

4. Посетим данную страницу, но, к сожалению, у нас нет токена.

![4](https://github.com/kynya00/CTF-Task-Solved/assets/101522045/ee2eaa59-2d79-4f56-b6d5-40eb8c33eb30)

5. Зная логин (почту) из первого пункта, попробуем войти, используя стандартные пароли, но, к сожалению, неудачно.
![5](https://github.com/kynya00/CTF-Task-Solved/assets/101522045/69c07960-e9d4-40b8-be45-697aba058eff)

6. Попробуем сбросить пароль от этой учетной записи.

![6](https://github.com/kynya00/CTF-Task-Solved/assets/101522045/21711709-474d-442a-aebe-0b3ab5f41ccb)

7. При сбрасывании пароля, попробуем перехватить запрос с помощью Burp.

![10](https://github.com/kynya00/CTF-Task-Solved/assets/101522045/9e188759-ca03-47e1-aa33-dca298f02a8c)


8. Ага, при сбрасывании пароля в Хедерах был передан небезопасно токен, попробуем сбросить пароль /r3s3t_pa5s.php, передавая токен следующим образом: http://ip/r3s3t_pa5s.php?token=*token*

![8](https://github.com/kynya00/CTF-Task-Solved/assets/101522045/03733009-2cb1-45da-bcd6-18adbc42eb6e)

9. Ликаем флажочек и бежим его сдавать.

![9](https://github.com/kynya00/CTF-Task-Solved/assets/101522045/0a386c50-8e53-47c1-b1fd-3212dd2052c3)
