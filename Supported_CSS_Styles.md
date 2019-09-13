MapTool supports a subset of the CSS level 1 specification. These styles
can be used in-line, and also as external styles within dialogs and
frames. This is not meant to be an exhaustive reference, nor an
introduction to CSS, this page is only a collection of which properties
are supported and to what extent. If you are looking for an introduction
to CSS, visit [W3Schools CSS
Tutorial](http://www.w3schools.com/css/css_intro.asp)

Also, note that some CSS attributes are modeled but not rendered,
meaning that they can be used and will be recognized, they just won't
have any effect on the rendered result. The list is available straight
from the Java documentation: [CSS
Styles](https://docs.oracle.com/javase/8/docs/api/javax/swing/text/html/CSS.html)

# Font Properties

## font

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p>font-style, font-weight, font-size, font-family</p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>none</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>yes</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>only font-size</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>font<span class="in">: bold</span> italic 12pt Arial<span class="op">,</span> Helvetica<span class="op">,</span> sans-serif;</span></code></pre></div></td>
</tr>
</tbody>
</table>

## font-family

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p><em>family-name</em>, <em>generic-name</em></p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>system default</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>yes</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>font-family<span class="in">: Arial</span><span class="op">,</span> Helvetica<span class="op">,</span> sans-serif;</span></code></pre></div></td>
</tr>
</tbody>
</table>

## font-size

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p><em>absolute-size</em>, <em>relative-size</em>, <em>length</em>, <em>percentage</em></p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>medium</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>yes</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>relative to parent element's font-size</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>font-size<span class="in">: 12pt;</span></span></code></pre></div></td>
</tr>
</tbody>
</table>

## font-style

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p>normal, italic, oblique</p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>normal</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>yes</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>font-style<span class="in">: italic</span>;</span></code></pre></div></td>
</tr>
</tbody>
</table>

## font-weight

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p>normal, bold, bolder, lighter, 100, 200, 300, 400, 500, 600, 700, 800, 900</p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>normal</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>yes</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>font-weight<span class="in">: bold</span>;</span></code></pre></div></td>
</tr>
</tbody>
</table>

# Color and Background Properties

## color

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p><em>color name</em>, <em>color code</em></p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>element specific</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>yes</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>color<span class="in">: #FF0000</span>;</span></code></pre></div></td>
</tr>
</tbody>
</table>

## background

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p>background-color, background-image, background-repeat, background-position</p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>none</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>background<span class="in">: #0000FF url(asset://de05e42d2eb43fe53a542db116da8083)</span> no-repeat right top;</span></code></pre></div></td>
</tr>
</tbody>
</table>

## background-color

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p><em>color name</em>, <em>color code</em></p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>transparent</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>background-color<span class="in">: #0000FF;</span></span></code></pre></div></td>
</tr>
</tbody>
</table>

## background-image

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p>none, <em>url</em></p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>none</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>background-image<span class="in">: url(asset://de05e42d2eb43fe53a542db116da8083)</span>;</span></code></pre></div></td>
</tr>
</tbody>
</table>

## background-repeat

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p>repeat, repeat-x, repeat-y, no-repeat</p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>repeat</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>background-repeat<span class="in">: no-repeat</span>;</span></code></pre></div></td>
</tr>
</tbody>
</table>

## background-position

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p>top, center, bottom, left, center, right</p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>top left</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>block-level and replaced elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>background-position<span class="in">: bottom</span> right;</span></code></pre></div></td>
</tr>
</tbody>
</table>

# Text Properties

## text-align

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p>left, right, center</p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>element specific</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>block-level elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>yes</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>text-align<span class="in">: right</span>;</span></code></pre></div></td>
</tr>
</tbody>
</table>

## text-decoration

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p>none, underline, line-through</p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>none</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>text-decoration<span class="in">: line-through</span>;</span></code></pre></div></td>
</tr>
</tbody>
</table>

## vertical-align

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p>baseline, sub, super</p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>baseline</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>inline elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>vertical-align<span class="in">: super</span>;</span></code></pre></div></td>
</tr>
</tbody>
</table>

# Box Properties

## border-style

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p>none, inset, outset</p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>none</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>border-style<span class="in">: inset</span>;</span></code></pre></div></td>
</tr>
</tbody>
</table>

## margin

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p><em>length</em>, auto</p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>none</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>margin<span class="in">: 10px;</span></span></code></pre></div></td>
</tr>
</tbody>
</table>

## margin-top

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p><em>length</em>, auto</p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>0</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>margin-top<span class="in">: 10px;</span></span></code></pre></div></td>
</tr>
</tbody>
</table>

## margin-right

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p><em>length</em>, auto</p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>0</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>margin-right<span class="in">: 10px;</span></span></code></pre></div></td>
</tr>
</tbody>
</table>

## margin-bottom

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p><em>length</em>, auto</p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>0</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>margin-bottom<span class="in">: 10px;</span></span></code></pre></div></td>
</tr>
</tbody>
</table>

## margin-left

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p><em>length</em>, auto</p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>0</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>margin-left<span class="in">: 10px;</span></span></code></pre></div></td>
</tr>
</tbody>
</table>

## padding

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p><em>length</em></p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>0</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>padding<span class="in">: 10px;</span></span></code></pre></div></td>
</tr>
</tbody>
</table>

## padding-top

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p><em>length</em></p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>0</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>padding-top<span class="in">: 10px;</span></span></code></pre></div></td>
</tr>
</tbody>
</table>

## padding-right

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p><em>length</em></p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>0</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>padding-right<span class="in">: 10px;</span></span></code></pre></div></td>
</tr>
</tbody>
</table>

## padding-bottom

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p><em>length</em></p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>0</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>padding-bottom<span class="in">: 10px;</span></span></code></pre></div></td>
</tr>
</tbody>
</table>

## padding-left

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p><em>length</em></p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>0</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>all elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>padding-left<span class="in">: 10px;</span></span></code></pre></div></td>
</tr>
</tbody>
</table>

# Classification Properties

## list-style-type

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p>none, disc, circle, square, decimal, lower-roman, upper-roman, lower-alpha, upper-alpha</p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>disc</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>list-item elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>yes</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>list-style-type<span class="in">: square</span>;</span></code></pre></div></td>
</tr>
</tbody>
</table>

## list-style-position

<table>
<tbody>
<tr class="odd">
<td><p><strong>Value:</strong></p></td>
<td><p>inside, outside</p></td>
</tr>
<tr class="even">
<td><p><strong>Initial:</strong></p></td>
<td><p>outside</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applies To:</strong></p></td>
<td><p>list-item elements</p></td>
</tr>
<tr class="even">
<td><p><strong>Inherited:</strong></p></td>
<td><p>yes</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relative Size:</strong></p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p><strong>Example:</strong></p></td>
<td><div class="sourceCode" id="cb1"><pre class="sourceCode css"><code class="sourceCode css"><span id="cb1-1"><a href="#cb1-1"></a>list-style-position<span class="in">: inside</span>;</span></code></pre></div></td>
</tr>
</tbody>
</table>

[Category:Macro](Category:Macro "wikilink")