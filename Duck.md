Settings supports themes etc. Allow user contirbuted themes via github. Package using bower and dsitrbute that way. 

Look to land-book for inspiration of landing, sign up, billing etc. For design of main bit of app a lot like soulver + medium. Very simple icon drop downs with settings. Split app into front-end, front-end app and backend APP with API. All bits and pieces should be split up so we can roll out bit by bit

Pricing wise keep it $5 or under. 

The feature that would make me use it is if it pulled from and could push to a Dropbox folder.
When one saves a doc it should actually save with the => sign on the line below and then output that into the sidebar.
That means the synced files are usable in plaintext. When we upload to it shouldn't take the webapp to make changes it should parse and spit it back out to the Dropbox folder. Browser side it always recalculates in case user is made changes to output.

Server side implement parsing use parselet. Client side use Jison (faster than peg.js).

### Features (remember to launch with minimal functionality)

- Sharing (privately and with another user)
- Themes
- Save note (should work offline). will be really simple so we ultimate just get a list of content items (like medium or Roon. And then a new Note button).
- Constants (define in settings. Also saves as text file so you can import and share on gists etc automcomplete using Codemirror autocompletion)
- Export to PDf and static page (would be nice to do client side)
- share public page 
- users can fork a shared page (public or private) make changes and merge them together.
- conversions (use js-quantities)w
- need some way to tell it to take quantity from previous line. maybe just PREV constant? Like an automatic variable?
- a way to graph things (grapher like language. example is https://github.com/kevinmehall/EquationExplorer. the key to is to make lines go further than one line. or just popup to see full calulcation?. yeah would mess with layout too much so you'd click an icon to see the graph. How do we detect graph equation? maybe just a function syntax? call function graph() to do it? yeah functions would be best. )
- Integration with OpenOffice or Word
- Integration in PowerPoint
- Integrate Evernote
- Share via web (web service that displays it via short url) Two columns. Maybe in the future even fully
- editable via the web
- Dropbox
- Export PDF
- We can use intelligent parsing to export as spreadsheet
- Share via email
- Simple droplr saving
- Killer feature make better version for this http://bjango.com/articles/soulver/

best demonstration would be a public page. users can then fork it to start their own. 

### Implementation

PrivateBackend stuff like sign ups, billing, etc happens in API first Grape + Sinatra app.

Then there is a public facing API app that handles importation, server side parsing data storing etc. 

Editor (text for note, side bar, graphing popup, theme styling etc) happens in a self-contained JS/CSS app packaged using rubygems and bower.

Themes a self-contained bower distributed package.

Main app that renders frontedn loads everything, communicates with API etc is a padrino app.
I think we can put in the the js that loads edito etc right in this app. Not much can be split out. Actually we should
split out frontend models for saving, settings, accounts etc. That can be a sepperate frontend app distributed through bower.

Share data with three rubyapps through gems. 

Should start with wrapping my head around Jison first.
Probably best order is; the editor, then themes, then private backend, public frontend, models JS, then main app.

For the themes we use our favorite coding themes as starting point. Tomorrow and Solarized FTW!

### Ideas

Should name app slightly differently than the mathematician to make for easy googling. Erdoes? Erds? Erdose? Erdus?

### Artificial Scarcity with bunnies

I need my first 1000 users to become profitable.  Why should I rob later users to pay
for my early adopters.

Release/do various things when signups occur

Various ideas;

After 100 signups the logo will change to a bunny

We can title the post submission something clever to. Like: "How I would have tricked you into signing up." or
"I need a thousand users. Here's how I was going to trick you into be one"

### 1 Bitcoin for life.

One bitcoin in exchange for lifetime account. Entitles user to lifetime free webapp; coupon codes for everything else.Run promo forever. 
