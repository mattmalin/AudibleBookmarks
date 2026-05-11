# Audible Bookmarks
Tools for easily extracting bookmarks and notes in note-friendly formatting.

### Audible Book to Player
From the Audible book page to the web player for that book. This is equivalent to clicking "Play" on the page, with added convenience of it not opening in a new reduced window, allowing bookmarklets to still be available in the main browser window.

Which bookmarklet you will need depends on the top-level domain (TLD) of the Audible site you use.
- For audible.co.uk: <a href='javascript:location.href=location.href.replace(/\?.+/,"").replace(/.co.uk\/.+\//,".co.uk/webplayer?asin=");'>Audible Book to Player</a> <- Drag this to bookmarks bar to use.
- For audible.com: <a href='javascript:location.href=location.href.replace(/\?.+/,"").replace(/.com\/.+\//,".com/webplayer?asin=");'>Audible Book to Player</a> <- Drag this to bookmarks bar to use.
- For other TLDs (eg audible.in, audible.cn), drag the .co.uk one above to bookmarks bar and replace .co.uk with the TLD you use (eg .in, .cn, etc) in both places it occurs.

### Audible Bookmarks - updated for early 2026 Audible website changes
From the audible cloud player in browser for the audiobook needed, pause the player (if you want), wait for it to load then click `...` on the page, followed by `Bookmarks` from the list that appears. When your bookmarks then load, click on this bookmarklet, and the notes will be copied to clipboard in a concise markdown format.

**Copy paste the below as a link for the bookmarklet**
```javascript
javascript:(function(){allBookmarks=document.querySelectorAll('li[class*="bookmarkItemContainer"]'),allBookmarksFormatted="",allBookmarks.forEach(o=>{chapterAndTimeStamp=o.querySelector('div[class*="bookmarkItemSection"]').innerText,bookmarkNoteText=o.querySelector('adbl-text-block[class*="bookmarkItemNote"]')?.innerText??'',formattedFullBookmarkNote='"'+bookmarkNoteText.trim()+'"\r\n*'+chapterAndTimeStamp.trim()+"*",bookmarkNoteText.trim().length>0&&(allBookmarksFormatted=allBookmarksFormatted+"\r\n\r\n"+formattedFullBookmarkNote)}),allBookmarks[0].focus(),navigator.clipboard.writeText(allBookmarksFormatted)})()
```
