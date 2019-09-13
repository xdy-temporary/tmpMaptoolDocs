# Overview

The list below was made by me personally (Azhrei) as a reminder of
things I wanted to work on. It is not given in any particular order,
although I did rank things I thought were more important with plus signs
("+") and less important with minus signs ("-"). Anyone wishing to
contribute code to MapTool in the form of Java patches should post to
the Developer Notes forum and specify which items you want to tackle as
we may have guidelines on how we want to see the item implemented.

# List of bug fix items for MapTool 1.3

There are other things beyond this list that would be "nice to have" but
since 1.3 is in feature freeze, they won't be happening.

1.  Loading campaign doesn't draw the screen correctly on the first
    refresh of the map
2.  Error in Help docs for the Campaign Properties \> Light tab.
    <http://forums.rptools.net/viewtopic.php?f=3&t=19240&view=unread#p203192>
3.  Moving seems to clear fog for all players, while Meta-I only clears
    for the selected token(s).
4.  Add build.xml target for clearing the version.txt to get back to
    DEVELOPMENT
5.  Add Help menu option that displays Java SystemProperties for
    debugging purposes (Java version, user.dir, other information from
    SysInfo?)
6.  Add startup check that grabs notes from rptools.net for display to
    user (used for things like version notes, update notes, etc)
7.  Feedback on SVN 5769 (latest as of 7/3)
    <http://forums.rptools.net/viewtopic.php?f=60&t=19195>
8.  Variable transparency for the statsheet?
9.  Dropping first token doesn't use Preferences setting for Filename
    vs. Creature name?
    <http://forums.rptools.net/viewtopic.php?f=3&t=19202&p=202692#p202692>
10. Movement metrics need to be displayed above hard fog
11. If statsheet is being displayed, map rendering should be clipped out
    of that area
12. Right-click menu on tokens sometimes is above or under the statsheet
13. When I draw VBL with the Poly Line tool and try to start a new line
    where the last line ended, it won’t work. I have to literally draw
    the line somewhere else and then go back to that point.
14. Using the \# in campaign properties should imply the \*, but without
    the \* actually showing up in the list