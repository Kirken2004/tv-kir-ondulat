# tv-kir-ondulat
Pine script for Trading View about Hodosa N-Wave

    This indicator is an amateur exercise. 

    THIS IS NOT AN ADVICE IN TRADING OR INVESTMENT. 
    USE, MODIFY, REDUCE, AUGMENT IT AT YOUR OWN RISK AND EXPENSE. 

## Disclaimer

    Distributed under the GNU Lesser General Public License. 
    This license apply to the modification and redistribution of the script. 
    It does not apply to the use of it. 
    
    For using this script inside Trading View, you may refer to the license under which Trading View and PineCoders are ruled. 


It's my first pine script ever. Be kind.

The actual code is very procedural and has many duplicated stuff. 

- I have to study the making of helper functions, scopes, series and how to dynamically instantiate shapes.

- I also have no idea how to manage multiple instances of this indicator on the same chart. This is not yet a toolbar tool.

- Only tested on BTCUSDT. This script may fail to render correctly on symbols with many zeros after the decimal point, at their current value.


## Getting Started

    - On your TV account, click on "Pine Editor".
    - Click on "Open" and choose "New Indicator..."
    - Give it a name if asked
    - Paste the content of "KOndulat.pine" into your editor (replace everything)
    - Click "Save"
    - You may have to remove the indicator from the currently displayed chart
    - Click on "Indicators" and look for the saved indicator (you chose the name)
    - On activation, it asks for three points A, B and C. (choose and click 3 times)
    - Open the "Settings" of the indicator in the top left area of the chart
    - You may check some options if needed


## Usage

In theory, the **N Wave** is the usual conclusion of an ABC Wave, usually described as ABCD. But as D is not realised yet, while C is.
If BC is atleast 33% of AB, it's fair to assume the price is going to rebound in the other direction with the same strength as the impulse AB. 

The **N arrow** is merely AB drawn again from C. 
That hypothetical D pointed by the N arrow is at the **Target Time**.

The **Target Time** is in a window in which the value is not supposed to be drastically changing, once the current bar gets inside. The duration of the window is inferred by the BC duration. 

To make things safer, a dashed line named the **Decision Line**, away from BC, is drawn at the same distance from C. This dashed line is coercitive. You have to know that changing decision (your positions) once the chart is past that point, is unsafe if your position was assisted by this indicator. 

The indicator is helpful at the time it is drawn until the chart gets in the window. It wont move over time. Whatever the market is doing, once on the other side of the **decision line**, this instance of the indicator becomes a thing of the past.

The **E arrow** is what the market would have done if not stopped at B. But delayed by the BC time. 

The **NT arrow** is almost the opposite, it's what the market would have done at the Target Time if the pressure had been the same between A and C. If C is lower than A, that differential is computed again. 

The **V arrow** is what the market would have done if the sign of BC had been reversed. 

The indicator loses his relevance when the **Retracement BC** is lower than 33%.
Above that, arrows **N, V, E and NT** can still show potential targets.

When the market is strongly bullish or bearish, it's not unusual to watch the price go crazy above or below the window. In such case, the chart may follow a strength arrow that is a multiple of **E** or **N**. That's why this script has an option to display those multiples. 


## F.A.Q.

    Why did i make this script ? 

As an exercise in the discovery of PineScript. I just wanted to understand how community indicators were made and how difficult or easy it was. 

    Why didnt you publish your script on TV ?

I did, and it lasted 24 hours, after which a moderator kicked me for breaching the "Rules of the House" at PineCoders. The violation i commited was primarily the lack of documentation. As i understood the situation, you cant publish a script still in a development phase. Giving no clue to the user is a violation of the rule of conduct. 

    What made you choose the N Wave as a subject for this exercise ?

I watched a presentation on Twitch about the undulatory theory of Hosoda. The streamer used a private indicator, apparently very simple but behind a paywall or something. I found that weird as the indicator is so simple to reverse engineer. So i did. I may have stolen the color grading since i followed a screenshot of the stream. 

    Are you going to update this indicator in the future ? Or make new ones ?

No. Probably not.


## CONTACT

    None.
    
    Kir out.