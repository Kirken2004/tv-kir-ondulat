# tv-kir-ondulat
Pine script for Trading View about an Hosoda N-Wave indicator 

    This indicator is an amateur exercise. 

    THIS IS NOT AN ADVICE IN TRADING OR INVESTMENT. 
    USE, MODIFY, REDUCE, AUGMENT IT AT YOUR OWN RISK AND EXPENSE. 


## Screenshots

![N Wave Target Window](https://github.com/Kirken2004/tv-kir-ondulat/blob/main/preview.jpg?raw=true)
<p align="center">fig. 1 - The N Wave Target Window</p>

![Fibonacci Axis](https://github.com/Kirken2004/tv-kir-ondulat/blob/main/preview_fibonacci_axis_retracements.jpg?raw=true)
<p align="center">fig. 2 - The Fibonacci Axis and the Retracements</p>

![Ichimoku Kinko Hyo and EMA](https://github.com/Kirken2004/tv-kir-ondulat/blob/main/preview_ichimoku_ema.jpg?raw=true)
<p align="center">fig. 3 - Ichimoku Kinko Hyo, Clouds and the EMA 200</p>

![Kihon Suchi and Tenkan Crossover Cycles](https://github.com/Kirken2004/tv-kir-ondulat/blob/main/preview_kihon_suchi_tenkan_crossovers.jpg?raw=true)
<p align="center">fig. 4 - Kihon Suchi and Tenkan Crossover Cycles</p>

![Inputs Panel](https://github.com/Kirken2004/tv-kir-ondulat/blob/main/preview_settings_inputs.jpg?raw=true)
<p align="center">fig. 5 - The Settings - The Inputs Panel</p>

![Style Panel](https://github.com/Kirken2004/tv-kir-ondulat/blob/main/preview_settings_style.jpg?raw=true)
<p align="center">fig. 6 - The Settings - The Style Panel</p>



## Disclaimer

    Distributed under the GNU Lesser General Public License. 
    This license apply to the modification and redistribution of the script. 
    It does not apply to the use of it. 
    
    For using this script inside Trading View, you may refer to 
    the license under which Trading View and PineCoders are covered. 


It's my first pine script ever. Be kind.

The actual code is very procedural and has many duplicated stuff. 

- I have to study the making of helper functions, scopes, series and how to dynamically instantiate shapes.

- I also have no idea how to manage multiple instances of this indicator on the same chart. This is not yet a toolbar tool.

- Only tested on BTCUSDT. This script may fail to render correctly on symbols with many zeros after the decimal point, at their current value.

- I used Bing Copilot to produce some parts of the script. 

- Until now, Copilot never ever once produced a working pine script for v5. I had to cut and refactor for my needs. Copilot is at the moment a pain in the ***.


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

_I'm not the best to explain. The following may be inaccurate. I'm improvising briefly as those concepts come to my mind writing this. Please, look for a proper documentation. Links at the bottom of this document._

In theory, the **N Wave** is the usual conclusion of an ABC Wave, usually described as ABCD. But as D is not realised yet, while C is.
If BC is atleast 33% of AB, it's fair to assume the price is going to turn in the other direction with the same strength as the impulse AB. 

The **N arrow** is merely AB drawn again from C. 
That hypothetical D pointed by the N arrow is at the **Target Time** (sometimes called the **N time**, or even **N Target**).

The **Target Time** is in a window, a box, in which the value is supposed to evolve or solidify the current structure move. The left side of the box is time 1, and the middle dashed line is the time 2. Once the current bar gets inside, you know the time component of the action. Yet you'll have to discover the price it goes to. The duration of the window is inferred by the BC duration. The right side of the window (time 3) is usually the beginning of a new wave building up, or a continuation you had to confirm.

A reddish dashed line named the **Correlation Line** is drawn away from BC, at the same distance from C. This dashed line is at a moment in time when you may want to check the rightness of the predictions. If the candles follow the arrows and dont change direction before this stage, the window is still a potential target for the N Wave. If the candles went completly elsewhere, you probably misplaced your ABC points. Or the market just went crazy, like it often does (sic). 
If the line is before or after time 2 by one period, you may determine a correlation with the Ichimoku numbers (ie. Kihon Suchi series).

The indicator is helpful at the time it is drawn until the candles gets into the window. It wont move over time. Whatever the market is doing, once on the other side of the **Correlation Line**, this instance of the indicator becomes a thing of the past. If you made a plan using it, stick to the plan. And play it safe if the market tries something unexpected in that window. 

The **E arrow** is what the market would have done if not stopped at B. But delayed by the BC time. 

The **NT arrow** is almost the opposite, it's what the market would have done at the Target Time if the pressure had been the same between A and C. If C is lower than A, that differential is computed again. 

The **V arrow** is what the market would have done if the sign of BC had been reversed. 

The indicator loses some of its relevance when the **Retracement BC** is lower than 33%.
Above that, arrows **N, V, E** and **NT** can still reveal potential targets.

When the market is strongly bullish or bearish, it's not unusual to watch the price go crazy above or below the window. In such cases, the chart may follow a strength arrow that is a multiple of **E** or **N**. That's why this script has an option to display those multiples as new attractive targets. Take notes that 5E/5N are irrational targets.

The **SLP** stands for **Straight Linear Projection**. It's really just the direction the chart is heading into from the C point to now (now being the last confirmed bar). It has no real value. The calculated value shown in the purple label is the market price this chart would end up at if continuing in that direction, up to the **Target Time**.

I also added a feature called **Tenkan Crossover Markers**. An arrow is displayed above bars when a Tenkan crossed over the Kijun. The numerical value indicate the number of bars since the last event of that kind occured on the left. When the tenkan is crossing over, it's often accompanied by a movement up or down of the price. It's a change in the structure itself. It's important to follow those crossovers. 

The **Kihon Suchi** series describe a typical number of bars after which the Tenkan sen crosses over the Kijun sen. It's theory. And prone to errors by 2 due to the nature of bars in a timeframe. After the last crossing, one can expect to see the next one following that series. I added this indicator for fun. The dashed gold line is not on the series. It shows the bar in the future that correspond to the same cycle than the last one. The numbers of the series can be displayed at the bottom center of the chart. 

At the moment, this indicator is tedious to use on several charts at once : 
    - You may require one layout(tab) per chart. 
    - Switching between symbols is not working. 
    - I wish i could draw several instances of this indicator on one chart without any trouble. 
    - Dont check every option at once, you'll lose elements past 50 ones on the chart per indicator. 
I'm pretty sure you'll find a comfy way to use it anyhow. 


## F.A.Q.

    Why did i make this script ? 

As an exercise in the discovery of PineScript. I just wanted to understand how community indicators were made and how difficult or easy it was. 

    Why didnt you publish your script on TV ?

I did, and it lasted 24 hours, after which a moderator kicked me for breaching the "Rules of the House" at PineCoders. The violation i commited was primarily the lack of documentation. As i understood the situation, you cant publish a script still in a development phase. Giving no clue to the user is a violation of the rule of conduct. 

    What made you choose the N Wave as a subject for this exercise ?

I watched a presentation on Twitch about the undulatory theory of Hosoda. The streamer used a private indicator, apparently very simple but behind a paywall or something restricting. I found that weird as the indicator is so simple to reverse engineer. So i did. I may have stolen the color grading since i followed a screenshot of the stream. This streamer also had other options and more variant of the tool in his arsenal. I'm way out of my league and i'm not inclined to copycat everything he does. But that's inspiring. 

    Are you going to update this indicator in the future ? Or make new ones ?

No. Probably not. I'll get bored very quickly on that subject.


## Documentation & Sources

- Videos

    - Japanese Forex Trader Kei's Masterclasses (English)

        - Ichimoku Kinko Hyo Part 1 [https://www.youtube.com/watch?v=BsS6iAqDZFc]
        - Ichimoku Kinko Hyo Part 2 [https://www.youtube.com/watch?v=paJ4siNG5DQ]
        - Ichimoku Kinko Hyo Part 3 [https://www.youtube.com/watch?v=iKyue8rugmw]
        - Ichimoku Kinko Hyo Part 4 [https://www.youtube.com/watch?v=4HJgaYwahyg]
        - Ichimoku Kinko Hyo Part 5 [https://www.youtube.com/watch?v=fM4s_piN-Ps]

    - ChaosTrader63's channel (English)

        - Trading Ichimoku Kinko Hyo Three Roles With Wave, Price, & Time Theories [https://www.youtube.com/watch?v=CIjWEsr0Cgo]

    - ZS Trader's Masterclasses (French)

        - On youtube [https://www.youtube.com/@cryptologik-live/videos]
        - On twitch on tuesdays [https://www.twitch.tv/cryptologikfr]

- Websites

    - Wikipedia

        - Fibonacci retracement [https://en.wikipedia.org/wiki/Fibonacci_retracement]
        - Ichimoku Kinkō Hyō [https://en.wikipedia.org/wiki/Ichimoku_Kink%C5%8D_Hy%C5%8D]

    - TradingView

        - IKH Wave Theory Introduction and Indicator Basics [https://www.tradingview.com/chart/BTCUSD/NHqEe3Qk-Ichimoku-Kink%C5%8D-Hy%C5%8D-Wave-Theory-Introduction-and-Indicator-Basics/]

    - XTB.com (French)

        - Ichimoku: quel est cet indicateur ? [https://www.xtb.com/fr/formation/ichimoku]


## Contact

    None.
    
    Kir out.
