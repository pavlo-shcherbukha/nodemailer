# SEND_EMAIL - тренинговый проект по NODE.JS по отрпавке email  

[Оригинальное описание](https://appdividend-com.cdn.ampproject.org/v/s/appdividend.com/amp/2017/08/11/send-email-in-node-js/?usqp=mq331AQA&amp_js_v=0.1#referrer=https%3A%2F%2Fwww.google.com&amp_tf=%D0%94%D0%B6%D0%B5%D1%80%D0%B5%D0%BB%D0%BE%3A%20%251%24s&ampshare=https%3A%2F%2Fappdividend.com%2F2017%2F08%2F11%2Fsend-email-in-node-js%2F)

[ Оригинальный репозиторий с github ](https://github.com/KrunalLathiya/nodemailer?ez_cid=CLIENT_ID)


[Some git help](https://github.com/TSM-08/SEND_EMAIL/blob/master/doc/git-help.md)

[some Node.js help](https://github.com/TSM-08/SEND_EMAIL/blob/master/doc/node-help.md)

[markdown-cheatsheet-online](https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf)

[github mastering-markdown](https://guides.github.com/features/mastering-markdown/)


Change setting on ypur account
1. enter in google account

 [pic1](https://github.com/TSM-08/SEND_EMAIL/blob/master/doc/pic/pic1.png)

 
2. set up 2-step verification

 [pic2](https://github.com/TSM-08/SEND_EMAIL/blob/master/doc/pic/pic2.png)

3. generate app password

 [pic2](https://github.com/TSM-08/SEND_EMAIL/blob/master/doc/pic/pic2.png)
this password will be used as a login


<p align="center">
  <img src="https://github.com/TSM-08/SEND_EMAIL/blob/master/doc/pic/pic2.png" width="350" title="hover text">
  <img src="https://github.com/TSM-08/SEND_EMAIL/blob/master/doc/pic/pic2.png" width="350" alt="accessibility text">
</p>

3. correct your mail setting
```js

      let transporter = nodeMailer.createTransport({
          host: 'smtp.googlemail.com',
          port: 465,
          secure: true,
          auth: {
              user: 'your-emeil@gmail.com',
              pass: 'your app password'
      });


```

4. correct your sender name
```js

      let mailOptions = {
          from: '"your-sender name" <your-emeil@gmail.com>', // sender address
          to: req.body.to, // list of receivers
          subject: req.body.subject, // Subject line
          text: req.body.body, // plain text body
          html: '<b>NodeJS Email Tutorial</b>' // html body


```
