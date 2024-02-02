# mega-increment README

Mega-increment extension is intended to ease parallel independent incrementations and decrementations in various strings. It can be used in writing code for lists, enums, arrays, tests, html and xml tags, csv files, data base examples and tests, date-time iterations, hexadecimal and binary register allocations and many other uses.

- `Basic` functionality is available in the **editor** tabs and `advanced options` are implemented in a separate **GUI** tab.
- **Editor** supports only `single line mode` (and cursor has `to stay on line` from which commands are called).
- **GUI** supports `multiline`, changing line, `interactivity`, `exports` and other advanced optons.

- Editor:
![howitworks](/media/basic02c.gif)

- GUI Advanced Increment:
![howitworks](/media/gui-gif1.gif)

There are also example videos on YouTube for [editor](https://youtu.be/URxZXJn2n1w) and [GUI Advanced Increment](https://youtu.be/YPACNYr_03A).

If you have found a `bug` or other issue or you have `feature request` please write here: https://github.com/vladanan/mega-increment/issues  

**If you want to `donate and support` further development**: https://paypal.me/vladanandjelkovic  



<h2 id="Contents">Contents</h2>

[Shortcuts](#Shortcuts)  
[How it works](#Howitworks)  
[Example with numbers](#Examplewithnumbers)  
[Date, time](#Datetime)  
[Units and decimal point](#Unitsanddecimalpoint)  
[Simple, random, crypto](#Simplerandomcrypto)  
[Hex and binary](#Hexandbinary)  
[Overlapping selections and deleting all selections](#Overlappingselectionsanddeletingallselections)  
[Enums and lists](#Enumsandlists)  
[GUI for Advanced Increment](#GUIforAdvancedIncrement)  
[Continuous and ranged enum variants](#Continuousandrangedenumvariants)  
[Public API](#PublicAPI)  
[Settings](#Settings)  
[FAQ](#FAQ)  
[Known Issues](#KnownIssues)  
[Licence](#Licence)  




<h2 id="Shortcuts">Shortcuts</h2>


There are four simple commands which are used in editor:
  - when some part of line is selected user can **add** it for incrementation (and then select type and stepping)
  - start **incrementing** by adding lines below the line where the cursor is
  - **delete** all selected parts for incrementation
  - start **Advanced GUI** mode

All commands are available in VSCode standard Command Palette (Linux/Windows: Ctrl+Shift+P / F1, Mac: ⇧⌘P / F1).  
***Tip:*** *By typing '**mega**' in Command Palette you get all of them quickly*

| Command Palette name | Default shortcut* | Mac shortcut* | Shortcuts other devs use |
| --- | ----------- | -- | -- |
| `Mega: Add selection for increment` | Ctrl + Alt + 8 | ⌥ ⌘ 8 | Ctrl+Shift+8, Ctrl+Alt+J, Ctrl+Shift+Q  |
| `Mega: Do increment` | Ctrl + Alt + U | ⌥ ⌘ U | Ctrl+Shift+Insert, Ctrl+Shift+U |
| `Mega: Clear all selections` | Ctrl + Alt + 0 | ⌥ ⌘ 9 | Ctrl+Shift+Delete, Ctrl+Alt+X |
| `Mega: Advanced increment` | Ctrl + Alt + 9 | ⇧ ⌥ 0 | Ctrl+Shift+9, Ctrl+Shift+4, Ctrl+Alt+7 |

\* *Shortcuts can be changed in VSCode settings.*  
\* *On Macs ⌥ ⌘ 0 is by default used for Toggle editor layout.*  
\* *On Windows 10 with default shortcut for add selection Ctrl+Alt+8 an apostrophe is written and selected text is deleted. After several shortcut combinations tested Ctrl+Alt+J works well.*  

[Back to Contents](#Contents)




<h2 id="Howitworks">How it works</h2>


1) In the editor select part of text on line.
2) Then issue **add** command (Ctrl+Alt+8) to add it for incrementing.
3) Choose the type of text which indicates to the incrementer how to treat selected text (available type options depend on what is selected).

    ![howitworks](/media/howitworks123.png)

4) Choose stepping for incrementation, default steppiing is set to **1**:

    ![howitworks](/media/howitworks4a.png)

    After entering your desired stepping and hitting Enter you will get notification about new selection added and also Status bar info about it:

    ![howitworks](/media/howitworks4b.png)

    You can also click on Status info bar and get more information about current selections.

5) Issue command for **increment** (Ctrl+Alt+U) 9 times and then below the active line new lines will appear with selected part incremented.  

    ![howitworks](/media/howitworks5.png)

6) To delete current selection(s) hit Ctrl+Alt+0.

    ![howitworks](/media/howitworks6.png)

**That's it!**  

Let's see that in motion:

![howitworks](/media/basic02c.gif)


[Back to Contents](#Contents)





<h2 id="Examplewithnumbers">Example with numbers</h2>


- If we want this `li`:  
`<li style="background-color: rgb(200, 69, 98); width: 120px;">Increment test</li>`  
  <li style="background-color: rgb(200, 69, 98); width: 120px;">Increment test</li>
- to be repeatedly changed in a way to gradually **decrease red** color and at the same time to **increase width** of element.
- For that we would:
  + **select** `200`, **add** it for increment by Ctrl+Alt+8, choose **number** type, input **stepping** -20
  + then **select** `120`, **add** it to increment, choose **number** type, input **stepping** 20
  + if we then **increment** that for eight times by Ctrl+Alt+U we should get this:  
    ```html
    <li style="background-color: rgb(200, 69, 98); width: 120px;">Increment test</li>
    <li style="background-color: rgb(180, 69, 98); width: 140px;">Increment test</li>
    <li style="background-color: rgb(160, 69, 98); width: 160px;">Increment test</li>
    <li style="background-color: rgb(140, 69, 98); width: 180px;">Increment test</li>
    <li style="background-color: rgb(120, 69, 98); width: 200px;">Increment test</li>
    <li style="background-color: rgb(100, 69, 98); width: 220px;">Increment test</li>
    <li style="background-color: rgb(80, 69, 98); width: 240px;">Increment test</li>
    <li style="background-color: rgb(60, 69, 98); width: 260px;">Increment test</li>
    <li style="background-color: rgb(40, 69, 98); width: 280px;">Increment test</li>
    ```

  + Lets see that in real:  
    ![example1](/media/example1a.png)  
    ![example1](/media/example1b.png)

- Remember:
  + When you want to **delete** chosen selection(s) and start over again then issue **clear** command (Ctrl+Alt+0).
  + If you want to try the same thing in Advanced GUI issue **advanced increment** command (Ctrl+alt+9).

- If you use decimal stepping on integer numbers i.e. inputting stepping of 0.333333 they will not turn in to floating point but instead they will be incremented every third time. If you input stepping of 0.25 increment will occur every fourth time, for 0.2 fifth and so on. This `fractional stepping` is available also for simple, date, time and enums.
- Numbers with floating point are recognized by decimal point, so if you want 5 to be incremented by 0.2 you should write it as 2.0.

[Back to Contents](#Contents)





<h2 id="Datetime">Date, time</h2>


- Lets say that we need alarms fetched from translation JSON but from every second day and ten minutes earlier. We start with this:
```javascript
const alarms: Alarm[] = [
    { day: t('alarm.items.day.2024-01-15'), time: t('alarm.items.time.13:00:00') },
];
```
- Select day part `2024-01-15`, add, choose `dateISO` type, input stepping 2
- Select time part `13:00:00`, add, choose `timeISO` type, input stepping -600 (10min = 600sec)
- Hit increment several times and we get this:
```javascript
const alarms: Alarm[] = [
	{ day: t('alarm.items.day.2024-01-15'), time: t('alarm.items.time.13:00:00') },
	{ day: t('alarm.items.day.2024-01-17'), time: t('alarm.items.time.12:50:00') },
	{ day: t('alarm.items.day.2024-01-19'), time: t('alarm.items.time.12:40:00') },
	{ day: t('alarm.items.day.2024-01-21'), time: t('alarm.items.time.12:30:00') },
	{ day: t('alarm.items.day.2024-01-23'), time: t('alarm.items.time.12:20:00') },
	{ day: t('alarm.items.day.2024-01-25'), time: t('alarm.items.time.12:10:00') },
	{ day: t('alarm.items.day.2024-01-27'), time: t('alarm.items.time.12:00:00') },
	{ day: t('alarm.items.day.2024-01-29'), time: t('alarm.items.time.11:50:00') },
	{ day: t('alarm.items.day.2024-01-31'), time: t('alarm.items.time.11:40:00') },
	{ day: t('alarm.items.day.2024-02-02'), time: t('alarm.items.time.11:30:00') },
];
```
- For now `timeISO` is without milliseconds.
+ **dateISO**: date part from ISO full date string
+ **timeISO**: time part without millisecond from ISO full date string  
***Tip:*** *Date: If you want to increase only months then don't increase days by 30 because not all months have 30 days. Better select only month and increment by appropriate stepping.*  
***Tip:*** *Time: To increase seconds stepping by 1-59, for minutes stepping: min\*60, for hours stepping: hours\*3600.*
- If you use decimal stepping on date and time i.e. inputting stepping of 0.333333 they will be incremented every third time. If you input stepping of 0.25 increment will occur every fourth time, for 0.2 fifth and so on. This `fractional stepping` is available also for types: simple, integer numbers and enums.
- **Some other date and time formats will soon be implemented in extension.**

[Back to Contents](#Contents)




<h2 id="Unitsanddecimalpoint">Units and decimal point</h2>


- What if we need shipping table with increasing weights by 12.6kg and decreasing price by $0.6 for bulk transport?
```html
<table>
<tr><td>Below 12.5kg</td><td>$2.00/kg</td></tr>
<tr><td>From 12.5kg to 25kg</td><td>$1.94/kg</td></tr>
<tr><td>Above 88kg</td><td>$1.50/kg</td></tr>
</table>
```
- We increment `12.5` with stepping 12.6, `25` by stepping 12.6 and `1.94` by stepping -0.06 and we get:
```html
<tr><td>From 12.5kg to 25kg</td><td>$1.94/kg</td></tr>
<tr><td>From 25.1kg to 37.6kg</td><td>$1.88/kg</td></tr>
<tr><td>From 37.7kg to 50.2kg</td><td>$1.82/kg</td></tr>
<tr><td>From 50.3kg to 62.8kg</td><td>$1.76/kg</td></tr>
<tr><td>From 62.9kg to 75.4kg</td><td>$1.70/kg</td></tr>
<tr><td>From 75.5kg to 88kg</td><td>$1.64/kg</td></tr>
```
<table>
<tr><td>Below 12.5kg</td><td>$2.00/kg</td></tr>
<tr><td>From 12.5kg to 25kg</td><td>$1.94/kg</td></tr>
<tr><td>From 25.1kg to 37.6kg</td><td>$1.88/kg</td></tr>
<tr><td>From 37.7kg to 50.2kg</td><td>$1.82/kg</td></tr>
<tr><td>From 50.3kg to 62.8kg</td><td>$1.76/kg</td></tr>
<tr><td>From 62.9kg to 75.4kg</td><td>$1.70/kg</td></tr>
<tr><td>From 75.5kg to 88kg</td><td>$1.64/kg</td></tr>
<tr><td>Above 88kg</td><td>$1.50/kg</td></tr>
</table>

[Back to Contents](#Contents)




<h2 id="Simplerandomcrypto">Simple, random, crypto</h2>


- Maybe you need to increase individual characters, get random or safe crypto values?

```javascript
const autoTokens: Token[] = [
    { subject: 'abcd', key: 'stupid_admin', crypto_pass: '12345678901234567890'},
];
```
- For `abcd` choose type simple and stepping 1, for `stupid_admin` choose type random, for '12345678901234567890' choose type crypto. No need for stepping for random and crypto. If we increment this several times we get something like this:
```javascript
const autoTokens: Token[] = [
  { subject: 'abcd', key: 'stupid_admin', crypto_pass:'12345678901234567890'},
  { subject: 'bcde', key: 'Iz_WnRfty+aC', crypto_pass:'7875368010268182393'},
  { subject: 'cdef', key: '&lt;!GQ)&gt;aR,F.y', crypto_pass:'4163091229532004722'},
  { subject: 'defg', key: '/iz)iB&#39;nJ2@z', crypto_pass:'4212026588723949856'},
  { subject: 'efgh', key: 'Sx]dz-/6f#&#39;a', crypto_pass:'16251594422145675523'},
  { subject: 'fghi', key: '0=nlwnh#x*)m', crypto_pass:'15652820121626408202'},
  { subject: 'ghij', key: ',fI7)nvBNi2D', crypto_pass:'16875909354991980776'},
  { subject: 'hijk', key: 'siCfWN:j^y\;', crypto_pass:'10664457782404241384'},
  { subject: 'ijkl', key: 'I%~VHGDW4Yo$', crypto_pass:'10809599484200095278'},
  { subject: 'jklm', key: 'p(yb!~KfhtN^', crypto_pass:'13851775674538229405'},
  { subject: 'klmn', key: 'S\PVVc4B{J?h', crypto_pass:'17372568455703339876'},
  { subject: 'lmno', key: 'mt7dZ\zZ=}t?', crypto_pass:'4400204851546143125'},
  { subject: 'mnop', key: 'tceHL8!+&amp;zeK', crypto_pass:'11185827497145895769'},
];
```
- **simple**: any string whom individual characters will be incremented by ASCII order i.e.: abcd, bcde, cdef, defg...  It supports `fractional stepping`.
- **crypto**: integer which will be followed by cryptographically safe array of numbers. Any integer can be selected but result numbers will be in 8/16/32/64bit format depending (not precisely) on number of digits in selected number.
- **random**: any string which will be followed by random printable ASCII characters, not cryptographically safe format.
- For `crypto` and `random` stepping is irrelevant.

[Back to Contents](#Contents)




<h2 id="Hexandbinary">Hex and binary</h2>


- Maybe we need to increment hexadecimal and binary numbers in ASCII?

```html
<h2>Nice hex stars &#x273B; converted to lots of binary digits 0010011100111011</h2>
```
- Increase hex part `273B` **not** `&#x` by type `hex` and stepping 1, then `0010011100111011` by type `binary` and also stepping 1. And we get:
```html
<h2>Nice hex stars &#x273B; converted to lots of binary digits 0010011100111011</h2>
<h2>Nice hex stars &#x273c; converted to lots of binary digits 0010011100111100</h2>
<h2>Nice hex stars &#x273d; converted to lots of binary digits 0010011100111101</h2>
<h2>Nice hex stars &#x273e; converted to lots of binary digits 0010011100111110</h2>
<h2>Nice hex stars &#x273f; converted to lots of binary digits 0010011100111111</h2>
<h2>Nice hex stars &#x2740; converted to lots of binary digits 0010011101000000</h2>
<h2>Nice hex stars &#x2741; converted to lots of binary digits 0010011101000001</h2>
<h2>Nice hex stars &#x2742; converted to lots of binary digits 0010011101000010</h2>
<h2>Nice hex stars &#x2743; converted to lots of binary digits 0010011101000011</h2>
<h2>Nice hex stars &#x2744; converted to lots of binary digits 0010011101000100</h2>
<h2>Nice hex stars &#x2745; converted to lots of binary digits 0010011101000101</h2>
<h2>Nice hex stars &#x2746; converted to lots of binary digits 0010011101000110</h2>
```
    Nice hex stars ✻ converted to lots of binary digits 0010011100111011  
    Nice hex stars ✼ converted to lots of binary digits 0010011100111100  
    Nice hex stars ✽ converted to lots of binary digits 0010011100111101  
    Nice hex stars ✾ converted to lots of binary digits 0010011100111110  
    Nice hex stars ✿ converted to lots of binary digits 0010011100111111  
    Nice hex stars ❀ converted to lots of binary digits 0010011101000000  
    Nice hex stars ❁ converted to lots of binary digits 0010011101000001  
    Nice hex stars ❂ converted to lots of binary digits 0010011101000010  
    Nice hex stars ❃ converted to lots of binary digits 0010011101000011  
    Nice hex stars ❄ converted to lots of binary digits 0010011101000100  
    Nice hex stars ❅ converted to lots of binary digits 0010011101000101  
    Nice hex stars ❆ converted to lots of binary digits 0010011101000110

- Hex is case insensitive and produces lowercase letters.
- Hex & binary are not tested with negative numbers yet, take care of results for signed values.

[Back to Contents](#Contents)





<h2 id="Overlappingselectionsanddeletingallselections">Overlapping selections and deleting all selections</h2>


- If we make selection which overlaps with other then the extension will delete existing selection(s) and ignore new one. In previous example
```html
<h2>Nice hex stars &#x273B; converted to lots of binary digits 0010011100111011</h2>
```
- that can be done by first selecting and adding `Nice` and than `e hex`. Or selecting `Nice` and `stars` and then  `e hex s`. In first case `Nice` would be deleted and in second case `Nice` and `stars` would be deleted.
- When you want to **delete** all chosen selections at once and start over again then issue **clear** command (Ctrl+Alt+0).

[Back to Contents](#Contents)




<h2 id="Enumsandlists">Enums and lists</h2>


- Enums and lists work as JSON arrays which are predefined in extension settings.
- You go to VSCode Settings (Ctrl + ,)(Mac: ⌘ ,) and then find `Mega Increment` section or just type '**mega**' in search field and you get to Mega Increment settings quickly.
- Once there find `Mega-increment: Key Value Pairs`, click `Add Item`, in `Key` field write title for your enum/list, in `Value` field write enum/list in JSON array format, for example for months:
  + Key: months
  + Value: ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"]
  + Click `OK`
  + You have your first enum and you can make lots of them. Also you can edit or delete them.
  + *Depending on OS especially on some Linux systems VSCode might have to be restarted for some settings to take effect.*
- Now with enum set up we can use it. We can step through enums in stepping just like other types. Se we will select every other month by selecting `January`, choose type `enum`, stepping `2` and then increment 5 times:
```javascript
switch (year.selectedMonth) {
  case 'January': console.log("Write here something about this season."); break;
  case 'March': console.log("Write here something about this season."); break;
  case 'May': console.log("Write here something about this season."); break;
  case 'July': console.log("Write here something about this season."); break;
  case 'September': console.log("Write here something about this season."); break;
  case 'November': console.log("Write here something about this season."); break;
  default: break;
}
```
- We do not have to start from the beginning of enum and we also can use negative stepping i.e. we can move through the enum backwards. So in the next example we start from `November` and move backwards 3 steps with stepping -3:
```javascript
switch (year.selectedMonth) {
  case 'November': console.log("Write here anything about this season."); break;
  case 'August': console.log("Write here anything about this season."); break;
  case 'May': console.log("Write here anything about this season."); break;
  case 'February': console.log("Write here anything about this season."); break;
  default: break;
}
```
- There are more interesting and powerful tricks we can do with enums. So lets create two more enums to see how it works. In Mega Increment settings we create two enums:
  + Key: colors, Value: ["blue","salmon","cyan","gray","green"]
  + Key: saturation, Value: ["light","","dark"]
- We start with this:
```html
<p style="color: darkblue" >This text will be interesting to see.</p>
```
- Then we select `dark`, add with type enum, stepping 1. Next we select `blue`, add with type enum, stepping 0.333333, and then increment 15 times. We get this:
```html
<p style="color: lightblue" >This text will be interesting to see.</p>
<p style="color: blue" >This text will be interesting to see.</p>
<p style="color: darkblue" >This text will be interesting to see.</p>
<p style="color: lightsalmon" >This text will be interesting to see.</p>
<p style="color: salmon" >This text will be interesting to see.</p>
<p style="color: darksalmon" >This text will be interesting to see.</p>
<p style="color: lightcyan" >This text will be interesting to see.</p>
<p style="color: cyan" >This text will be interesting to see.</p>
<p style="color: darkcyan" >This text will be interesting to see.</p>
<p style="color: lightgrey" >This text will be interesting to see.</p>
<p style="color: grey" >This text will be interesting to see.</p>
<p style="color: darkgrey" >This text will be interesting to see.</p>
<p style="color: lightgreen" >This text will be interesting to see.</p>
<p style="color: green" >This text will be interesting to see.</p>
<p style="color: darkgreen" >This text will be interesting to see.</p>
```
- result:

![howitworks](/media/example-enums.png)

- So what happened with color attribute? Enum ["light", "", "dark"] went normally with stepping 1, but enum ["blue", "salmon", "cyan","gray", "green"] because of stepping 0.333333 changed `only once every third time` so for each color we get three variants of different saturation (light, normal, dark). This kind of `fractional stepping` we can also do with integer numbers, dateISO, timeISO and simple. Try it yourself.

Here are few already prepared enums which you may find useful during work and insert them in Mega Increment settings.
+ Key: week days, Value: ["Sunday","Monday","Tuesday","Wednesday","Thursday","Friday","Saturday"]
+ Key: short days, Value: ["sun","mon","tue","wen","thu","fri","sat"]
+ Key: colors, Value: ["red","green","blue","cyan","magenta","yellow","black"]
+ Key: roman numerals, Value: ["I","II","III","IV","V","VI","VII","VIII","IX","X"]
+ Key: numbers, Value: ["one","two","three","four","five","six","seven","eight","nine","zero"]

There are two variants of enums but since they can be interchangeably used only in Advanced Increment GUI they will be covered later.

[Back to Contents](#Contents)





<h2 id="GUIforAdvancedIncrement">GUI for Advanced Increment</h2>


Graphical user interface for Advanced increments provides user with interactive incrementing, detailed picture of selections, enums, result, changing line text with active settings, multi line strings, direct insert of enums in line text, retrieving line text, changing variant of enums, exporting results, exporting API calls and more to come.  

Lets se how it looks on previous example with colors.

  1. Advanced increment tab  

  **Line text section:**

  2. Number of times the line text is incremented
  3. Line text is automatically retrieved from editor
  4. Use Alt+8 to get focus on line text  
  *More information about Alt+8 and other web accesskeys in: https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/accesskey*
  5. Line text can be retrieved back if changed or lost  

  **Types section, buttons enable selecting type for selected text, available buttons depend on what kind of text is selected:**

  6. **Basic** forms of incrementing: simple which treats selected text as sweet of individual characters and number for integers and floating point numbers
  7. **JS** group for enums/lists, date and time
  8. **C** group for hex, binary, random and crypto types  

  **Enums section:**

  9. Table of available enums in mega increment settings, from this table new enums can be inserted in line text
  10. Button for inserting enums from table (alongside those maybe already present in text line)  

  **Selections section:**

  11. Table with details about selections
  12. Buttons for:
        + **deleting** all selections (shortcut Alt+0)
        + export of active setup as curl API call (*Be careful when using `'` and `"` in curl API calls from (Linux/Mac) shell(s). Because of shell performing string concatenation on the command line and JSON format which depends on `""` you probably must: escape each `'` with `'\''` for shell concatenation, escape each `"` with `\"` for JSON parsing. In some programming languages practical implementation for escaping like this might require additional escaping of backslash `\` character so it might look as this: `'\\''` and `\\"`.*)

  **Result section:**  

  13. Area for interactive display of incrementing result
  14. Buttons for exporting the result to:
      + editor (when back in editor go to the end of line and hit Ctrl+Alt+U to retrieve result from GIU)
      + clipboard and
      + JSON array.

  ![howitworks](/media/gui3.png)

Let's see that in motion:

  ![howitworks](/media/gui-gif1.gif)

[Back to Contents](#Contents)





<h2 id="Continuousandrangedenumvariants">Continuous and ranged enum variants</h2>


- **continuous**: treats enum list as continuous i.e. infinite and increments items in linear fashion. When incrementation reaches the end of list it goes further like there is new list attached. If we increment enum with simple numbers ["one","two","three","four","five","six","seven","eight","nine","ten"] starting from `one` and with stepping 3 we will have: `one`, `four`, `seven`, `ten` *and then:* `three` (lite thirteen), `six` (like sixteen), `nine` (like nineteen) etc. etc.

- **ranged**: enum list is contained in its range so increments beyond list length are trimmed. This variant makes sense if you start from the beginning or middle of the enum but if you start from near the end it makes less sense:
  * Let's say we start from `six` with stepping 3 in numbers. After 2 increments it goes out of the enum range because `six` + 3 = `nine` and +3 = `twelve`:
    - but we can't go to `twelve` or `two` because we selected ranged variant so `two` and the rest will be trimmed 
    - and we also can't go to `one` because it is not the starting position and it also doesn't fit for decrement: `six` -3 = `three` and -3 = `zero`, so `one` is not solution.
  * So in this case  and only 2 items from enum will be repeated constantly in result: `six` and `nine`.
  * Therefore, ranged is very specific and you must clearly understand how it behaves in order to use it correctly in relation to continuous. Best is to first test result with your expectations.

[Back to Contents](#Contents)




<h2 id="PublicAPI">Public API</h2>


This project includes public API with same functions as extension. You can see the MACf API Documentation at: https://vezbamo.vercel.app/api/mi/pad or at [GitHub](https://github.com/vladanan/mega-increment/blob/master/PublicAPIDocs.md).

[Back to Contents](#Contents)




<h2 id="Settings">Settings</h2>


For Mega Increment settings you go to VSCode Settings and then find Mega Increment section or just type '**mega**' in search field and you get to those settings quickly.
- *Depending od OS especially on some Linux systems VSCode might have to be restarted for some settings to take effect.*

This extension contributes the following settings in VSCode:
- `Mega-increment: Default Stepping`: Choose default stepping for editor and GUI.
- `Mega-increment: Default Enum Variant`: Choose default incrementation variant for enums.
    * continuous: Treats enum list as continuous i.e. infinite and increments items in linear fashion.
    * ranged: Enum list is contained in its range so increments beyond list length are trimmed.
- `Mega-increment: Key Value Pairs`: Create custom key value pair lists for frequently used enums and lists.  

[Back to Contents](#Contents)




<h2 id="FAQ">FAQ</h2>


### Why would this extension be needed if those same things can be programmed at need with loops etc.?
I developed this extension from my personal need so I can vouch for the following reasons:
  - You will lose more time to program any of the custom increments than to produce it via extension.
  - Yes, programmed snippets can be reprogrammed and extended but that is also true for snippets from extension, except for highly customized and isolated cases.
  - Snippet from extension is easier to read and maintain.
  - Snippet from extension is faster to produce and use for testing:
    + If code works well it can be later optimized 
    + If you find out that you don't need such code then at least you didn't spend a lot of time developing custom code.

Since I offer a public API outside of extension anyone from any app can use extension power instead of writing custom code for most standard increments and decrements.

Can this be done using AI? Yes but it would usually last longer and with uncertain results.


### Why GUI sections are divided and named Basic, JS, C?
![nodonations](/media/nodonations2.png)


[Back to Contents](#Contents)



 
<h2 id="KnownIssues">Known Issues</h2>


Windows 10:
- With default shortcut for add selection Ctrl+Alt+8 an apostrophe is written and selected text is deleted. The same can happen wiht Ctrl+Alt+9 or 0. After several shortcut combinations tested Ctrl+Alt+J works well.
- When items are selected with `Enter` in menu in editor sometimes `Enter` is written in editor itself so selection iz owerwritten and new line is inserted. After Ctrl+Z `Undo` all works well.

[Back to Contents](#Contents)




<h2 id="Licence">Licence</h2>


Copyright (C) Vladan Anđelković. All rights reserved.
