# Code-Editor Deconstruction Project

## Summary
Download the code editor source code from w3schools.com and deconstruct the code to build a customized local editor.

## Rationale
The first reason for this project is examples from one of the Udemy course videos for web development. One of the best ways to learn how to code is to find how others have created their sites. The course states to open a website, then F12 to break the site. Some issues with that are the requirement for an internet connection, and, for newer developers, they may not have an idea where to start.

## Issues
We tried using online code editors when testing code; a storm knocked out power, disabling internet service. This project took several days to complete; there was a lot of frustration as this is much harder to accomplish than building from scratch. Additionally, code will break as items are removed; however, run as intended as additional code is removed.

We tried to build our own console, tried CodeMirror, and tried tearing Sublime and Brackets a new one as we did to N++ [https://honestlee.info/how-to/customize/npp]; all options failed miserably. We researched other options and found W3Schools has the best editor, even after finding websites that plagiarized W3’s pages.

Another issue we faced was the lack of Font awesome. Although we were able to link to FA without a signup, major corporations pay extra for the other fonts. We typically use Bootstrap and find the code more compact and easier to manipulate. Nevertheless, we created an account.

As we linked to the FA resource, we saw that the orientation icon (mobile phone with lines) did not exist and would need to pay to access. We added our link to the head and saw not all icons would render. We tried changing encoding, trying to link to W3, to find the solution is to use a CDN.

One of the problems faced was that, instead of coding it right, W3 was lazy and created a combination of concerns by using internal and inline styling and scripts. There were MANY lines in the files that contained the dreadful !important. If we need to use that, then there is improper code, or improper order.

There are many moving parts; we created a list of tests to check. We were almost done to find out we removed the cursors line and had to rework several steps behind. It was at this point we created the documentation to learn from our mistakes.

During testing our deconstruction, we found that using Chrome keeps a cache and running edited code was not happening without having to clear the browsing history. Instead of having to copy the path inside a manually-opened Chrome Incognito tab, we edited out N++ shortcuts.xml (see our tutorials) to include this line to create a “Chrome-nito” run option
<pre>&lt;Command name=”Chrome-nito” Ctrl=”no” Alt=”no” Shift=”no” Key=”0”>chrome “http://localhost/redirect.php?file=$(FULL_CURRENT_PATH)” -incognito”&lt;/Command></pre>

However, this still fails to refresh each time and end up using a different browser to ensure changes.

## Testing
We all should be using testing techniques before sending our product out to the world (although some of the worst UI/UX sites rank top on search results). However, we have no quick way to run code snippets; we must create a new HTML file or copy one, open a text editor, then edit and test as usual.

There are many options for text editors; Notepad++ (N++), Brackets, and Sublime were mentioned the most in the Udemy web courses. N++ was the only text editor we used beforehand and had no idea about Sublime or Brackets until recently. Once taking the courses, and practicing a bit, we found that all three are really needed for a full testing experience. We wrote tutorials at https://honestlee.info/how-to on how to install and configure N++ for WampServer (among others).

## Editor
None offer the perfect solution singly; the consoles in Brackets and Sublime are either not user friendly or cannot perform certain tasks efficiently (e.g., running PHP, some JS). Therefore, we installed all three and will utilize each for specific tasks using the stolen code editor to test our code and snippets without the need to create a new file.

## Process
Instead of just tearing the code editor apart and posting the final product, we decided to record the steps. This helps new developers review steps on ways to solve issues and to use Git as a way for senior developers to review our process and provide feedback as to what we should and should not be doing as we are fairly new developers ourselves.

## Result
This solved our problem of testing code snippets without internet service. This also allows us to help others, help ourselves, and to brag about what legal issues we are facing by doing what we just did (i.e., “show your work”). As for code itself, we were able to reduce the entire project down to (in lines): HTML = 85 | CSS = 90 | JS = 7,764 | Total = 7,939. The total lines used for the entire app, without customization, is over 3000 lines less than the number of lines used in the base JS!

#                            Steps Taken to Solve This Problem

## Save the Source Code
Go to W3schools.com, click Try it Yourself, and use Ctrl+S to save the files to a testing folder. Using different browsers and at different times offers different downloads; one download contained over 6,000 lines in the HTML file (app. 5000 were Google). Rename to a simple name, such as Editor.html.

## Use Code as Base
Now we have a base, create a new folder and name it 0Base. We will leave the base alone as a backup and make a copy to edit. Note, we are NOT changing any file names, only creating a folder named to that step then copying the last step inside henceforth.

## Step 0 – Base Contents
When saving a website, an HTML file will be separate to a folder named with the download name followed by _files (Ex. Editor_files). We started with 82 files in the folder and 1106 lines/46,292 chars in the HTML file. 

## Step 1 – Cleanup HTML
Our first task is to go through to remove all unnecessary meta and tags (Ex. og:image tags, Google ads/tag manager) and to separate code for readability (if needed). Keep lines as-is, do NOT move lines around yet!

## Step 2 – Remove Unused Files
Once the code can be read easily, we can go through the HTML file to locate any linked files located in the folder that were included and omit the rest cascading top-down. After this task, we were left with 47 files. 

## Step 3 – Remove Extra Spaces
As we examine the HTML, we find MANY extra spaces, we edited to remove ONLY double spaces; this is our note:
> *After opening all needed files in N++, removed extra spaces<br>
2x spaces alone were 88,266 chars <br>
The last is our note to separate the internal CSS to an external sheet for Separation of Concerns.

## Step 4 – Remove Additional Files
The next step starts with the harder parts, removing all unneeded files and fixing anything that breaks. It was at this point that the outcome would change, or we would not know that omitting certain code broke other aspects. We ran through Step 2 again, removing more unused files; at the end of this, we had 8 files.

This section took days to complete as the code would break, but not understanding the code fully at this point made us rework it, then finally forced ourselves to keep going. It was then we realized we were right, we just had to strip it down.

## Step 5 – Repeat
Since we had enough of that step, we saved, then we ran through Step 2 again to find any more unused files. Since we created an external sheet, we have an extra file. Nonetheless, after this step, we were left with only three files.

## Step 6 – Clean HTML 
This step cleans up the HTML; this removes most deprecated, outdated, or improper code used. This also includes fixing the broken FA icon that we cannot access. The only icon that comes close is the columns. It was at this point that we had an idea and rotated an icon for later use.

Additionally, W3 used javascript:void(0). Not being familiar with this, we decided to research instead of just using it. We already noticed the poor coding practices and thought to examine before continuing. As an idea, a quick search revealed:

> **Should I use void 0?**
<br>Generally, you want to avoid href="javascript:void(0)" as it will cause the browser to parse the value of the link URL, which is both costly and unnecessary

## Step 7 – Clean JS 
Which leads us to the next, tedious, and excruciating part, going through the 9000 lines of JavaScript. Considering we did not truly have to worry about interactivity until now, we did not concern ourselves with any scripts. We found A LOT of the scripts were Google ads; Code mirror alone (w/comments) is 11,345 lines.

Notes included regex for removing comments. Research on this subject alone took several hours. This section took testing to the maximum extent. One note was to test all functionality: copy/paste/min/max/ resize H/ resizeV/drag/omit/mode/reset/overflow/fonts/icons/results/omit+create

There were other options we tried that took many hours; the option is to mark (Ctrl+M), then keep the dialog open, go through, then search entire document and other tedious, useless, and wasteful options found online.

This step also included removing lines with single characters; specifically over 100 lines with a single }. While there may still be a lot of code that can be omitted or edited, there is just too much for this type of project and will go into customizing.

