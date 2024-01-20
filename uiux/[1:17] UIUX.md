# [1/17] UIUX 

### Design Heuristics

#### [1] Visibility of System Status

- **Definition:** The system should always keep users informed about what is going on, through appropriate feedback within reasonable time
- **Classical Examples**
  - Loading Bars (tqdm)
  - Reset User Password 
    - Email address that the confirmation is sent to
    - Time (24 hours to change password)
  - Bar at the Top of the Iphone
    - Wifi Available (2 bars vs 3 bars) $\rightarrow$ provides more information about what's going wrong!
- **Violation of Visibility System Status**
  - Apple Mac Updates $\rightarrow$ the 'About a minute remaining' is oftentimes a lie
  - SSOL
    - Waitlist software, class registration, provides absolutely no feedback or user visibility which leads to a bunch of useless emails

#### [2] Match Between System and Real World

- **Definition:** The system should speak the users' language, with words, phrases and concepts familiar to the user, rather than system-oriented terms
  - Helps user readability, helps us learn via metaphors (trash bins = garbage for Mac)
- **Classical Examples**
  - 'Desktop' $\rightarrow$ idea of desktop
  - File system $\rightarrow$ Computer File System
    - Aspects of subfolders are really useful
    - People like this, leverages what they already know, and provides good functionality
  - Movie Theatre Seat Selection Chart $\rightarrow$ how close you will be to the screen, close to the aisle, etc.
    - Let's you evaluate important seat selection features!
- **Violation**
  - 'CREAT' $\rightarrow$ is the command for UNIX (should be create)

#### [3] User Control and Freedom (Navigation)

- **Definition:** Users should be able to quickly make choices, correct mistakes, or backtrack on choices made. Support undo and redo.
- **Classical Examples**
  - Command + Space (on Mac) $\rightarrow$ typing anything and getting results (matching files) is better than remembering where you stored something exactly, makes navigation very clear
  - Amazon Side Tab (filters and sorts) $\rightarrow$ example is furniture shopping and it gives you categories for 'color', 'material', etc.
    - Helps you filter down to the thing you want (out of the thousands and thousands of things)
  - Undo Buttons $\rightarrow$ undoing a 'conversation moved to trash' or 'send email'
    - Ability to undo is the most important thing, so they can change their mind later! 

#### [4] Consistency and Standards

- **Definition:** Users should not have to wonder whether different words, situations, or actions mean the same thing. Follow platform conventions.
- **Classical Examples**
  - Word vs. Powerpoint $\rightarrow$ image editing techniques are the same! Provides a level of consistency to the image options
    - Word and Powerpoint way of inserting images are the same (which is better for user consistency)
  - Application design across different devices (make sure that apps look somewhat similar or similar enough across phone + laptop UIs)

-  **Violation**
  - Android vs Apple consistency (video recording) $\rightarrow$ the buttons are different across the camera apps, and that is annoying
    - Not important if it "intuitively" makes sense (i.e. both are a red dot), you want the placement to be the same

#### [5] Error Prevention

- **Definition:** Even better than good error messages is a careful design which prevents a problem from occuring in the first place.
- **Classical Examples**
  - Columbia Search $\rightarrow$ I want the college, not the sportswear company, so saving a few more pieces of information to prioritize the college is much better for when I search it up on Google
    - #1 recommended will be Columbia University
  - Autosave $\rightarrow$ you don't have to remember anything anymore! No more panic about Command + S
- **Violation**
  - 'Reply All' $\rightarrow$ a lot of personal information can be leaked for reply all messages, Reply and Reply All look very similar but the consequences are way worse

#### [6] Recognition Rather than Recall

- **Definition:** Minimize the user's memory load by making objects, actions, and options visible. The user should not have to remember information from one part of the dialogue to another
- **Classical Example**
  - Can't remember the exact location of a file, rather an icon is way easier so you can just click on it to access that file (find the property of that file $\rightarrow$ which gets you the filepath)
  - Autocomplete in VSCode $\rightarrow$ find the variable names
    - Recognizing the variable name rather than recall
- **Violation**
  - Picking font $\rightarrow$ how tf am I supposed to know what MS San Serif vs MS Serif? Writing the font name in the actual font is much better (than having to remember the font)!

#### [7] Flexibility and Efficiency of Use

- **Definition:** Accelerators - unseen by the novice user - may often speed up the interaction for the expert. Allow useres to tailor frequent actions.
- **Classical Example**
  - Fast Typing via swiping on the Iphone
  - Keyboard shortcuts
  - Emacs Editor (change the color and visual UI of their coding platform)

#### [8] Aesthetic and minimalist design

- **Definition:** Dialogues sholud not contain information which is irrelevant or rarely needed. Every extra unit of information in a dialogue competes with the relevant units of information and diminishes their relative visibility.
- **Classical Examples:**
  - Google Search Engine is better than Bing $\rightarrow$ no extraneous links, lot of whitespace, simple search bar
  - Tinder $\rightarrow$ reduces people to a name, age, picture, and 'yes'/'no' (super minimalist design)
- **Violation**
  - Boarding Passes, printed versions are ugly as hell
    - Aesthetics are not just color and visibility!

#### [9] Helps users recognize, diagnose, and recover from errors

- **Definition:** Error messages should be expressed in plain language (no codes), precisely indicate the problem, and constructively suggest a solution
- **Classical Examples**
  - When passwords tell you that you have to be 6 characters, only numbers and letters, or that your email is invalid!
- **Violation**
  - Horrible computer Error message $\rightarrow$ random binary errors lmao

#### [10] Help and Documentation

- **Definition:** Documentation should be easy to search, focused on the user's task, list concrete steps to be carried out, and not be too large.
- **Classical Examples**
  - StackOverflow $\rightarrow$ you don't have to read the whole user manual anymore!
- **Violation**
  - Windows 95 video guide is so useless!