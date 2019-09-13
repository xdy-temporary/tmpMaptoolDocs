The variable *macro.return* holds the value returned from a called macro
to the calling macro. Other than *macro.return*, a called variable
shares no other variables with the calling macro.

## Examples

When a macro on a [library token](Token:library_token "wikilink") is
called by another macro, the called macro may return a value to the
called macro by assigning that value to the variable *macro.args*.

### Calling Macro

The macro below calls a macro called **getDamage** on the [library
token](Token:library_token "wikilink") "Lib:combat", passing the
variable *damageDice* as an argument. It also sets

<table>
<thead>
<tr class="header">
<th><p>Calling Macro</p></th>
<th><p>Called Macro</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><div class="sourceCode" id="cb1"><pre class="sourceCode numberSource mtmacro numberLines"><code class="sourceCode"><span id="cb1-1"><a href="#cb1-1"></a>[h:damageDice=&quot;2d6&quot;]</span>
<span id="cb1-2"><a href="#cb1-2"></a>[MACRO(&quot;getDamage@Lib:combat&quot;):damageDice]</span>
<span id="cb1-3"><a href="#cb1-3"></a>[h:damageProperties=macro.return]</span>
<span id="cb1-4"><a href="#cb1-4"></a>[h:varsFromStrProp(damageProperties)]</span></code></pre></div></td>
<td><div class="sourceCode" id="cb2"><pre class="sourceCode numberSource mtmacro numberLines"><code class="sourceCode"><span id="cb2-1"><a href="#cb2-1"></a>&lt;!-- getDamage Macro --&gt;</span>
<span id="cb2-2"><a href="#cb2-2"></a>[h:returnData = &quot;&quot;]</span>
<span id="cb2-3"><a href="#cb2-3"></a>[h:damageRoll = eval(macro.args) + 9]</span>
<span id="cb2-4"><a href="#cb2-4"></a>[h:damageType = &quot;piercing&quot;]</span>
<span id="cb2-5"><a href="#cb2-5"></a>You hit your target for [r:damageRoll] damage!</span>
<span id="cb2-6"><a href="#cb2-6"></a>[h:returnData=setStrProp(returnData,&quot;damType&quot;, damageType)]</span>
<span id="cb2-7"><a href="#cb2-7"></a>[h:returnData=setStrProp(returnData,&quot;damage&quot;, damageRoll)]</span>
<span id="cb2-8"><a href="#cb2-8"></a>[h:macro.return=returnData]</span></code></pre></div></td>
</tr>
</tbody>
</table>

In the example above, we assume that the **getDamage** macro was called
by another macro (for example, a token macro) and has received some
value in the form of *macro.args*. The statements in **getDamage** are
executed, and the final statement assigns the value of returnData to the
variable *macro.return*.

When execution of the **getDamage** macro is complete and control is
handed back to the calling macro, *macro.return* is also passed back to
the calling macro, where it can be manipulated like any other variable.

[Category:Special Variable](Category:Special_Variable "wikilink")