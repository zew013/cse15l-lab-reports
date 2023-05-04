# Lab Report 3
## Zelong Wang

## Command ```grep```
##
### Option 1 ```-e pattern```
Source: \
https://en.wikibooks.org/wiki/Grep \
GPT 4, letting him futher explain each option

**Description:** \
Specify the patterns to search for. This is useful when you have multiple patterns to search for in a single command.

**Example (1)**:

```
(base) zl@ous-MacBook-Pro docsearch % grep -e 'building' -e 'Boston' technical/911report/chapter-1.txt
```

**Output:** 

```
*Boston*: American 11 and United 175. Atta and Omari boarded a 6:00 A.M. flight from Portland to *Boston*'s Logan International Airport.
    
When he checked in for his flight to *Boston*, Atta was selected by...

All on board, as well as many civilian and military personnel in the *building*, were killed

...
```

**Explain:** \
The command extracts lines that includes either "building" or "Boston". If we do it separately, then if they are in the same sentence, we might get two repeated sentences.

**Example (2)**: 
```
(base) zl@ous-MacBook-Pro technical % ls | grep -e bio -e gov
```

**Output:** \
biomed \
government

**Explain:** \
The command extracts lines that includes either "bio" or "gov". It saves the time of writing multiple conditions.

<br>
<br>

### Option 2 ```-i```
Source: \
https://en.wikibooks.org/wiki/Grep \
GPT 4, letting him futher explain each option

**Description:** \
`-i`: Ignore uppercase vs. lowercase. Case-insensitive search. It can be useful when we want to find out both the upper and the lower case.

**Example (1)**: 
```
(base) zl@ous-MacBook-Pro technical % grep -i 'Between' 911report/chapter-1.txt
```

**Output:** 
```
*Between* 6:45 and 7:40, Atta and Omari, along with Satam al Suqami,...

...The Shehri brothers had adjacent seats in row 2 (Wail in 2A, Waleed in 2B), in the firstclass cabin. They boarded American 11 *between* 7:31 and 7:40. The aircraft pushed back from the gate at 7:40.

...
```

**Explain:** \
Both "Between" and "between" are taken into account. It's useful because in this case they are not different, and we save time not writing two conditions.

**Example (2)**: 
```
(base) zl@ous-MacBook-Pro technical % grep -i 'flights' 911report/chapter-1.txt
```

**Output:**
```
INSIDE THE FOUR *FLIGHTS*

Boarding the *Flights*

The 19 men were aboard four transcontinental *flights*

...
```
**Explain:** \
Both "Flights" and "flights" are taken into account. It's useful because in this case they are not different, and we save time not writing two conditions.

<br>
<br>

### Option 3 ```-v```
Source: \
https://en.wikibooks.org/wiki/Grep \
GPT 4, letting him futher explain each option

**Description:** \
`-v`: Invert match. Show lines that do not match the pattern. It could be useful if you want to find the negation of a condition which is difficult to define.

**Example (1)**: 
```
(base) zl@ous-MacBook-Pro technical % grep -v 'it' 911report/chapter-1.txt 
```

**Output:**
	
```
"WE HAVE SOME PLANES"



INSIDE THE FOUR FLIGHTS

Boarding the Flights



Atta and Omari arrived in Boston at 6:45. Seven minutes later, Atta apparently took a call from Marwan al Shehhi, a longtime colleague who was at another terminal at Logan Airport. They spoke for three minutes.

It would be their final conversation.

...
```

**Explain:** \
Any lines not including "it" is returned. Notice the last line, it is case-sensitive. And it's helpful because it's hard to list all the conditions not including "it".


**Example (2)**: 
```
(base) zl@ous-MacBook-Pro technical % ls ./911report | grep -v 'chapter' 
```

**Output:**
```
preface.txt
```
**Explain:** \
Any file not including "chapter" is returned. It's helpful when you don't know what are the names of other files besides "chapter".



### Option 4 ```-c```
Source: \
https://en.wikibooks.org/wiki/Grep \
GPT 4, letting him futher explain each option


**Description:** \
`-c`: Output count of matching lines only. 

**Example (1)**: 
```
(base) zl@ous-MacBook-Pro technical % grep -c 'flight' 911report/chapter-1.txt 
```

**Output:**
```
74
```

**Explain:** \
Number of lines that contain "flight". It saves the extra steps of extract the lines and count the lines if we only want to know the number of lines.


**Example (2)**:

```
(base) zl@ous-MacBook-Pro technical % ls ./911report | grep -c 'chapter'
```

**Output:**
```
16
```
**Explain:** \
It directly returns the number of chapters and saves the intermediate steps.


