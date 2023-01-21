# AudibleBookmarks
Tools for easily extracting bookmarks and notes in note-friendly formatting.



## Audible Bookmarks bookmarklets
These are two useful bookmarklets which helps with the journey of extracting and saving audiobook bookmarks notes and clips from audible. This is tailored to use audible.co.uk so far, although can easily be adapted for other regions.

These bookmarklets are quick and dirty - I am not an advanced JavaScript developer and it's hastily complied so far for just my use case and desired Markdown formatting - this may be expanded in future. If you have suggestions or code improvements, please do raise an issue or pull request so this can develop into something more robust and flexible for the needs of others.


### Audible Book to Player
From the Audible book page to the web player for that book. This is equivalent to clicking "Play" on the page, with added convenience of it not opening in a new reduced window, allowing bookmarklets to still be available in the main browser window.

<a href="javascript:location.href=location.href.replace(/\?.+/,"").replace(/.co.uk\/.+\//,".co.uk/webplayer?asin=");">Audible Book to Player</a> <- Drag this to bookmarks bar to use.


### Audible Bookmarks
From the audible cloud player in browser for the audiobook needed, pause the player (if you want), wait for it to load then click `...` on the page, followed by `Bookmarks` from the list that appears. When your bookmarks then load, click on this bookmarklet, and the notes will be copied to clipboard in a concise markdown format.

NOTE! The default audible view for bookmark clips/note is from most recently created at the top to oldest at the bottom. Since bookmarks are typically created in order of listening, this also reverses the order of the notes from the page to a more sensible order.

<a href="javascript:(function(){allBookmarks=[...document.querySelectorAll(..adblCpBookmarkArea:not(#adbl-cp-bookmark-list-row-\\{0\\}.)].reverse(),allBookmarksFormatted=..,allBookmarks.forEach((o=>{chapterAndTimeStamp=o.querySelector(..adblCpBookmarkPosition.).innerText,bookmarkNoteText=o.querySelector(..adblCpBookmarkNote.).innerText,bookmarkLinkAddress=o.querySelector(..adblCpBookmarkStart.).href,formattedFullBookmarkNote='.'+bookmarkNoteText.trim()+'.\r\n*'+chapterAndTimeStamp.trim()+. - [Bookmark Link](.+bookmarkLinkAddress+.)*.,bookmarkNoteText.trim().length>0&&(allBookmarksFormatted=allBookmarksFormatted+.\r\n\r\n.+formattedFullBookmarkNote)})),allBookmarks[0].focus(),navigator.clipboard.writeText(allBookmarksFormatted);})()">Audible Bookmarks</a> <- Drag this to bookmarks bar to use.


