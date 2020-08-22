# Compilation Visualizer for Unity

![Unity Version Compatibility](https://img.shields.io/badge/Unity-2018.4%20%E2%80%94%202020.2-brightgreen)

## What's this?
This tool visualizes the assembly compilation process in Unity3D. It hooks into the Editor-provided events and nicely draws them on a timeline. That's especially helpful when trying to optimize compile times and dependencies between assemblies.  

Besides showing a graphical view of compilation, selecting an assembly shows both dependencies and dependents of that assembly.  

The screenshots show full compilations; but the timeline works as well for partial compilations (e.g. you changed a single script and Unity only recompiles the relevant parts of the dependency chain).

## Quick Start
Install via OpenUPM: https://openupm.com/packages/com.needle.compilation-visualizer/

You can open the **Compilation Visualizer** by selecting `Window > Analysis > Compilation Timeline`.

![Compilation Process](https://github.com/needle-tools/compilation-visualizer/wiki/images/compact-view-recompile.gif)

## Screenshots
![Compilation Process](https://github.com/needle-tools/compilation-visualizer/wiki/images/expanded-view-recompile.gif)

![Compact View](https://github.com/needle-tools/compilation-visualizer/wiki/images/compact-view.png)
![Compact View with selected assembly](https://github.com/needle-tools/compilation-visualizer/wiki/images/compact-view-selection.png)
![Expanded View](https://github.com/needle-tools/compilation-visualizer/wiki/images/expanded-view.png)
![Expanded view with selected assembly](https://github.com/needle-tools/compilation-visualizer/wiki/images/expanded-view-selection.png)

## Compatibility to 2018.4 LTS
While most functionality works great in 2018.4 LTS, some minor things are different:
- no "Recompile" button for now as `CompilationPipeline.RequestScriptCompilation` doesn't exist. You can always `Right Click > Reimport` an asmdef or script to cause a recompile.  
_Future Work: could manually set scripts dirty from code._  

- slightly less accurate total compilation time — 2019.1+ has events for the entire compilation while on 2018.4 the last finished assembly compilation is used as end date.
- no PackageInfo for now on 2018.4 as `PackageInfo.FindForAsset` doesn't exist.  
_Future Work: there's ways to still find the right package._

## Contact
<b>[needle — tools for unity](https://needle.tools)</b> • 
[@NeedleTools](https://twitter.com/NeedleTools) • 
[@marcel_wiessler](https://twitter.com/marcel_wiessler) • 
[@hybridherbst](https://twitter.com/hybdridherbst)
