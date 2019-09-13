Updating hit points (or wounds, life points, or the like) using macros is a commonly requested macro procedure, and a very useful feature. When combined with MapTool's Bars feature (which can display health bars, ammo bars, and the like) it can be a simple and very cool way to keep an eye on how your character is doing.

Setting up Health Bars and the macros that update them is easy too.

The Bar
-------

To set up or change the various Bars you want in your game, you access the Bars dialog by selecting *Edit &gt; Campaign Properties*', and selecting the tab named **Bars**.

You will see that by default, MapTool has one bar already set up - the Health Bar. A preview of this bar is shown in the lower portion of the Bars dialog (it will appear as a green bar on a black background). Grab the “Preview” slider and move it up and down - that's what the bar will look like as it is depleted.

To see a bar on a Token, drag a token on the map, right-click on it, and select **Bars &gt; Health.** A dialog will pop up that shows a slider, as well as a checkbox called “Hide.” Uncheck the box, and hit **OK**, and the bar will appear over the token.

We will not do anything fancy with the bar at this point - we'll leave it as is.

The Healing & Hurting Macro
---------------------------

Bars can be altered by macros; each bar has a name, and when you need to refer to it in a macro, the variable you use is *bar.BarName*. So, for instance, the Health Bar - in macro speak - is *bar.Health*.

We're going to create a short macro, in the Campaign window, that will adjust the hit points of a token, and adjust the Health Bar correspondingly. Before we can start, we need to make sure two properties exist.

### HP and MaxHP

Since the length of a health bar is calculated in our macro by dividing the current Hit Points by the Maximum Hit Points, we obviously need two Token Properties to represent these concepts. So, to do that, we edit the Campaign Properties to include two items: “HP” and *MaxHP* (you can use whatever name you like, but I like those).

To put these properties in (assuming that you are using the default set of properties):

1.  Select **Edit &gt; Campaign Properties**.
2.  In the Properties tab, select “Basic” in the left-hand list of property types.
3.  In the main text area, you will see a list of properties, including things like Strength, Dexterity, and so forth.
4.  Put your cursor in that text window, and add - at the bottom of the list - the property *MaxHP*.
5.  Click the “Update” button. The property list will be updated with the new *MaxHP* property.
6.  Click **OK**.

You'll note that we didn't add any property for “current HP,” because the default properties already include that - it's called HP, and in the property list, it appears as *\*@HP*.

Once you click OK, you can then double click on a token, and see the new property in the list of Token Properties. Make sure to put a number in that box (for instance, a token with all of its Hit Points, and a maximum of 25 hit points, should have the value 25 in both HP and MaxHP).

### Writing the Macro

Assuming you've successfully created the new token property *MaxHP*, we can move on to the macro itself. We're going to create a macro that pops up a small dialog, asking you for a number of hit points, and whether that many hit points is being lost or gained (damage or healing, in other words).

1.  In the Campaign macro window (if you don't see it, select **Window &gt; Campaign**), right-click and select “Add New Macro.”
2.  Right-click on the button labeled **(new)** and select **Edit**.
3.  In the macro editing dialog, label the new macro “Damage or Healing.”
4.  At the bottom of the screen, check the box “Apply to Selected Tokens.”
5.  In the “Options” tab, uncheck “Allow Players to Edit Macro” (if it is not already unchecked).
6.  Finally, go back to the “Details” tab, and in the main macro editing area, paste in the macro below.

``` mtmacro
[h:status = input(
"hpChange|0|Number of Hit Points",
"dmgOrHealing|Damage,Healing|Is the character taking damage or being healed?|RADIO|SELECT=0")]
[h:abort(status)]

[if(dmgOrHealing == 0),CODE:
{
    [h:HP = HP - hpChange]
    [h:bar.Health = HP / MaxHP]
    [r:token.name] loses [r:hpChange] hit points.
};
{
    [h:diff = MaxHP - HP]
    [h:HP = min(HP+hpChange, MaxHP)]
    [h:bar.Health = HP / MaxHP]
    [r:token.name] is healed and gains  [r:min(diff,hpChange)] hit points.
};]
```

After pasting that macro into the macro editing dialog, click **OK**, and you're all set. You should now be able to select a token (making sure the token has values for both HP and MaxHP - otherwise, you can get errors) and click the macro button, and you will be prompted to enter the amount of HP gained or lost. Once you hit “OK” on that dialog, the token's properties will be updated, and the health bar will update as well.

### Nonlethal damage

This macro can be expanded to also allow for non-lethal damage fairly easily. To do so, add one more Property called *Nlthl* to track the token's nonlethal damage accumulation. Then the macro becomes:

``` mtmacro
[h:status = input(
"hpChange|0|Number of Hit Points",
"dmgOrHealing|Damage,Healing|Is the character taking damage or being healed?|RADIO|SELECT=0",
"lethalOrNo|Lethal,Nonlethal|Is the damage lethal?|RADIO|SELECT=0")]
[h:abort(status)]

[if(dmgOrHealing == 0),CODE:
{
    [if(lethalOrNo == 0),CODE:
    {
        [h:HP = HP - hpChange]
        [h:bar.Health = (HP - Nlthl) / MaxHP]
        [r:token.name] loses [r:hpChange] hit points.
    };
    {
        [h:Nlthl = Nlthl + hpChange]
        [h:bar.Health = (HP - Nlthl) / MaxHP]
        [r:token.name] loses [r:hpChange] hit points.
    };]
};
{
    [h:diff = MaxHP - HP]
    [h:HP = min(HP+hpChange, MaxHP)]
    [h:Nlthl = max(Nlthl+hpChange, 0)]
    [h:bar.Health = (HP - Nlthl) / MaxHP]
    [r:token.name] is healed and gains  [r:min(diff,hpChange)] hit points.
};]
```

Links
-----

1.  [Fading Arc Health bar](http://forums.rptools.net/viewtopic.php?t=13493)

<Category:Cookbook>