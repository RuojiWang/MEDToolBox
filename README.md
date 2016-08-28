<td bgcolor=#F0FFFF>
# MEDToolBox
### MEDToolBox is your unique medical toolbox for maxillofacial preoperative planning.
 <div>
 <img src="https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/MEDToolBox-is-your-unique-skill-2.png" height="545" width="415"/>
 <img src="https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/MEDToolBox-is-your-unique-skill-3.png" height="545" width="415"/>
 </div>
***
## Brief Introduction
 
 <small>
 * MEDToolBox is your medical toolbox for maxillofacial preoperative planning. My first impression of the software engineer. It comes from a national 863 project in China. This software is a preoperative planning system based on VTK&ITK. 
 
 * It includes many functions related to cranial and maxillofacial surgery. The use of the implicit function to make guide plate is an innovative function, which makes it possible to get any size and shape of the maxillofacial mesh. 
 
 * As a preoperative planning the MEDToolBox has five modes to complete a series of maxillofacial operation, such as reflection mode guide plate mode and collision detection mode. The following picture shows the function distribution.
 </small>

 <div  align="center">
 <img src="https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/function-distribution-map-english.png"/>
 </div>
 
***

## Software Design&Architecture

 <small>
 * The interface of the MEDToolBox is developed by using QT framework technology, the logic part of the system is based on VTK open source library. 
 
 * The system can be divided into interactor, renderer, render window and other components corresponding to data processing, rendering and display. If we look at the system from the functional view, The system can also be divided into the following five modes: file mode, measurement mode, guide plate mode, reflection mode and collision detection mode. Switch between the five modes can achieve a series of complex maxillofacial preoperative design and planning operation. 
 
 * The five modes correspond to the five groups interactive menu, such design reference the architecture of VTK, making the structure of the entire system becomes more clear, more easy to maintain and less coupling. And such design also So benefits the stability and robustness of the system. 
 
 * Each interactor registers an event listener, when the there is a warning or error, the messages will be writed into system log, these message will help us restore use scene and maintenance the system. Each interactor inherit from the VTK interactive class while using QT signals and slots mechanism implementation of the right mouse button menu function.

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
  * the advantage of the implicit function is that you can adjust the shape and size of the funciton to clip. Other softwares use a method of erasing data. For example you are deal with dicoms, you should erase dicom piece by piece to get the mesh. Once you make a mistake in any piece of dicom you may waste lots of time to find the dicom piece and erase it again. What's worse is that most time the mistake of erasing a piece is not obvious. So the use of implicit function means relatively higher efficiency.
  
  * The following four pictures and four steps to show how to make guide plate for a patient. Each picture corresponds to a step.In case you are not satisfied you can do pick point and adjust implicit funciton step over and over again. Try both projection point surface point you may get better result.
    * firstly, open the original maxillofacial data and find position to fix the plate. What need to pay attention to is that only the lower half part of maxillofacial or the joint of the maxillofacial can fix the plate. For the following example we can use the temporomandibular joint.
    * secondly, use clip plane function until we get the mesh near the Symmetric position joint. the smaller the data, the easier the later work.
    * then use mouse to pick point of implicit function. drag the green point(point of the implicit) to adjust the size and shape of the implicit function until you are satisfied.
    * finally, clip plate and see what you get in the preview window. You do not need to clip the same shape as the missing part, generally speaking, the mesh is accepted as long as it can support the corresponding muscle and can be fixed. you can see the mesh I clip is not the same as the missing part.

  </small>

***

## Environment Configuration
 <small>
 This software is based on VTK5.2 ITK4.4 and QT4.8(you may need QtDesigner or QTCreator to make QT more easy). 
 * For Linux, you may cmake it yourself. Use Google to find out how to cmake VTK5.2 and ITK4.4 for Linux.  
 * For Windows, you could download dll&lib from https://my.pcloud.com/publink/show?code=XZprOfZXDY03wBqtpS3eUctlW8hNRc3rMNX (VS2010 or other versions is recommended). Or you can use Google to find out how to cmake VTK5.2 and ITK4.4 for windows. 
 </small>

***

## File Catalog
 <small>
 MEDToolBox.rar include 3 types of files.
 * STLfiles folder(include stl files use for test)
 * MEDToolBox files(includes MEDToolBox.sln MEDToolBox.sdf) 
 * MEDToolBox folder(include almost all source code). 
 </small>

***

