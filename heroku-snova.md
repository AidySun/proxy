# Snova on Heroku

Reference: https://waylau.com/heroku-snova-c4-cross-wall/
  - 服务端https://snova.googlecode.com/files/snova-c4-java-server-0.22.0.war
  - 客户端https://snova.googlecode.com/files/gsnova_0.22.1_windows_386.zip

## steps  

```
$ heroku login

$ heroku plugins:install https://github.com/heroku/heroku-deploy

$ heroku apps:create
Creating app... done, ⬢ safe-depths-58500
https://safe-depths-58500.herokuapp.com/ | https://git.heroku.com/safe-depths-58500.git

szh@DESKTOP-VKH73JO C:\Users\szh
$ heroku plugins:install java
Installing plugin java... installed v3.1.1

szh@DESKTOP-VKH73JO C:\Users\szh
$ heroku war:deploy "C:\Users\szh\Downloads\snova-c4-java-server-0.22.0.war" --app bj-ss
Uploading snova-c4-java-server-0.22.0.war
events.js:287
      throw er; // Unhandled 'error' event
      ^

Error: spawn java ENOENT
    at Process.ChildProcess._handle.onexit (internal/child_process.js:267:19)
    at onErrorNT (internal/child_process.js:469:16)
    at processTicksAndRejections (internal/process/task_queues.js:84:21)
Emitted 'error' event on ChildProcess instance at:
    at Process.ChildProcess._handle.onexit (internal/child_process.js:273:12)
    at onErrorNT (internal/child_process.js:469:16)
    at processTicksAndRejections (internal/process/task_queues.js:84:21) {
  errno: 'ENOENT',
  code: 'ENOENT',
  syscall: 'spawn java',
  path: 'java',
  spawnargs: [
    '-Dheroku.appName=bj-ss',
    '-Xmx1g',
    '-Dheroku.warFile=C:\\Users\\szh\\Downloads\\snova-c4-java-server-0.22.0.war',
    '-jar',
    'C:\\Users\\szh\\AppData\\Local\\heroku\\node_modules\\@heroku-cli\\plugin-java\\lib\\heroku-deploy-complete.jar'
  ]
}


$ heroku plugins:install npm

$ # local install JDK11, Node.js

$ heroku war:deploy snova-c4-java-server-0.22.0.war --app safe-depths-58500
$ heroku open

```

