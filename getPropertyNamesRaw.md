### Notes

When token properties are created during campaign, they are persistent
in the MapTool campaign, regardless of whether they are editable in the
*Edit Token* window. In other words, even though a property is removed
from the campaign properties, it remains available in the MapTool code.
[getPropertyNamesRaw()](getPropertyNamesRaw "wikilink") will return
*all* token properties that exist or have ever existed in the particular
campaign, even if users cannot directly edit those properties (*i.e.*,
they do not appear in the token's properties when you double click on a
token). To get only properties that are currently visible and editable,
use [getAllPropertyNames()](getAllPropertyNames "wikilink").

[Category:Token Function](Category:Token_Function "wikilink")
[Category:Property Function](Category:Property_Function "wikilink")