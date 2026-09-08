blueticks Solutions — landing page
==================================

Plain HTML, CSS and JavaScript. No build step, no Node, nothing to install.


HOW TO PUT IT ONLINE (Hostinger)
--------------------------------
1. Log in to hPanel and open File Manager.
2. Go into public_html.
3. Upload blueticks-landing.zip there.
4. Right-click the zip and choose Extract.
5. Make sure index.html sits directly inside public_html, NOT inside a
   folder — the address bar should show .../public_html/index.html.
   If the extract created a folder, open it, select everything (including
   the hidden .htaccess file — "select all" does not catch hidden files,
   tick it separately), Move, single-click ".." once, then MOVE.
6. Delete the zip and the leftover empty folder.

No domain yet? Hostinger gives every account a temporary preview address
(something like yoursite.preview-domain.com) in hPanel. The site works on
it exactly the same. When the real domain is pointed at the hosting,
nothing here needs changing.


WHAT'S IN HERE
--------------
  index.html          The whole page — copy, styles and script in one file.
  assets/             Video, poster image, favicon. See assets/README.txt
                      for the two placeholder videos to replace.
  .htaccess           Compression and caching. Harmless if Hostinger
                      ignores any part of it.


THE ?for= LINKS (for email campaigns)
-------------------------------------
Same page, different first impression, depending on the link you send:

  yoursite.com/?for=local
      Headline becomes the plumber line, and the page scrolls itself
      down to the local-business section with a soft highlight.

  yoursite.com/?for=shopify
      Headline becomes the "why is it so quiet in there" line, and it
      scrolls to the Shopify section instead.

  yoursite.com
      The general headline, no auto-scroll.

So local-business emails get the first link, Shopify sellers get the
second, and both land on the part of the page that speaks to them.


THINGS YOU MIGHT WANT TO EDIT
-----------------------------
Everything is in index.html and it's plain English — search for the text
you want to change and type over it.

  WhatsApp number   search for   923005521519      (appears 6 times)
  Email address     search for   bluetickssolutions@gmail.com
  LinkedIn URL      search for   linkedin.com/company
  Colours           search for   :root                 (top of the file)


WHERE THE CONTACT FORM ENQUIRIES GO
-----------------------------------
On Netlify (where the site is now): Netlify Forms catches them.

Nothing to install — the form already has the right markup. But two
things have to happen once:

  1. REDEPLOY the site with this version of index.html. Netlify only
     notices a form when it scans a fresh deploy. Until you redeploy,
     the form falls back to opening the visitor's email app.

  2. Turn on the email alert. In Netlify:
        Site configuration > Forms > Form notifications
        > Add notification > Email notification
        > send to bluetickssolutions@gmail.com

After that, every enquiry lands in two places: your Netlify dashboard
under Forms > contact (a proper list you can search and export to CSV),
and your inbox.

Free plan allows 100 submissions a month, which is plenty to start.
Spam is handled by a hidden honeypot field — you'll never see the bots.

To check the list: Netlify dashboard > your site > Forms > contact.


IF THE SITE EVER MOVES TO HOSTINGER
-----------------------------------
Netlify Forms only works on Netlify. Hostinger runs PHP instead, so:

  1. Upload hostinger-only/contact.php into public_html, next to
     index.html.
  2. In index.html find this line (near the bottom, in the script):

        var FORM_ENDPOINT = '';

     change it to:

        var FORM_ENDPOINT = 'contact.php';

  3. Open contact.php and set $MAIL_FROM to a real mailbox on your own
     domain (create one in hPanel). Shared hosts reject mail that claims
     to come from a gmail.com address.

Every enquiry then gets written to .data/submissions.json on your hosting
BEFORE the email is attempted — so even if the mail server has a bad day,
nothing is lost. The .htaccess in here already blocks the public from
reading that folder.


THE SAFETY NET
--------------
Whichever of the two is running, if the form can't reach it the page
quietly falls back to opening the visitor's own email app with the
message already written. An enquiry is never just silently dropped.

And WhatsApp is on the page five different ways — for most visitors
that's still the one they'll actually use.
