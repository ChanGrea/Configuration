# Ubuntu 환경 설정

## IDE

---

### VSCode

#### 설치

- [https://code.visualstudio.com/](https://code.visualstudio.com/)

#### 설정

- Extension 설치
  - [Settings Sync](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync)

### Intellij

#### 설치

- [https://www.jetbrains.com/ko-kr/idea/download/#section=linux](https://www.jetbrains.com/ko-kr/idea/download/#section=linux)

## Tool

---

### Typora

#### 설치

- [https://typora.io/#linux](https://typora.io/#linux)

  ```bash
  # or run:
  # sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BA300B7755AFCFAE
  wget -qO - https://typora.io/linux/public-key.asc | sudo apt-key add -
  
  # add Typora's repository
  sudo add-apt-repository 'deb https://typora.io/linux ./'
  sudo apt-get update
  
  # install typora
  sudo apt-get install typora
  ```

#### 테마 적용

- [Quartz](http://theme.typora.io/theme/Quartz/) 에서 설치
- **theme** 폴더 안에 있는 **quartz** 폴더와 **css 파일들** 복사
- Typora "File" - "Preference"
  - Appearance - Open Theme Folder
  - 폴더 안에 복사한 파일들 Paste

### Git

```bash
sudo apt install git
```

### GitKraken

#### 설치

- [https://www.gitkraken.com/](https://www.gitkraken.com/)

### Node

#### NVM 설치

- 관련 패키지 설치

  ```bash
  sudo apt-get install build-essential libssl-dev
  ```

- nvm 설치

  ```bash
  # curl 설치
  sudo apt-get install curl
  
  curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
  ```

- bashrc를 통해 적용

  ```bash
  source ~/.bashrc
  ```

- nvm 설치 확인

  ```bash
  nvm --version
  ```

#### Node.js 설치

- Node version 확인

  ```bash
  nvm ls-remote
  ```

- Node 설치 (LTS 설치)

  ```bash
  nvm install <version>
  ```

- 설치 확인

  ```bash
  nvm ls
  node --version
  npm --version
  ```

  - default 확인

### Yarn

- 패키지 관리 도구
- React.js에서 사용할 용도

#### 설치

```bash
npm install -g yarn
```

#### 확인

```bash
yarn --version
```

## 기타

---

### Font

#### D2coding 설치

- 설치
  - [https://github.com/naver/d2codingfont](https://github.com/naver/d2codingfont)

#### Terminal 적용

- "Edit" - "Preference" - "profiles" 탭
  - "New"로 생성
  - Custom font 체크 후 지정

### zsh

#### 설치

```bash
sudo apt-get install zsh
```

#### 설치 확인 및 적용

```bash
# 설치 확인
zsh --version

# 적용(기본 쉘 변경)
chsh -s /usr/bin/zsh
```

### oh-my-zsh

#### 설치

```bash
# curl 이용
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

# wget 이용
sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
```

#### 테마 변경

- [테마 확인](https://github.com/robbyrussell/oh-my-zsh/wiki/External-themes)

- ```bash
  vi ~/.zshrc
  
  # THEME="rubbyrussell" 부분을
  # THEHE="<변경하고 싶은 테마 이름>" 으로 바꾸고 저장
  
  source ~/.zshrc
  ```

  