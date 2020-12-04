# PEN-300 OSEP Blog
This is a blog to put thoughts, feedback, frustrations, and the like as I work through OffSec's PEN-300 and prep for OSEP. I always found detailed blogs and feedback from other students useful while pursuing OSCP and ye olde OSCE, so I thought I'd put this on my GH so others can get a feel for this new course.

*Note: I am making every effort to not reveal any info I shouldn't in this doc. If you see anything that you think shouldn't be included in here, esp if it could possibly breach OffSec's academic integrity policy, please let me know ASAP and I will modify.*

## Overall Notes
### Experience
I'm starting this after completing OSCP (2017-2018), ye olde OSCE (2018-2019), and the AWAE course (in-progress). I have about 2.5 years of official offensive security experience and another year of serious training before that prepping for OSCP. Half a year was an internal offsec team and the other 2 years was in consulting. While I'm very determined, I don't consider myself particularly gifted. I failed OSCP twice and OSCE three times.

### Notes on PEN-300
- I wish it would have at least touched on macOS and/or cloud, considering many newer companies have one or both of those (sometimes with no Windows footprint at all).

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

#### Goofs
- 3.6.1 paragraph 1 grammar error last sentence
