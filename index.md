## Welcome to the Snip it page.


### Markdown

Arduino community is gathering a bunch of common snip-its of code together, so you dont haft to.

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/MaderDash/basicSnipits.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Toggle Momentary switch 🔘

```
byte buttonPin = 3;
bool setState = false;

void setup(){
  pinMode(buttonPin, INPUT);
  pinMode(13, OUTPUT);
}

void loop() {
  if (digitalRead(buttonPin) == HIGH && lockout == false) {
  setState = !setState;
  lockout = true;
  delay(50);
  }
  if (digitalRead(buttonPin) == LOW && lockout == true) {
    lockout = false;
    delay(50);
  }
  digitalWrite(13, setState);
}

```