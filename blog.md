# PEN-300 OSEP Blog
This is a blog to put thoughts, feedback, frustrations, and the like as I work through OffSec's PEN-300 and prep for OSEP. I always found detailed blogs and feedback from other students useful while pursuing OSCP and ye olde OSCE, so I thought I'd put this on my GH so others can get a feel for this new course.

*Note: I am making every effort to not reveal any info I shouldn't in this doc. If you see anything that you think shouldn't be included in here, esp if it could possibly breach OffSec's academic integrity policy, please let me know ASAP and I will modify.*

## Overall Notes
### Experience
I'm starting this after completing OSCP (2017-2018), ye olde OSCE (2018-2019), and the AWAE course (in-progress). I have about 2.5 years of official offensive security experience and another year of serious training before that prepping for OSCP. Half a year was an internal offsec team and the other 2 years was in consulting. While I'm very determined, I don't consider myself particularly gifted. I failed OSCP twice and OSCE three times.

### Notes on PEN-300
- I wish it would have at least touched on macOS and/or cloud, considering many newer companies have one or both of those (sometimes with no Windows footprint at all).
- I like how it favors the line-upon-line approach, and the exercises generally follow the content (except just a little further to ensure you aren't just cp/pasting code)
- It would be great if they'd add the ability to do 1.2x, 1.5x, 2.0x, etc. for the videos, as the speaking is fairly slow. Slow is ok for the first time around but when you're looking back for something specific it is agonizing. For now I use this (from my friend Jacob Skiba):
```
javascript:(function(){v = document.getElementsByTagName("video")[0]; if (!v) { alert("Cannot find video tag"); return } ; i = prompt("Enter a video speed\n(example: .5, 1 (default), 2.3)"); if (isNaN(i) || parseInt(i) <= 0) { alert("Must enter a positive number"); return } else { v.playbackRate = i; console.log("New speed: "+ v.playbackRate); v.play(); return }})()
```

## Course Sections
### 1. Evasion Techniques and Breaching Defenses: General Course Information
Overview of the course was typical. I like how they defined pentest (external vs internal) and red team engagement. I'm sure some would disagree with their definitions but I liked the clarity of what they said.

### 2. Operating System and Programming Theory
Fairly basic programming info towards the beginning. Not meant to be anything groundbreaking. But good for folks who don't have a strong coding background (like me). Gives plenty of wiki links for more info.

I appreciated the Windows-specific info related to WOW64, Win32 APIs, and the registry. I'd worked with APIs and stuff before in shellcode but this gave some theory/context info.

### 3. Client Side Code Execution With Office
#### I liked
Solid overall, gave some good ideas for phishing pretexts and a methodical, line-by-line approach to crafting good poisoned documents. I liked how they explained WinAPIs well and how shellcode runners are created in-depth.

#### I did not like
This will probably be a recurring theme, but I wish other C2 frameworks were introduced instead of MSF only. Also, tons of orgs have been watching for `DownloadString`, `IEX`, and similar techniques so...

#### Pain points and stuff to review
- 3.6 got pretty crunchy and I need to go over it again

#### Goofs
- 3.6.1 paragraph 1 grammar error last sentence

### 4. Client Side Code Execution With Windows Script Host
#### I liked
I don't have a lot of experience with SE, so this was a great module. I like how it touched on Sharpshooter and some great frameworks, BUT it gave a solid understanding of the underlying techniques so we can modify the automated tools as-needed for evasion.

### 5. Process Injection and Migration
#### I liked
Explanation of all the techniques were good (with the exception of reflective PE injection...but I'm ok with that). I feel confident in my understanding of process injection, DLL injection, and hollowing after this section.

#### I did not like

#### Pain points and stuff to review
- 5.1.2.1 - do #3 "the right way" -- I used reflection/assembly.load for the sake of time, but I should translate all the APIs into powershell.
- Go back and do 5.1.2.2 Extra Mile. Looks very useful.

#### Goofs

### 6. Introduction to Antivirus Evasion
#### I liked
The techniques were cool and fairly simple to implement. It was great to walk out with some Defender-killing techniques. The heuristics bypasses were really interesting.

I like how the theory of AV tools was discussed and how the exercises were relevant and got you thinking about how to bypass. This was in positive stark contrast to ye olde OSCE.

#### I did not like

#### Pain points and stuff to review

#### Goofs
- p.159, grammar goof - "The most complicated approach is to reverse-engineering the antivirus..."
- p.184, capitalization error - "As for VirtualALlocEx,..."

### 7. Advanced Antivirus Evasion
#### I liked
I loved how they went over Windbg in a very approachable way. It somehow made things a bit easier when moving from x86 debuggers (Immunity, Olly, etc.). The AMSI theory was excellent and helped me to understand it much better. The AMSI bypass examples were exceptional and paved the way for developing your own.

#### I did not like

#### Pain points and stuff to review
- Should really review the Jscript AMSI section and do/redo the exercises. DotNetToJscript wasn't working super great for some reason, so I glossed over it a bit.
- Also, check sharpshooter with AMSI bypass. Need to get that working.

#### Goofs
- In 7.1.1, mention that you should connect to the `defender` host, not the `dev` host. I poked around on `dev` looking for Windbg and it wasn't there. Better yet, just have Windbg on both (not sure why you wouldn't have it on the `dev` machine :D)

### 8. Application Whitelisting
#### I liked
A bunch of great methods to bypass default AppLocker rules, and more advanced ones. This was an excellent section, and I feel armed to face even more intense AppLocker policies.

#### I did not like
Not sure why but it felt like this section wouldn't end. Good and bad I suppose. The later part with `Microsoft.Workflow.Compiler.exe` was just something I glossed over and didn't really go over. I thought it's something I'll go for when/if I need it.

#### Pain points and stuff to review
- Need to do 8.4.5.2 Extra Mile...and really that whole 8.4.5 section.