## Step 8 – Clean CSS and Customizing
These are general notes taken during this part. This part of the process cleans the CSS while we go through and edit code for customization. We left this section last as it is a complicated task that affects other concerns; yet easiest to fix.

W3 has a save, it links to their site, and a home button. Instead of removing them, we changed the home button for a refresh (instead of using the browser refresh), added our own orientation icon using an onclick event to rotate the icon); the same was done for the theme.

We kept the save, but instead created a script that saves the file as index.html to the local system; finally added a trash icon in Editor that dumps the current code without refreshing the page.

Think about interaction. Each time we open an app, each time we visit the main page of a website, we have a type of welcome. The problem with this code editor is that script is populated on load; this script is hard-coded, meaning that each time the page refreshes, it displays the default script.

We did not plan on a second sheet; however, as we played in the sandbox, we found UI/UX went bad. All we needed to do was copy the current HTML, remove the dummy text, edit a few items, rename and we had a blank template.

A mistake was made that turned out to be accurate. When clicking the script option, the cursor default bottom is the end of the script tag (click anywhere below </ script>). We should never place code after this; the downloaded code had 10 iframes after </body>!. They buried it so well we could not even find it by sight; we needed to use N++.

Because the HTML is the page, the default cursor is a new line under </style>.

As for customizing, we just chose colors, spent hours testing variations and what we can use in the files provided. We can go much farther than what we have done; however, is a bit much for this.