## Build&Warm Reminder
 <small>
 * For windows put the ITK VTK and QT folder the same catalog like the following picture shows(open MEDToolBox.sln with txt you will know why). 
 * Rebuild it in the DEBUG&win32 mode.
 * Use right mouse button or click the menu to interact.
 * IN CASE YOU FAIL BUILD&COMPILE TRY FOLLOWING:
   * .suo .ncb .user(generated by VS2010).
   * debug or release catalog and some .obj files.
   * generatedfiles catalog(generated by QT).
 * BUT I GUESS YOU WILL NOT MEET ABOVE I THINK I HAVE DONE THAT FOR YOU.

 ![image](https://github.com/RuojiWang/MEDToolBox/raw/master/images-folder/how-to-place-folders.png)
 
***

##Update&version
 >I am busy recruiting recently, so update should be quite slow.
 
 <small>
 * 2.0 integrated all interactive mode.
 * 2.2 added log record function and registered listener event.
 * 3.0 reconstructed all the code and mode.
 * next version: repair the bug in the collision detection mode and guide plate mode.
   * switch the collision detection function may cause file in the renderer removed. 
   * implicit function may not get the craniofacial data mesh when input strange point data.
   * sometimes double click to open the right menu.
   * sometimes file loaded rotate automaticly.
   * add feature of the force feedback device.
   * add an automatic testing framework later.
   * merge the clip preview interface to the main interface to improve efficiency.
   * modify the detail of the interaction ot the implicit function to improve efficiency.
   
>  * I really want to optimize the underlying of the VTK but I do not know how to do it.
 </small>

***

##License

Copyright [2016] [RuojiWang of copyright owner | YeaTmeRet@gmail.com | 1035456235@qq.com]

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
***

## FAQ
 <ol>
   <li type="disc">Why are you upload rar file instead of a folder which includes all the source code?</li>
   <li type="circle">Files in the MEDToolBox folder are more than 100, which is not all by GitHub.</li>
   
   <li type="disc">What's you Email Address, so I can contact with you?</li>
   <li type="circle">For any question or detailed information:MY EMAIL YeaTmeRet@gmail.com OR 1035456235@qq.com. I am willing to help you :).</li>

   <li type="disc">The files in MEDToolBox seems a little mess?</li>
   <li type="circle">MEDToolBox folder includes more than 100 files that's why I upload a rar file. Of course I could remove some files, for example I could remove CollisionDetectionInteractorStyle1.h and CollisionDetectionInteractorStyle1.cpp. In fact I only use CollisionDetectionInteractorStyle6.h and CollisionDetectionInteractorStyle6.cpp, but in my opinion the CollisionDetectionInteractorStyle1 is the original version of the CollisionDetectionInteractorStyle6, so I keep it in case I may use it. Maybe that is a little weird, but I guess every developer has his won weird things like this habit for me.~ I may remove these "redundant files" when the work is done.</li>

   <li type="disc">What's the advantage and disadvantage of the MEDToolBox?</li>
   <li type="circle">The advantange of the MEDToolBox is the use of the implicit function to make guide plate is an innovative function, which makes it possible to get any size and shape of the smooth-edge maxillofacial mesh. As a preoperative planning the MEDToolBox has many modes to complete a series of maxillofacial operation, such as reflection mode guide plate mode and collision detection mode.;The disadvantage of the MEDToolBox is that the VTK is designed as a common interactive framework, so that VTK has to take many things into consideration, which cause the low inefficient. Unless redesign or rewrite VTK from the bottom, VTK can not be effective.</li>

   <li type="disc">Why is the GUI(your picture) shows MEDToolBox3 not MEDToolBox?</li>
   <li type="circle">After the reconstruction and system-level adjustment, I guess now MEDToolBox is its 3.0 version.</li>

   <li type="disc">What else do you want to express beside above?</li>
   <li type="circle">I think the GitHub means a new land for my software career. It's the first time I take part in the social software development. I have little experience I may commit many mistakes. But what's more important, I am willing to listen to any advice and work harder.</li>

   <li type="disc">Your environment configuration for Linux and Windows seems too simple?</li>
   <li type="circle">Actually I only develop MEDToolBox on Windows, so I upload dll&lib I compile on the pcloud, I am not familiar with Linux environment configuration, But I guess it has many in common with what on Windows. If I write the cmake process on Windows or Linux there, the file will be too long. So I only provide dll&lib which I compile here, for other things, use the Google you will get them, not that hard.</li>
   
   <li type="disc">I see a folder named ITK, but you do not mention it anywhere?</li>
   <li type="circle">So far, all the functions in the MEDToolBox3 are based on VTK&QT, I plan to add some new feature which need ITK library, that is to say, I will use ITK in later version. So I upload the ITK files.</li>
 </ol>
***
</td>
