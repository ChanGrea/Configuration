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

# 쉘 변경 확인
echo $SHELL
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


#### 플러그인 설치

- alias-tips 기능

- autosuggestion 기능

- syntax-highlighting 기능

- ( git은 기본 내장 플러그인이므로 설치 필요없음)

- [https://github.com/zsh-users](https://github.com/zsh-users) 참고

- ```bash
  # move plugin directory
  $ cd ~/.oh-my-zsh/plugins/
  
  # install plugin
  $ git clone https://github.com/djui/alias-tips
  $ git clone https://github.com/zsh-users/zsh-autosuggestions
  $ git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
  ```

#### 플러그인 적용

```bash
$ vi ~/.zshrc

# 플러그인 설정
plugins=( git alias-tips zsh-autosuggestions zsh-syntax-highlighting )


# 맨 끝에 추가
source ~/.oh-my-zsh/plugins/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
source ~/.oh-my-zsh/plugins/zsh-autosuggestions/zsh-autosuggestions.zsh 
```

#### new Line 적용

```bash
# agnoster theme 적용 기준, theme 폴더의 해당 테마 설정 파일 open
vi ~/.oh-my-zsh/themes/agnoster.zsh-theme
```

```markdown
# 아래와 같이 newline 적용
build_prompt() {
  RETVAL=$?
  prompt_status
  prompt_virtualenv
  prompt_context
  prompt_dir
  prompt_git
  prompt_bzr
  prompt_hg
  prompt_newline //이부분을 추가 꼭 순서 지켜서
  prompt_end
}

# 해당 prompt 함수 추가
prompt_newline() {
  if [[ -n $CURRENT_BG ]]; then
    echo -n "%{%k%F{$CURRENT_BG}%}$SEGMENT_SEPARATOR
%{%k%F{blue}%}$SEGMENT_SEPARATOR"
  else
    echo -n "%{%k%}"
  fi

  echo -n "%{%f%}"
  CURRENT_BG=''
}
```



