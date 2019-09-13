### Applies To

**MapTool Version:** 1.5+
**Java Version:** MT version 1.5 can only use Java 10

### Launching MapTool via Jar File

With no options, 2GB of memory and a 1MB stack size using the 1.5.0 jar file. Note the jar file name must match exactly.

`javaw -Xmx2048M -Xss1M -jar maptool-1.5.0.0.jar`

### Command Line Options for MapTool

The following command line options are available when launching MapTool from a shell or command prompt. *These are for advanced users or developers.*

The full option name may be used or just the first letter.

The following options have no parameters and take the form of:

*`javaw`` ``-jar`` ``maptool-x.x.x.x.jar`` ``-option`*

`d/debug - Turn on System.out enhanced debug output`
`m/macros - Output list of defined macro functions`
`r/reset - Reset startup options to defaults`
`f/fullscreen - Maximize MapTool window`

The following options require a single parameter and take the form of:

*`javaw`` ``-jar`` ``maptool-x.x.x.x.jar`` ``-option=value`*

`v/version - Override MapTool version`
`m/monitor - Sets which monitor to use beginning with 0.`

These options require the monitor option be specified on the same command line.

*`javaw`` ``-jar`` ``maptool-x.x.x.x.jar`` ``-monitor`` ``-option=value`*

`w/width - Override MapTool window width`
`h/height - Override MapTool window height`
`x/xpos - Override MapTool window starting x coordinate`
`y/ypos - Override MapTool window starting y coordinate`

### Examples

`javaw -Xmx2048M -Xss1M -jar maptool-1.5.0.0.jar -version=1.5.6.7`
`javaw -Xmx2048M -Xss1M -jar maptool-1.5.0.0.jar -v=1.5.6.7`
`javaw -Xmx2048M -Xss1M -jar maptool-1.5.0.0.jar -fullscreen`
`javaw -Xmx2048M -Xss1M -jar maptool-1.5.0.0.jar -f`
`javaw -Xmx2048M -Xss1M -jar maptool-1.5.0.0.jar -monitor=0 -width=800 -height=800`
`javaw -Xmx2048M -Xss1M -jar maptool-1.5.0.0.jar -monitor=0 -xpos=20 -ypos=20`
`javaw -Xmx2048M -Xss1M -jar maptool-1.5.0.0.jar -monitor=0 -x=20 -y=20 -w=800 -h=1200`
`javaw -Xmx2048M -Xss1M -jar maptool-1.5.0.0.jar -m=0 -xpos=150 -y=150 -width=1000 -height=1200`