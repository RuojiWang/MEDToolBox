<td bgcolor=#F0FFFF>
# MEDToolBox
### MEDToolBox is your unique medical toolbox for maxillofacial preoperative planning.
 <div>
 <img src="https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/MEDToolBox-is-your-unique-skill-2.png" height="545" width="415"/>
 <img src="https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/MEDToolBox-is-your-unique-skill-4.png" height="545" width="415"/>
 </div>
***
## Brief Introduction
 
 <small>
 * MEDToolBox is your medical toolbox for maxillofacial preoperative planning. My first impression of the software engineer. It comes from a national 863 project in China. This software is a preoperative planning system based on VTK&ITK. 
 
 * It includes many functions related to cranial and maxillofacial surgery. **The use of the implicit function to make guide plate is an innovative function, which makes it possible to get any size and shape of the maxillofacial mesh.** 
 
 * **As a preoperative planning the MEDToolBox has five modes to complete a series of maxillofacial operation, such as reflection mode guide plate mode and collision detection mode. The following picture shows the function distribution.**

 * **According to the Pareto Principle, Only 20% is the most important things. Important imformation is marked in bold.**
 </small>

 <div  align="center">
 <img src="https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/function-distribution-map-english.png"/>
 </div>
 
***

## Software Design&Architecture

 <small>
 * The interface of the MEDToolBox is developed by using QT framework technology, the logic part of the system is based on VTK open source library. 
 
 * **The system can be divided into interactor, renderer, render window and other components corresponding to data processing, rendering and display. If we look at the system from the functional view, The system can also be divided into the following five modes: file mode, measurement mode, guide plate mode, reflection mode and collision detection mode. Switch between the five modes can achieve a series of complex maxillofacial preoperative design and planning operation.** 
 
 * **The five modes correspond to the five groups interactive menu, such design reference the architecture of VTK, making the structure of the entire system becomes more clear, more easy to maintain and less coupling. And such design also benefits the stability and robustness of the system.** 
 
 * **Each interactor registers an event listener, when the there is a warning or error, the messages will be writed into system log, these message will help us restore use scene and maintenance the system. Each interactor inherit from the VTK interactive class while using QT signals and slots mechanism implementation of the right mouse button menu function.**
 
 * The following twelve pictures are divided into five groups, Each group contains two pictures, except the last one contains four pictures. The five groups of pictures show what the interface looks like when you interact in that mode respectively. The five modes from top to bottom are: file mode  which mainly deal with the import/export of maxillofacial data simple and data operation like merge and interaction mode operation, measurement mode which mainly deal with the measure of the maxillofacial data, reflection mode which mainly deal with anything about maxillofacial repair by using symmetry, collision detection mode which mainly deal with the collision detect of the maxillofacial data, guide plate mode which mainly deal with the fixation and defect of the maxillofacial data.
 </small>

 <img src="https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/switch-meun.png" height="390" width="415"/>
 <img src="https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/file-mode-interface.png" height="390" width="415"/>
 
 <img src="https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/measurement-boundbox-interface.png" height="390" width="415"/>
 <img src="https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/reflection-mode-interface.png" height="390" width="415"/>
 
 <img src="https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/collision-detection-mode-interface.png" height="390" width="415"/>
 <img src="https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/collision-detection-mode-detection-interface.png" height="390" width="415"/>
 
 <img src="https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/guide-plate-mode-interface.png" height="390" width="415"/>
 <img src="https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/guide-plate-mode-draw-surface-curve-interface.png" height="390" width="415"/>

 <img src="https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/clip-plate-from-guide-plate-mode-interface-1.png" height="390" width="415"/>
 <img src="https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/clip-plate-from-guide-plate-mode-interface-2.png" height="390" width="415"/>
 
 <img src="https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/clip-mesh-from-guide-plate-mode-interface-1.png" height="390" width="415"/>
 <img src="https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/thickened-mesh-from-guide-plate-mode-interface.png" height="390" width="415"/>
 
***
## Advantage&Example
  <small>
  * The advantages of the MEDToolBox are the following:
     * The use of the computer-assisted maxillofacial preoperative planning has all the advantages of computer assisted surgery. It extends the limited vision space of the cranial and maxillofacial surgery, breaks through the limit of the traditional skull and maxillofacial surgery, and deepens the concept of the skull and maxillofacial surgery and surgical instruments. Especially, when it comes to avoiding operation risk, improving the operation accuracy, optimizing operation process, improving the operation of the planning efficiency.
     * **The use of the implicit function allows you to adjust the shape and size of the funciton to clip. With the help of implicit function you can get almost any shape and size of smooth-edge mesh. However, other softwares use a method of erasing data. For example if you are deal with dicoms, you should erase dicom piece by piece to get the mesh or mesh module. Once you make a mistake in any piece of dicom you may waste lots of time finding the wrong piece of dicom and erase it again. What's worse is that most time the wrong piece of dicom is not obvious, even someone tells you the wrong piece of dicom you may still need some time to find the mistake. So the use of implicit function means relatively higher efficiency.**
     * **The use of the listen events can record many exceptions and errors in the system. The design of five modes correspond to the five groups interactive menu, which reference the architecture of VTK, making the structure of the entire system becomes more clear, more easy to maintain and less coupling. And such design also benefits the stability, robustness, maintainability and extensible of the system.**

  
  * There are four pictures
