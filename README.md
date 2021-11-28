<p align="center"><img align="center" style="width:320px" src="https://finapp.ilko.me/icon.png"/></p><br/>

# Open source finance application
Finapp helps you to control personal finances easily and efficiently.

# 🚀 Features
- Works offline on all devices (Service Worker): you can see all your data. Create, edit and delete transactions.
- Instant synchronisation between all device (Firebase).
- Optimised for mobile and PC.
- Themes: dark and white.
- Support multiple currencies with auto conversion.

# 🦄 Technologies
- Vue
- Nuxt
- Stylus
- Pug
- Firebase

# 📦 Setup

### Project setup
``` bash
# clone the repo
$ git clone https://github.com/ilkome/finapp.git finapp

# go into app's directory
$ cd finapp

# install app's dependencies
$ npm install
```

### Firebase setup
- Create a Firebase project in the [Firebase console](https://console.firebase.google.com/)
- Go to the Authentication tab and enable Google authentication.
- Go to the Database tab and enable Firestore.
- Select Realtime Database and go to Rules tab.
- Change rules to:
``` javascript
{
  "rules": {
    "users": {
      "$uid": {
        ".read": "auth != null && auth.uid == $uid",
        ".write": "auth != null && auth.uid == $uid"
      }
    },
    "currencies": {
      ".read": "auth != null",
      ".write": "auth != null"
    },
    "users-info": {
      "$uid": {
        ".read": "auth != null && auth.uid == $uid",
        ".write": "auth != null && auth.uid == $uid"
      }
    }
  }
}
```
- Go to the Project Overview and click Add Firebase to your web app.
- You need to replace config in app's directory `services/firebaseConfig.js` with your config.
``` bash
apiKey: 'YOUR_CONFIG',
authDomain: 'YOUR_CONFIG',
databaseURL: 'YOUR_CONFIG',
projectId: 'YOUR_CONFIG',
storageBucket: 'YOUR_CONFIG',
messagingSenderId: 'YOUR_CONFIG'
```


## Development

#### Compiles and hot-reloads
``` bash
$ npm run dev
```

## Production
#### Compiles and minifies for production
``` bash
$ npm run build
```

## Upload to server
You can add your FTP config in app's directory `ftp.config.js`

``` bash
# upload all files from dist folder
$ npm run upload

# upload only css, js, html files from dist folder
$ npm run upload-min
```

# 🤪 Stay In Touch
I would like to speak with you about Finapp. I'm looking for awesome projects.

# 📄 License
[MIT License](https://github.com/ilkome/finapp/blob/main/LICENSE)
