# doterra-po3-widget
DoTERRA's Power of Three $50 Bonus Widget is a convenient tool that allows wellness advocates to quickly glance at their progress and see if they are close to achieving their $50 monthly bonus. This information was never available on mobile until now, making it a game changer.

I was able to spearhead this project with the help of two back-end developers and our usability research team. Feedback from customers has been fantastic; they now want more widgets to help them run their business.

ℹ️ The following documentation is intended for internal use only. Some information has been redacted for privacy. See below for examples of the documentation experience.
## Promo Videos

https://www.youtube.com/watch?v=GRjHj73SBa8

https://www.youtube.com/watch?v=YxJMa38EimQ

## Po3 Rules
https://media.doterra.com/us/en/flyers/power-of-3.pdf

__Individual must have all of the following to qualify for Po3 Bonus:__
- [x] 100 LRP PV (personal volume)
- [x] 600 TV (team volume)
- [x] 3 individuals on level 1 of downline have at least 100 PV each

## Design / UI
### Final Design Screenshots

After many interations following usability feedback this is the final completed widget on iOS. Android team reference the following image and contact Bekah if you have any questions. 

<img width="1001" alt="Screenshot 2024-09-30 at 11 43 21 PM" src="https://github.com/user-attachments/assets/908573c2-7ea5-45fd-ae2b-62e59bc47d03">

### Color Legend
* Dark Blue (#5597E2) : Completed PV 
* Light blue (#CADFF8) : Scheduled PV (within current month)
* Purple (#A25EB5) : Completed TV / TV needed
* Green (#7BB739): Goal reached 

### Green Text / Progress Circle
* If downline team member reaches 100 PV turn progress circle and PV green (Image #1)
* Do not turn leader’s progress circle and PV/TV text green until goal Po3 goal is reached 
* When Po3 goal is reached turn text and circle green. Add green check in place of inner circle. 

## Refresh App
### Logic 
* If app is logged in - When user taps widget do not open app but trigger a refresh.
* If app is logged out show login screen prompt. When user presses on widget open app’s login page. Following successful login the widget should refresh.
### Last updated X min ago
Each widget needs to contain text showing when the last updated time was. For example: “5 min ago”. Increment by minute and refresh the widget every hour. If the refresh doesn’t push through, then display “1+ hours ago“.  When the user presses on the app widget, it should refresh and does NOT open the Shop App unless the user is not logged in. 

## API
### GET information hidden for privacy
### How is the data sorted?
* If PV >= 100: Sort by VOL1 (highest to lowest)
* If PV < 100: Sort by (VOL1 + AUTO_NEXT_VOLUME)

This sorting method allows scheduled orders with high PV to be prioritized over completed orders with not enough PV to contribute to the bonus. 
## Translations 
Localization has been implemented, ensuring that the widgets are compatible with Chinese, French, Japanese, Spanish, and English.
