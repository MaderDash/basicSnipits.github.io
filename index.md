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
// You will need a pull DOWN resistor conected to the button for this code to work.
byte buttonPin = 3;  // this is where your button is conected.
bool setState = false; // This varable is the state we are switching.

void setup(){
  pinMode(buttonPin, INPUT);  // Sets the input for the button
  pinMode(13, OUTPUT);         // Sets pin 13 to output for the onboard led on the uno board.
}

void loop() {
    /* This first if statment triggers when the button is pulled high.
        If the button is held, this will not keep cycleing, it will only work  one time.
    */
  if (digitalRead(buttonPin) == HIGH && lockout == false) {
  setState = !setState;
  lockout = true;
  delay(50);
  }
  /*  This if statment waits untill you release the button
       Then It resets the button for the next press.
       There are 50 miliseccond delays just to keep things stable.
  */
  if (digitalRead(buttonPin) == LOW && lockout == true) {
    lockout = false;
    delay(50);
  }
  // This is where we change the state of the pin, baised off of the state of the varable.
  digitalWrite(13, setState);
}

```