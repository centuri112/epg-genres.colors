epg-genres.colors
=================


How to give your EPG genre color in XBMC.

I want to give EPG genre color and be able to customize the color to the genre names. So I found a way that will allow XBMC to put epg genre colors to any skins despite which back-end or XMLTV you use. This will require little editing in the skin.  If you feel uncomfortable on editing a skin, you might want to email the skin creator and have them see this instruction and ask if they can do this for you.

I've tested this in 4 skins:

Skins Tested:
ACE
AEON NOX
Back Row
Confluence

First step is to find the file to edit. Below are the 4 I have done and there paths. Note: For other skins should follow the same path but depends on what they call the PVR filename.  If you can't find the file you might want to email the skin creator. 

Skins path and filename

	ACE
	\Users\Username\AppData\Roaming\XMBC\Addon\skin.ace\720p\ViewsLiveTV.xml
	
	AEON NOX
	\Users\Username\AppData\Roaming\XMBC\Addon\skin.aeon.nox\1080i\Includes_PVR.xm.
	
	Back Row
	\Users\Username\AppData\Roaming\XMBC\Addon\skin.back.row\720p\ViewsPVR.xml		
	
	Confluence
	\Program Files (x86)\XMBC\Addon\skin.confluence\720p\ViewsPVR.xml

Open the file in any text editor and search for the lines below. These lines are in the file twice so you will have to replace them both.

For ACE search for
<texture border="3">genres/$INFO[ListItem.Property(GenreType)].png</texture>

For AEON NOX search for
<texture border="4">$INFO[ListItem.Property(GenreType),epg-genres/,.png]</texture>

For Back Row search for
<texture border="3">genres/$INFO[ListItem.Property(GenreType)].png</texture>

For Confluence search for
<texture border="3">genres/$INFO[ListItem.Property(GenreType)].png</texture>

Change them to (Remember need to do this twice)
<texture border="3">epg-genres/$INFO[ListItem.Genre].png</texture>

Save file once you change both lines.

Second step need to add a epg- genre folder in the skins media folder	

	ACE
    \Users\Username\AppData\Roaming\XMBC\Addon\skin.ace\media

	AEON NOX
	\Users\Username\AppData\Roaming\XMBC\Addon\skin.aeon.nox\media
	
	Back Row
	\Users\Username\AppData\Roaming\XMBC\Addon\skin.back.row\media
	
	Confluence
	\Program Files (x86)\XMBC\Addon\skin.confluence\media
		
And add this file in the media folder
	
	epg-genres
	
In the epg-genre folder is the Genre color with Genre name.  

In order for this to work you will have to restart XBMC.  If you do any changes example: change color or add/change the genre name you will have to restart XBMC to show the changes in the EPG.

When you rename a file you can not use some special charaters example /  windows will not let you use this character or others but you can use dash.  

This is a good fix till something better comes along.  Maybe some one can make a addon.  I'm trying to lean how to write an addon but I think there is not away to access the genre list from the XBMC code. If there is a way please PM me. There is not much detail on addon access to XBMC.

That is it. Enjoy your color EPG Genre.

Special Note about EPG Genre:
	The EPG Data I am using is MediaPortal backend with Argus TV using XMLTV Schedule Direct.  The XMLTV file you use might have different genre names so you will have to edit the color genre names to fit your XMLTV Genre. One thing you should know that some PVR addon handle genre different.  Most XMLTV list shows with more than one genre example the show “Castle”  genre is ”Comedy Crime Drama Series”.  Some clients only see the first Genre so Castle is “Comedy”.  Some will show all 3 so then you will need to create a genre color name called “Comedy Crime Drama Series.png”.    If you use MediaPortal backend with XMLTV plugin it will show all genres for a show. So looks like Argus TV only see the first one.
	



	



