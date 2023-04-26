# CodeColosseumDesktop

This app in intended to be used as Graphic client for Code Colosseum     
https://github.com/dariost/CodeColosseum

## Known bugs
- Missing newline character for ("on", "data") callback on js api: an issue has been opened on the Tauri repo, a fix to this bug is currently undergoing review.
- Executables can only be successfully launched when there are no space characters in the path: the behavior appears to be inconsistent under different operative systems, it looks like this behavior can be traced back to an incorrect implementation of the Tauri API, solving this bug might require opening a new issue on the Tauri repo.
- The StdErr is currently shown just below the messages chat inside the game page, it would be appropriate to find a better way to show these error messages on the UI.

## Functionalities



## Install

TODO: Download a binary release

## Setup Development Environment 
The project by default is intended to be used with Visual Studio Code.
The app is a client and in order to be used it requires to connect to instance of CodeColosseum server (cocod).

Dependencies:
- Rust
- NodeJS
- TypeScript
- Angular
- Tauri
- CodeColosseum 

- Rust
```bash
  sudo apt update
  sudo apt install libwebkit2gtk-4.0-dev \
      build-essential \
      curl \
      wget \
      libssl-dev \
      libgtk-3-dev \
      libayatana-appindicator3-dev \
      librsvg2-dev
  curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

- NodeJS
```bash
  curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
  source ~/.bashrc
  nvm list-remote
  nvm install --lts
```
  
- TypeScript
```bash
  npm install -g typescript
```

Angular
```bash
  npm install -g @angular/cli
```

CodeColosseum ( for the server ) 
```bash
  sudo apt install cargo
  source install_coco.sh
  ./cocod
```


## Running the app

From the main folder of the app ( same location as package.json )     

Install node dependencies (run once):     
```bash
yarn install
```

To run the actuall app during development ( it autoreload when files are changed )     
Then navigate to `http://localhost:4200/`
```bash
yarn tauri dev
```

To build a "production" version, the build artifacts will be stored in the `dist/` directory and the tauri builded version will be located in `src-tauri/target` folder.
```bash
yarn tauri build
```

__This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 13.3.5.__