# User Guide
This section details how to use the editor.

## Open the Editor
Run Editor.html; once open, there will be a note to the right of Template Options to let users know what template is used and relative notes. A basic template is populated that allows users to use this as a boilerplate template HTML file or to edit ad-hoc.

Clicking HTML replaces the template with style tags. This code editor does NOT require the header and head to run and encourages users to utilize internal over inline CSS. Clicking JavaScript is the same as HTML, instead using script tags; notes to assist.

## Blank.html
When in Editor (main) page, there is a third option, Blank. When clicking, it opens to a page with no placeholder. The user writes their own code or chooses the HTML or JavaScript template. Additionally, this is the last page; in lieu of Blank, we used Both so the user can use CSS and JavaScript immediately without having to copy to the editor.

There is no return built to go back to the main page as Blank.html is the actual goal of this project; if wanting to go back, use the browser Back button.

## Options
The navbar offers more options than W3. Although there are tips when hovering, we will discuss each.

The refresh W3 used contained the void statement; we researched and another option (again, not best practices) was to use href=”#”. Instead, we are using window.location.href= window.location.href to reload itself. When in Editor, as noted, clicking Refresh loads boilerplate; Blank is blank.

The next option is orientation. We are using the opposite configuration so the view will be to landscape when viewing portrait and vice-versa.

The same is for dark/light mode; the icon is opposite of the view.

Run will run whatever is in the editor.

The next is the save option. We need to register to use the W3 option; therefore, coded a way to save this as index.html.

Finally, because we need a way to reset Editor, we created a trash that clears the editor without loading the boilerplate (it took us several hours to find this solution); no option in Blank as refresh clears all.

## Easter Eggs
Throughout some of our projects we added hidden extras, or what some refer to as unborn chickens on the first Sunday after the full moon that occurs on or after the spring equinox…however negated by our credibility statement at https://honestlee.info/ 
> *We strive to be [somewhat] professional in all our pages and provide information without unnecessary commentary and hold ourselves to [some type of] high academic and professional standards.<br>We will, nevertheless, on some occasions, quite possibly, perhaps throw in some humor intermittently, inconspicuously, and intentionally appearing ignorant. We do not regret this decision; however, both rue and lament it.*

Watching *The Big Bang Theory* The Re-Entry Minimization, Amy and Leonard were trying to find Waldo without their glasses, and we thought, why not bury Waldo somewhere in the code?

For this project, we decided on WALDO, split into five pieces. The only hint is it they are an inline comment surrounded by an HTML comment, encapsulated in a multi-line CSS comment buried somewhere in the four pages.

We have other projects that will be added, if possible, that will also include Waldo buried in code, as well as one buried in a binary calculator we built in Excel.

Unfortunately, we keep getting denied by Google for AdSense; we were going to offer $50 to the first 10 people that found all Easter Eggs if we were able to make $1000 on our site, which we may be losing soon.