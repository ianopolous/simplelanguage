# SimpleLanguage @ DSLDI summer school

A simple language built using Truffle for the GraalVM.

This fork of simple language intended to be used by the audience of the DSLDI summer school in Lausanne 2015.

This repository is licensed under the permissive UPL licence. Fork it to begin
your own Truffle language.

## Prerequisites
* maven3 
* ant (for IGV)
* eclipse (optional)

## Installation:

* Clone SL repository using:
   "git clone https://github.com/grashalm/simplelanguage"
* Download 
   for Linux: https://www.dropbox.com/s/wdtl6dubyax4sg4/graalvm_linux.zip?dl=0 
* Download for Mac: https://www.dropbox.com/s/evtg738slq4neas/graalvm_mac.zip?dl=0
* Unpack the downloaded graalvm_*.zip into simplelanguage/graalvm. P
* Verify that the file "simplelanguage/graalvm/java" exists
* Execute "./build"

## Eclipse instructions:

* Create a new workspace
* Right click on the package explorer -> Import... -> Existing Project into Workspace -> Select simple language folder -> Finish

## Running

* Execute "./run Test.sl" to run a simple language source file.
* Execute "./run_igv Test.sl" to dump graphs to the igv.
* Execute "./run_assembly Test.sl" to dump compiled assembly of simple language functions.

## Debugging

* Execute "./debug Test.sl" to debug you simpel language source file.
* Attach a Java remote debugger (like eclipse) on port 8000.

## IGV

* Execute "./igv" to start the ideal graph visualizer

## Instructions for Can we fold it yet? (optional)
* Clone JRuby 9k master
* Extract downloaded graalvm (see installation) into $JRuby/graalvm-jdk1.8.0 directory.
* `$ function jt { ruby tool/jt.rb $@; }`
* `$ jt build`
* `$ jt run --graal test/truffle/can-we-fold-yet.rb`

```
$ jt run --graal test/truffle/can-we-fold-yet.rb test/truffle/can-we-fold-yet.rb
Can Truffle constant fold yet?
> 14
Yes! Truffle can constant fold this to 14
> 14 + 2
Yes! Truffle can constant fold this to 16
> eval([1, 2, 3].inspect).sort[1] * 2
Yes! Truffle can constant fold this to 4
> eval(rand < 0.5 ? '14 - 2' : '10 + 2')
Yes! Truffle can constant fold this to 12
> eval('rand')
No :( Truffle can't constant fold that
```
## Exercise
Fork this repository and develop, alter or extend their own DSL using Truffle.
Send the link to your repository to christian.humer@oracle.com.
For questions feel free to use the same adress.


## Further information:

* https://wiki.openjdk.java.net/display/Graal/Publications+and+Presentations
* http://ssw.jku.at/Research/Projects/JVM/Truffle.html
