Introduced in version 1.5.0. The variable  can be used to override the
behavior of the default  function to continue execution instead of
halting.

Whenever you set  to , any use of  in a subsequently called macro will
not abort, but will trigger a return from the macro instead.

The variable  must be in the variable scope where the abort should be
caught. It is not a general flag to turn off abort behavior, just
temporarily in the macro or variable scope where it's set.

## Usage

Set this variable to  (default abort behavior) or  (catch aborts).

``` mtmacro numberLines
[h: macro.catchAbort = 0]
[h: macro.catchAbort = 1]
```

## Examples

When a macro is called by another macro, the called macro may use  to
cancel execution. Usually all macro execution would stop, so the calling
macro would not continue. We can now override that default behavior by
*catching* the abort.

### Default behaviour

The macro below will not have any output because the default behavior is
that any call to  will stop the overall macro execution. Whatever code
is defined after the call to  is not executed.

<table>
<thead>
<tr class="header">
<th><p>Default abort Macro</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><div class="sourceCode" id="cb1"><pre class="sourceCode numberSource mtmacro numberLines"><code class="sourceCode"><span id="cb1-1"><a href="#cb1-1"></a>[h: resultText = &quot;defaultValue&quot;]</span>
<span id="cb1-2"><a href="#cb1-2"></a>[h: resultText = abort(0)]</span>
<span id="cb1-3"><a href="#cb1-3"></a>[r: resultText]</span></code></pre></div></td>
</tr>
</tbody>
</table>

### Catching the abort

The macro below will output  as the  set to  prevents the call to  from
actually terminating execution. The example shows how to set a default
value for any return value of a function/macro that has an  call in it.
The macro then re-enables the normal function of  again by setting  to .
As each macro has its own variable scope, this only affects calls to
within the current macro or calls to other macros from the current
macro. The exception is if the called macro shares the scope with the
calling macro, in which case the  is ignored.

<table>
<thead>
<tr class="header">
<th><p>Catching abort</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><div class="sourceCode" id="cb1"><pre class="sourceCode numberSource mtmacro numberLines"><code class="sourceCode"><span id="cb1-1"><a href="#cb1-1"></a>[h: macro.catchAbort = 1]</span>
<span id="cb1-2"><a href="#cb1-2"></a>[h: resultText = &quot;defaultValue&quot;]</span>
<span id="cb1-3"><a href="#cb1-3"></a>[h: resultText = abort(0)]</span>
<span id="cb1-4"><a href="#cb1-4"></a>[r: resultText]</span>
<span id="cb1-5"><a href="#cb1-5"></a>[h: macro.catchAbort = 0]</span></code></pre></div></td>
</tr>
</tbody>
</table>

### Catching the abort with nested macro calls

Same as in the above example, the calling macro below will output
because we activate catching aborts (in anything that this macro will
call afterwards) with  set to  .

<table>
<thead>
<tr class="header">
<th><p>Called macro using an abort as function doSomething()</p></th>
<th><p>Calling macro catching an abort</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><div class="sourceCode" id="cb1"><pre class="sourceCode numberSource mtmacro numberLines"><code class="sourceCode"><span id="cb1-1"><a href="#cb1-1"></a>[h: &quot;this macro will do something and then abort&quot;]</span>
<span id="cb1-2"><a href="#cb1-2"></a>[h: &quot;... doing something&quot;]</span>
<span id="cb1-3"><a href="#cb1-3"></a>[h: abort(0)]</span></code></pre></div></td>
<td><div class="sourceCode" id="cb2"><pre class="sourceCode numberSource mtmacro numberLines"><code class="sourceCode"><span id="cb2-1"><a href="#cb2-1"></a>[h: macro.catchAbort= 1]</span>
<span id="cb2-2"><a href="#cb2-2"></a>[h: resultText = &quot;defaultValue&quot;]</span>
<span id="cb2-3"><a href="#cb2-3"></a>[h: resultText = doSomething()]</span>
<span id="cb2-4"><a href="#cb2-4"></a>[r: resultText]</span>
<span id="cb2-5"><a href="#cb2-5"></a>[h: macro.catchAbort= 0]</span></code></pre></div></td>
</tr>
</tbody>
</table>

### See also

[abort()](abort "wikilink") [assert()](assert "wikilink")

### Version changes

[Category:Special Variable](Category:Special_Variable "wikilink")