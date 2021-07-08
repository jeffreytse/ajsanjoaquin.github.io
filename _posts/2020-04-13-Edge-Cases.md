---
layout: post
title:  "Edge Cases"
date:   2020-04-13 17:04:01
categories: post
---

I got off from the bus and proceeded to walk for half a kilometer.
‘405 Havelock, Furama Hotel. Turn on the second right’ I kept muttering to myself so I didn’t have to check my Google Maps again. As I was nearing my destination, I glanced on top of the buildings. I saw the bright golden words ‘FURAMA RIVERFRONT’ which impulsively made me brisk walk. I was, after all, late.

[!furama](https://miro.medium.com/max/2400/1*pZl0t1PATe-SdOv3NHiAkA.jpeg "It’s quite a good experience having a free dinner at a four- star hotel")

I walked across the driveway because there was no dedicated pedestrian lane to the hotel. People were getting off their cars with their blazers and Indochinos. I was getting off the road with my Uniqlo outfit and blue Nike trainers. Luckily, those people went to a different event.
I entered the Mercury Room, and I immediately saw the only two people I chatted with the day before, a Filipino doctor and an Indonesian photographer. Yesterday, they were strangers. Now they are the only people I know in the room.
They led me to a table, and I proceeded to talk with the Doctors who were all from Indonesia. Barely 5 minutes getting into the table and before I could finish answering their questions about my summer, I was shifted again since the event hosts decided they wanted to randomize the tables (ostensibly to prevent people from grouping up; that made it fair game to me). This allowed me to meet doctors ranging from an oncologist to an otorhinolaryngologist (Ear, Nose, Throat doctor; yes I also had to google that up).
I was seated with a Japanese M.D. & PhD. from Fukuoka, two medical students from my university, and my photographer friend. As we introduced ourselves, the Dr., M.D. asked:
‘Hello, where are you from? Do you have a specialty?’
‘I’m from the Philippines. No I don’t.’
‘Ah, general practitioner?’
‘No, I’m an undergraduate student from NUS.’
The two medical students then looked at me, as if trying to recall my face. I added:
‘No, I’m not a medical student, I’m a liberal arts student.’
It all started with a dance
A day before, I accepted an invite from my Doctor friend, Eugene, to join a doctor’s gathering. He previously invited me to food gatherings so I assumed I was getting free snacks. The doctors arrived late, and in the confusion of the introductions that followed, the organizer thought I was a volunteer. The event was a reunion of the Asian Medical Student’s Alumni Club (AMSAC) in Singapore. The food gathering I thought of turned out to be a dance session, and I initially thought this was a relaxation session from their events as an alternative to a Zumba class. They invited me to dance with them.

[!amsaac](https://miro.medium.com/max/700/1*MsnqOh8uZsuk3fN5j8hpng.jpeg)

Volunteer to eat food? Yes. But volunteer for the dance? Not as eager.
While there was no food, I decided to stick around because a group of doctors dancing to “This is Me” from The Greatest Showman is such an unusual sight. I wouldn’t be able to see doctors as serious, precise professionals in the same way again as some of us made clumsy choreographic mistakes.
At the middle of the dance, due to my engaging performance (or realistically, not enough doctors were dancing), I was invited to dance with them for the real performance. The organizer then explained this was merely a practice session because they were going to perform at Resorts World Sentosa in front of hundreds of medical students from AMSA International (the non-alumni medical association).
To see doctors dance is an unusual sight, but to see them parade themselves in front of medical students was entirely something else. Again, my search for quality food would surely be found at one of Singapore’s well-known resorts. I agreed to join.
At the end of the practice, I was requested to collect the payments from the doctors for the session (of course I didn’t pay with anything except for my labor). Sure, I talked to them and all, but realistically I just met them a few hours ago, and with my friend Eugene having to leave in the middle of practice for an errand, I was still a stranger. Ah, yes. Trust a stranger with almost a thousand dollars.
As I sat there awaiting people to pull out their wads of cash from their luggage, I met the Indonesian photographer who would help me survive the initial contact in the dinner. When I mentioned I was a student with a scholarship in a foreign country, he shared his dream of sending his child to the same position I now occupy. I didn’t expect that response, as I usually got a “good luck with your studies” response whenever I tell them the same thing. It’s good to be reminded of privilege, especially when it takes you in an unusual adventure.
Unfortunately, the doctors that came late to the practice were to be my downfall as they were the necessary manpower that rendered myself unnecessary for the dance. In the end, I wasn’t able to join. As I was about to leave, grateful yet still wanting some free food, the organizer invited me to the dinner the next night as an appreciation for the volunteers (though I think I was the only volunteer).

[!dancing_peeps](https://miro.medium.com/max/700/1*JmjCwGBvMEbW2pgdOcdWMA.jpeg "Author’s impression of the doctors dancing at Sentosa that night (Image taken from Musical TARU)")
### "Sure, I guess"
It turns out this dinner was the main reunion event, where all the doctors in the alumni club attended. I got further “good luck with your studies” as well as genuinely interested people when I mentioned I was doing a summer job on plant metabolic modelling. I was also introduced to a former cruise doctor who now works in Malaysia (who offered to tour me around Kuala Lumpur during Hari Raya).
All in all, it was pretty confusing at first, but it was great once you were finally eating and getting to know where these doctors worked ranging from clinics to startups.

[!presenting](https://miro.medium.com/max/700/1*RMCP3GxPBGzkmWoMYDCO4g.jpeg "Some doctors had interesting backgrounds like working for Alodokter, a successful Indonesian healthcare info startup!")

The biggest factor to not saying no given their unusual requests at first (can you join us in our dance at Sentosa and collect our money?) was my free time. I was genuinely curious what these doctors would (and did) do. It taught me being fun was not something to be traded once you were a professional, more so when you are at the front line of telling people and their families of terminal illnesses and death. Most of them were beyond their thirties, and it’s reassuring that their friendships have endured even as they have graduated from medical school.
They have made their diverse backgrounds a tool, as I overheard one of them asking if they can be connected to someone in Malaysia to transfer some medical technologies to its Southeast Asian neighbors as technologies aren’t standardized among them. This was an opportunity for them to share best practices and updates about their respective medical communities.
I had seen a different snapshot of them. And it’s probably not something seen by most, if not all, of their patients.

[!doctors_good_dancers](https://miro.medium.com/max/700/1*RMCP3GxPBGzkmWoMYDCO4g.jpeg)


Some edge cases and cautionary examples on using Markdown for writing content using this theme. In particular, list syntax can really knot things up.
<!--more-->

### Mathjax improperly parsing greater and less than and ampersands inside blocks

The mathjax HTML ```<head>``` scripts have been modified to properly render block style mathjax expressions inside a ```$$ ... $$``` set of character pairs,
using the standard Kramdown parser. Some examples sent to me by Quxiaofeng are now parsing correctly, I believe.

This code:

```latex
$$
  D = \left(\begin{matrix}
  1 & -1 & & & & \\
  &    & \cdots &   & \\
  &    &        & 1 & -1
 \end{matrix}
 \right)
$$
```
yields this:

$$
D = \left(\begin{matrix}
  1 & -1 & & & & \\
  &    & \cdots &   & \\
  &    &        & 1 & -1
\end{matrix}
\right)
$$

Other examples from the [wikia Tex reference](http://latex.wikia.com/wiki/Matrix_environments):

$$
\begin{matrix}
\alpha& \beta^{*}\\
\gamma^{*}& \delta
\end{matrix}
$$


$$
\begin{bmatrix}
\alpha& \beta^{*}\\
\gamma^{*}& \delta
\end{bmatrix}
$$

$$
\begin{Bmatrix}
\alpha& \beta^{*}\\
\gamma^{*}& \delta
\end{Bmatrix}
$$

$$
\begin{vmatrix}
\alpha& \beta^{*}\\
\gamma^{*}& \delta
\end{vmatrix}
$$

$$
\begin{Vmatrix}
\alpha& \beta^{*}\\
\gamma^{*}& \delta
\end{Vmatrix}
$$

$$
\begin{Vmatrix}
\alpha& \beta^{*}\\
\gamma^{*}& \delta
\end{Vmatrix}
$$

However, a problem still exists for inline matrix notation, from an example [here](https://en.wikibooks.org/wiki/LaTeX/Mathematics#Matrices_in_running_text):

A matrix in text must be set smaller: $$ \bigl(\begin{smallmatrix}a & b \\ c & d\end{smallmatrix} \bigr) $$ to not increase leading in a portion of text. The way this inline matrix is written is: ```$$ \bigl(\begin{smallmatrix}a & b \\ c & d\end{smallmatrix} \bigr) $$```

## Edge Case 1 from Quxiaofeng:

### No blank lines between Markdown list items

The issue arises when sidenotes and marginnotes are put into list items.  As mentioned in the main documentation page, lists can be problematic not only for semantic clarity, but also because they can creating formatting issues. For example:

### Related algorithms

+ Split Bregman iteration {% sidenote 1 'Goldstein, T. and Osher, S. (2009). The split Bregman method for l1-regularized problems. SIAM J. Img. Sci., 2:323-343.' %}
+ Dykstra's alternating projection algorithm {% sidenote 2 'Dykstra, R. L. (1983). An algorithm for restricted least squares regression. J. Amer. Statist. Assoc., 78(384):837-842.' %}
+ Proximal point algorithm applied to the dual
+ Numerous applications in statistics and machine learning: lasso, gen. lasso, graphical lasso, (overlapping) group lasso, ...
+ Embraces distributed computing for big data {% sidenote 3 'Boyd, S., Parikh, N., Chu, E., Peleato, B., and Eckstein, J. (2011). Distributed optimization and statistical learning via the alternating direction method of multipliers. Found. Trends Mach. learn., 3(1):1-122.' %}

### Why this matters

Notice how the sidenotes display properly, but the fact that sidenotes have more display 'volume' than the list items themselves causes a horizontal mismatch between the sidenote item's number and its corresponding list item.

Please note that there must be *no blank lines between your list items*. This is due to a really strange thing about the Jekyll Markdown engine I have never noticed before. If you have a list, and you put a blank line between the items like this:

```
  + list item 1

  + list item 2
```

It will create an html tag structure like this:

```
<ul>
   <li>
      <p>list item 1</p>
  </li>
  <li>
      <p>list item 2</p>
   </li>
</ul>
```
Which *totally* goofs up the layout CSS.

However, if your Markdown is this:

```
    + list item 1
    + list item 2
```

It will create a tag structure like this:

```
<ul>
   <li>list item 1</li>
   <li>list item 2</li>
</ul>
```

Here is the same content as above, with a blank line separating the list items. Notice how the sidenotes get squashed into the main content area:


### Remarks on ADMM version 2 - **one blank line** between Markdown list items

Related algorithms

+ Split Bregman iteration {% sidenote 1 'Goldstein, T. and Osher, S. (2009). The split Bregman method for l1-regularized problems. SIAM J. Img. Sci., 2:323-343.' %}

+ Dykstra's alternating projection algorithm {% sidenote 2 'Dykstra, R. L. (1983). An algorithm for restricted least squares regression. J. Amer. Statist. Assoc., 78(384):837-842.' %}

+ Proximal point algorithm applied to the dual

+ Numerous applications in statistics and machine learning: lasso, gen. lasso, graphical lasso, (overlapping) group lasso, ...
<br>
<br>
<br>
<br>

### Liquid tag parsing strangeness

Example of the proper way to write an url inside a *Liquid* full-width image tag.

This code: ```{{ '{% fullwidth "assets/img/rhino.png" "Tuftes pet rhino (via <a href=\"//www.edwardtufte.com/tufte/\">Edward Tufte</a>)" ' }} %}```

produces the following image with a title. Notice that I have had to escape the double quotes in the HTML with a backslash. Also, the example above leaves out the single quote in 'Tufte's" because of the topsy-turvy way that you have to escape the escapes in code sections that are used for illustrative purposes in this text. Bottom line is that there are occasionally some odd interactions between the Markdown parser, custom *Liquid* tags and HTML.
{% fullwidth "assets/img/rhino.png" "Tufte's pet rhino (via <a href=\"//www.edwardtufte.com/tufte/\">Edward Tufte</a>)" %}
