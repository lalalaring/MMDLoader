# MMDLoader

![MMDLoaderExample](https://github.com/syoyo/MMDLoader/blob/master/mmdview.gif?raw=true)

(c) model : http://mikumikudance.wikia.com/wiki/Miku_Hatsune_(Lat)
(c) motion: http://mmd.nomeu.org/thumbs/sm13622845

Simple MMD(PMD, VMD) loader in C++.
MMDLoader is written in portable manner. No dependency except for C++ STL.


## Usage

Simply copy `mmd_*`, `pmd_*` and `vmd_*` files to your project.

## Code sample in quick

```
#include "pmd_reader.h"
#include "vmd_reader.h"
#include "mmd_scene.h"
#include "mmd_math.h"

PMDModel* model = NULL;
VMDAnimation* anim = NULL;
MMDScene* scene = NULL;

char* pmdmodel = "input.pmd";
char* vmdmodel = "input.vmd";

PMDReader pmdreader;
model = pmdreader.LoadFromFile(pmdmodel);
assert(model);

VMDReader vmdreader;
anim = vmdreader.LoadFromFile(vmdmodel);
assert(anim);

MMDScene* scene = new MMDScene();
scene->SetModel(model);
scene->AttachAnimation(anim);
```

## Example

OpenGL(GLUT) example viewer is included(see viewer_main.cc).


## Features

Supported

* PMD model loading.
* VMD motion loading.
* Bone animation(IK).

Not supported(Contributors welcome!)

* Morph
* Physics(Bullet)

## Author

Syoyo Fujita(syoyo@lighttransport.com)

## License

3-clause BSD.


