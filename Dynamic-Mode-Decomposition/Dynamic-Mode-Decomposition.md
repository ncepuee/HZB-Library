Dynamic
Mode
Decomposition
OT149_Kutz_FM.indd 1 9/28/2016 11:16:06 AM

Dynamic
Mode
Decomposition
Data-Driven Modeling of Complex Systems
J. Nathan Kutz
University of Washington
Seattle, Washington
Steven L. Brunton
University of Washington
Seattle, Washington
Bingni W. Brunton
University of Washington
Seattle, Washington
Joshua L. Proctor
Institute for Disease Modeling
Bellevue, Washington
Society for Industrial and Applied Mathematics
Philadelphia
OT149_Kutz_FM.indd 3 9/28/2016 11:16:06 AM

Copyright © 2016 by the Society for Industrial and Applied Mathematics
10 9 8 7 6 5 4 3 2 1
All rights reserved. Printed in the United States of America. No part of this book may
be reproduced, stored, or transmitted in any manner without the written permission of
the publisher. For information, write to the Society for Industrial and Applied Mathematics,
3600 Market Street, 6th Floor, Philadelphia, PA 19104-2688 USA.
MATLAB is a registered trademark of The MathWorks, Inc. For MATLAB product information,
please contact The MathWorks, Inc., 3 Apple Hill Drive, Natick, MA 01760-2098 USA,
508-647-7000, Fax: 508-647-7001, info@mathworks.com, www.mathworks.com.
Publisher David Marshall
Acquisitions Editor Elizabeth Greenspan
Developmental Editor Gina Rinelli Harris
Managing Editor Kelly Thomas
Production Editor Ann Manning Allen
Copy Editor Julia Cochrane
Production Manager Donna Witzleben
Production Coordinator Cally Shrader
Compositor Techsetters, Inc. and Scott Collins
Graphic Designer Lois Sellers
Library of Congress Cataloging-in-Publication Data
Names: Kutz, Jose Nathan.
Title: Dynamic mode decomposition : data-driven modeling of complex systems /
J. Nathan Kutz, University of Washington [and three others].
Description: Philadelphia : Society for Industrial and Applied Mathematics,
[2016] | Series: Other titles in applied mathematics ; 149 | Includes
bibliographical references and index.
Identifiers: LCCN 2016024120 (print) | LCCN 2016026184 (ebook) | ISBN
9781611974492 | ISBN 9781611974508
Subjects: LCSH: Decomposition (Mathematics) | Mathematical analysis.
Classification: LCC QA402.2 .D96 2016 (print) | LCC QA402.2 (ebook) | DDC
518/.2--dc23
LC record available at https://lccn.loc.gov/2016024120
is a registered trademark.
OT149_Kutz_FM.indd 4 9/28/2016 11:16:06 AM

Contents
| Preface                     |                |     |     | ix  |
| --------------------------- | -------------- | --- | --- | --- |
| Notation                    |                |     |     | xi  |
| Acronyms                    |                |     |     | xv  |
| 1 DynamicModeDecomposition: | AnIntroduction |     |     | 1   |
1.1 DMD . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 2
1.2 FormulatingtheDMDarchitecture. . . . . . . . . . . . . . . . . . . . 3
1.3 TheDMDalgorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 7
1.4 Examplecodeanddecomposition . . . . . . . . . . . . . . . . . . . . . 11
1.5 LimitationsoftheDMDmethod . . . . . . . . . . . . . . . . . . . . . 15
1.6 Broadercontextofequation-freemethods. . . . . . . . . . . . . . . . 18
1.7 InterdisciplinaryconnectionsofDMD . . . . . . . . . . . . . . . . . 22
| 2 FluidDynamics |     |     |     | 25  |
| --------------- | --- | --- | --- | --- |
2.1 Modaldecompositioninfluids . . . . . . . . . . . . . . . . . . . . . . . 25
2.2 ApplicationsofDMDinfluids . . . . . . . . . . . . . . . . . . . . . . . 31
Re=100flowaroundacylinderwake
| 2.3 Example:      |     | .   | . . . . . . . . . | . 33 |
| ----------------- | --- | --- | ----------------- | ---- |
| 3 KoopmanAnalysis |     |     |                   | 39   |
3.1 Spectraltheoryandeigenfunctionexpansions . . . . . . . . . . . . . 39
3.2 TheKoopmanoperator . . . . . . . . . . . . . . . . . . . . . . . . . . . 43
3.3 ConnectionswithDMD . . . . . . . . . . . . . . . . . . . . . . . . . . . 46
3.4 Exampledynamicalsystems. . . . . . . . . . . . . . . . . . . . . . . . . 49
| 4 VideoProcessing |     |     |     | 55  |
| ----------------- | --- | --- | --- | --- |
Background/foregroundvideoseparation
| 4.1 |     | . . . . . . | . . . . . . . . . | . 55 |
| --- | --- | ----------- | ----------------- | ---- |
4.2 RPCAandDMD . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 56
4.3 DMDforbackgroundsubtraction. . . . . . . . . . . . . . . . . . . . . 58
4.4 Simpleexampleandalgorithm . . . . . . . . . . . . . . . . . . . . . . . 60
4.5 DMDforvideosurveillance. . . . . . . . . . . . . . . . . . . . . . . . . 63
| 5 MultiresolutionDMD |     |     |     | 71  |
| -------------------- | --- | --- | --- | --- |
5.1 Time-frequencyanalysisandtheGábortransform . . . . . . . . . . 71
5.2 WaveletsandMRA . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 72
5.3 FormulatingmrDMD . . . . . . . . . . . . . . . . . . . . . . . . . . . . 75
5.4 ThemrDMDalgorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . 78
5.5 Examplecodeanddecomposition . . . . . . . . . . . . . . . . . . . . . 80
v

vi Contents
5.6 Overcomingtranslationalandrotationalinvariances. . . . . . . . . 87
| 6 DMDwithControl |     | 91  |
| ---------------- | --- | --- |
6.1 FormulatingDMDc. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 91
6.2 TheDMDcalgorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . 96
6.3 Examples . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 97
6.4 Connectionstosystemidentificationmethods. . . . . . . . . . . . . 100
6.5 ConnectionstoKoopmanoperatortheory . . . . . . . . . . . . . . . 101
| 7 DelayCoordinates,ERA,andHiddenMarkovModels |     | 105 |
| -------------------------------------------- | --- | --- |
7.1 Delaycoordinatesandshift-stackingdata . . . . . . . . . . . . . . . . 105
7.2 ConnectiontoERAandHankelmatrices. . . . . . . . . . . . . . . . 109
7.3 HMMs . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 113
| 8 NoiseandPower |     | 119 |
| --------------- | --- | --- |
8.1 Powerspectrum . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 119
8.2 Truncatingdataandsingularvaluethresholding. . . . . . . . . . . . 126
8.3 CompensatingfornoiseintheDMDspectrum . . . . . . . . . . . . 128
| 9 SparsityandDMD |     | 133 |
| ---------------- | --- | --- |
9.1 Compressedsensing . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 134
9.2 Sparsity-promotingDMD . . . . . . . . . . . . . . . . . . . . . . . . . . 137
9.3 Sub-NyquistsampledDMD. . . . . . . . . . . . . . . . . . . . . . . . . 139
9.4 CompressedDMD. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 140
9.5 CodeforcompressedDMD . . . . . . . . . . . . . . . . . . . . . . . . . 150
| 10 DMDonNonlinearObservables |     | 159 |
| ---------------------------- | --- | --- |
10.1 Koopmanobservables . . . . . . . . . . . . . . . . . . . . . . . . . . . . 159
10.2 Nonlinearobservablesforpartialdifferentialequations . . . . . . . 160
10.3 ExtendedandkernelDMD . . . . . . . . . . . . . . . . . . . . . . . . . 166
10.4 ImplementingextendedandkernelDMD. . . . . . . . . . . . . . . . 172
| 11 Epidemiology |     | 177 |
| --------------- | --- | --- |
11.1 Modelinginfectiousdiseasespread . . . . . . . . . . . . . . . . . . . . 177
11.2 Infectiousdiseasedata. . . . . . . . . . . . . . . . . . . . . . . . . . . . . 179
11.3 DMDforinfectiousdiseasedata . . . . . . . . . . . . . . . . . . . . . . 180
11.4 Examples . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 181
11.5 TheepidemiologicalinterpretationofDMDmodes . . . . . . . . . 184
| 12 Neuroscience |     | 185 |
| --------------- | --- | --- |
12.1 Experimentaltechniquestomeasureneuralactivity . . . . . . . . . 185
12.2 Modaldecompositioninneuroscience . . . . . . . . . . . . . . . . . . 187
12.3 DMDonneuralrecordings . . . . . . . . . . . . . . . . . . . . . . . . . 188
| 13 Financial | Trading | 195 |
| ------------ | ------- | --- |
13.1 Financialinvestmentandalgorithmictrading . . . . . . . . . . . . . 195
13.2 Financialtime-seriesdataandDMD . . . . . . . . . . . . . . . . . . . 197
13.3 Tradingalgorithmsandtraining . . . . . . . . . . . . . . . . . . . . . . 200
13.4 Tradingperformance . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 204
| Glossary |     | 207 |
| -------- | --- | --- |

Contents vii
Bibliography 213
Index 233

Preface
Theintegrationofdataandscientificcomputationisdrivingaparadigmshiftacross
theengineering,natural,andphysicalsciences. Indeed,thereexistsanunprecedented
availabilityofhigh-fidelitymeasurementsfromtime-seriesrecordings,numericalsim-
ulations, and experimental data. When data is coupled with readily available algo-
rithmsandinnovationsinmachine(statistical)learning,itispossibletoextractmean-
ingfulspatiotemporal patternsthatdominatedynamicactivity. Adirectimplication
ofsuchdata-drivenmodelingstrategiesisthatwecangaintractiononunderstanding
fundamentalscientificprocessesandalsoenhanceourcapabilitiesforprediction,state
estimation,andcontrolofcomplexsystems. Theabilitytodiscoverunderlyingprin-
ciplesfromdatahasbeencalledthefourthparadigmofscientificdiscovery[131]. Math-
ematicaltechniquesgearedtowardcharacterizingpatternsindataandcapitalizingon
theobserved low-dimensionalstructuresfallclearlywithinthisfourthparadigmand
areinever-growingdemand.
The focus of this book is on the emerging method of dynamic mode decomposi-
tion (DMD). DMD is a matrix decomposition technique that is highly versatile and
builds upon the power of singular value decomposition (SVD). The low-rank struc-
turesextractedfromDMD,however,areassociatedwithtemporalfeaturesaswellas
correlated spatial activity. One only need consider the impact of principal compo-
nentanalysis(PCA)andFouriertransformstounderstandtheimportanceofversatile
matrixdecompositionmethodsandtime-seriescharacterizationsfordataanalysis.
From a conceptional viewpoint, the DMD method has a rich history stemming
fromtheseminalworkofBernardKoopmanin1931[162]onnonlineardynamicalsys-
tems. Butduetothelackofcomputationalresourcesduringhisera,thetheoreticalde-
velopmentswerelargelylimited. InterestinKoopmantheorywasrevivedin2004/05
byMezi´cetal.[196,194],withSchmidandSesterhenn[250]andSchmid[247],in2008
and2010,respectively,firstdefiningDMDasanalgorithm. Rowleyetal.[235]quickly
realizedthattheDMDalgorithmwasdirectlyconnectedtotheunderlyingnonlinear
dynamicsthroughtheKoopmanoperator,openingupthetheoreticalunderpinnings
forDMDtheory. Thus,agreatdealofcreditforthesuccessofDMDcanbedirectly
attributedtotheseminalcontributionsofIgorMezi´c(UniversityofCalifornia,Santa
Barbara),PeterSchmid(ImperialCollege),andClancyRowley(PrincetonUniversity).
This book develops the fundamental theoretical foundations of DMD and the
Koopmanoperator. Itfurtherhighlightsmanynewinnovationsandalgorithmsthat
extendtherangeofapplicabilityofthemethod. WealsodemonstratehowDMDcan
beappliedinavarietyofdiscipline-specificsettings. Theseexemplarfieldsshowhow
DMDcanbeusedsuccessfullyforprediction,stateestimation,andcontrolofcomplex
systems. ByprovidingasuiteofalgorithmsforDMDanditsvariants,wehopetohelp
thepractitioner quicklybecome fluent inthisemergingmethod. Our aimisalsoto
augmentatraditionaltrainingindynamicalsystemswithadata-drivenviewpointof
ix

x Preface
thefield.
Toaidindemonstratingthekeyconceptsofthisbook,wehavemadeextensiveuse
ofthescientificcomputingsoftwareMATLAB.MATLABisoneoftheleadingscien-
tificcomputingsoftwarepackagesandisusedacrossuniversitiesintheUnitedStates
forteachingandlearning. Itiseasytouse,provideshigh-levelprogrammingfunction-
ality,andgreatlyreducesthetimetoproduceexamplecode. Thebuilt-inalgorithms
developed by MATLAB allow us toeasily use many of the key workhorse routines
ofscientificcomputing. Given thatDMD wasoriginallydefined asan algorithm, it
isfittingthatthebookisstronglyfocusedonimplementationandalgorithmdevelop-
ment. WeareconfidentthatthecodesprovidedinMATLABwillnotonlyallowfor
reproducibleresearchbutalsoenhancethelearningexperienceforboththosecommit-
tedtoitsresearchimplementationandthosecurioustodabbleinanewmathematical
subject. Allthecodesareavailableatwww.siam.org/books/ot149.
J.NathanKutz
StevenL.Brunton
BingniW.Brunton
JoshuaL.Proctor
Seattle,WA
March2016

Notation
A Matrixrepresentationofdiscrete-timelineardynamics
A˜ ReduceddynamicsonPODsubspace
A Matrixrepresentationofcontinuous-timelineardynamics
Ab Matrixrepresentationofbackward-timedynamics
A Rank-r approximationoflineardynamicsfromERA
r
A Matrixrepresentationoflineardynamicsonthestatex
X
A Matrixrepresentationoflineardynamicsontheobservablesy
Y
B Inputmatrix
B Inputmatrixforrank-r ERAsystem
r
b VectorofDMDmodeamplitudes
C Linearmeasurementmatrixfromstatetooutputs
C Linearmeasurementmatrixforrank-r ERAsystem
r
D Cylinderdiameter
F Discrete-timeflowmapofdynamicalsystem
F Discrete-timeflowmapofdynamicalsystemthroughtimet
t
f Continuous-timedynamicalsystem
G Matrixrepresentationoflineardynamicsonthestatesandinputs[xTuT]T
G Implicitmeasurementfunction
g Vector-valuedobservablefunctionsonx
g Scalarobservablefunctiononx
(cid:2) Hilbertspaceofscalar-valuedfunctionsonstate-space
J NumberoftimebinsinmrDMD
(cid:3) Koopmanoperator
K Finite-dimensionalapproximationtoKoopmanoperator
L Low-rankportionofmatrixX
L NumberoflevelsinmrDMD
(cid:2) CurrentlevelinmrDMD
m Numberofdatasnapshots
m NumberofdaysinthefutureforDMDprediction
f
m NumberofpastdaystakenintoaccountinDMDprediction
p
N Nonlinearpartialdifferentialequation
N˜ Macroscalenonlinearity
n Dimensionofthestate,x∈(cid:2)n
P UnitarymatrixthatactsoncolumnsofX
p Dimensionofthemeasurementoroutputvariable,y∈(cid:2)p
q Continuous-timestateofpartialdifferentialequation
q Dimensionoftheinputvariable,u∈(cid:2)q
Re Reynoldsnumber
xi

xii Notation
r Residualerrorvector
r RankoftruncatedSVD
˜r RankoftruncatedSVDofΩ
S SparseportionofmatrixX
s Sparsevector
s Numberoftimestoshift-stackdataforERA
t Time
t kthdiscretetimestep
k
Δt Timestep
U Leftsingularvectors(PODmodes)ofX
Uˆ Leftsingularvectors(PODmodes)ofΩ
U˜ Leftsingularvectors(PODmodes)ofX (cid:5)
U Free-streamfluidvelocity
∞
u Controlvariable
V RightsingularvectorsofX
Vˆ Rightsingularvectors(PODmodes)ofΩ
V˜ Rightsingularvectors(PODmodes)ofX (cid:5)
W EigenvectorsofA˜
X
Datamatrix,X∈(cid:2)n×(m−1)
X
(cid:5)
Shifteddatamatrix,X
(cid:5)∈(cid:2)n×(m−1)
Xk Datamatrixcontainingsnapshots j throughk
j
x Snapshotofdataattimet
k k
Y
Datamatrixofobservables,Y=g(X),Y∈(cid:2)p×(m−1)
Y
(cid:5)
Shifteddatamatrixofobservables,Y
(cid:5)=g(X (cid:5)),Y (cid:5)∈(cid:2)p×(m−1)
y Vectorofmeasurements,y∈(cid:2)p
η Noisemagnitude
Θ Measurementmatrixtimessparsifyingbasis,Θ=CΨ
Λ DiagonalmatrixofDMDeigenvalues(discrete-time)
λ DMDeigenvalue
μ Bifurcationparameters
ν Kinematicviscosityoffluid
ξ Spatialvariable
ρ Radiusofeigenvaluethresholdforfast/slowseparationinmrDMD
Σ Matrixofsingularvalues
Σˆ MatrixofsingularvaluesofΩ
Σ˜ MatrixofsingularvaluesofX (cid:5)
σ kthsingularvalue
k
Υ Inputsnapshotmatrix,Υ ∈(cid:2)q×(m−1)
Φ MatrixofDMDmodes,Φ(cid:3)X (cid:5) VΣ−1W
Φ DMDmodesonX
X
Φ DMDmodesonY
Y
φ DMDmode
ϕ Koopmaneigenfunction

Notation xiii
Ψ Orthonormalbasis(e.g.,FourierorPODmodes)
Ω Stateandinputsnapshotmatrix,Ω∈(cid:2)(q+n)×(m−1)
ω Continuous-timeDMDeigenvalue,ω(cid:3)log(λ)/Δt
(cid:7)·(cid:7) (cid:2)
pseudonormofavectorx: thenumb(cid:2)erofnonzeroelementsinx
| (cid:7)·(cid:7) 0 (cid:2) 0 -normofavectorxgivenby(cid:7)x(cid:7) |     | =   | |x | |     |
| ----------------------------------------------------------------- | --- | --- | ---- | --- |
(cid:3)(cid:2) n
| 1 1                                                           |     | 1 i=1 | i                 |     |
| ------------------------------------------------------------- | --- | ----- | ----------------- | --- |
| (cid:7)·(cid:7) (cid:2) -normofavectorxgivenby(cid:7)x(cid:7) |     | = n   | (x(cid:3) 2)      |     |
| 2 2                                                           |     | 2 i=1 | i (cid:2) (cid:2) |     |
(cid:7)·(cid:7) FrobeniusnormofamatrixXgivenby(cid:7)X(cid:7) = n m |X |2
|     |     |     | (cid:4)(cid:9)i=1 | (cid:5)j=1 |
| --- | --- | --- | ----------------- | ---------- |
| F   |     |     | F                 | (cid:2)ij  |
(cid:7)·(cid:7) NuclearnormofamatrixXgivenby(cid:7)X(cid:7) =trace X∗X = m σ
| ∗   |     | ∗   |     |     |
| --- | --- | --- | --- | --- |
i=1 i
(form≤n)
(cid:6)
| 〈·,·〉 | Forfunctions,〈f(x),g(x)〉= |     | ∞ f(x)g ∗(x)dx. |     |
| ----- | ------------------------- | --- | --------------- | --- |
Innerproduct.
−∞

Acronyms
ALM AugmentedLagrangemultiplier
ARIMA Autoregressiveintegratedmovingaverage
ARMA Autoregressivemovingaverage
ARX Autoregressiveexogenous
BPOD Balancedproperorthogonaldecomposition
cDMD Compresseddynamicmodedecomposition
csDMD Compressedsensingdynamicmodedecomposition
CFD Computationalfluiddynamics
CWT Continuouswavelettransform
DEIM Discreteempiricalinterpolationmethod
DMD Dynamicmodedecomposition
DMDc Dynamicmodedecompositionwithcontrol
DNS Directnumericalsimulation
ECoG Electrocorticography
EEG Electroencephalography
EFM Equation-freemethod
EOF Empiricalorthogonalfunctions
ERA Eigensystemrealizationalgorithm
fbDMD Forward/backwardDMD
FFT FastFouriertransform
GPFA Gaussianprocessfactoranalysis
HMM HiddenMarkovmodel
ICA Independentcomponentanalysis
KIC Koopmanwithinputsandcontrol
LDS Lineardynamicalsystem
LDV LaserDopplervelocimetry
LIM Linearinversemodeling
MRA Multiresolutionanalysis
mrDMD Multiresolutiondynamicmodedecomposition
NLDS Nonlineardynamicalsystems
NLS NonlinearSchrödinger
NLSA NonlinearLaplacianspectralanalysis
NNMF Nonnegativematrixfactorization
OKID ObserverKalmanfilteridentification
PCA Principalcomponentanalysis
xv

xvi Acronyms
PCP Principalcomponentpursuit
PCR Principalcomponentregression
PIV Particleimagevelocimetry
POD Properorthogonaldecomposition
RIP Restrictedisometryproperty
ROM Reduced-ordermodel
RPCA Robustprincipalcomponentanalysis
SARIMA Seasonalautoregressiveintegratedmovingaverage
SIR Susceptible,infected,recovered
SSA Singularspectrumanalysis
STBLI Shockturbulentboundarylayerinteraction
STFT Short-timeFouriertransform
SVD Singularvaluedecomposition
SVM Supportvectormachine
tlsDMD Total-least-squaresDMD
VARIMA Vectorautoregressiveintegratedmovingaverage

Chapter 1
Dynamic Mode
Decomposition: An
Introduction
The data-driven modeling and control of complex systems is a rapidly evolving
field with great potential to transform the engineering, biological, and physical
sciences. Thereisunprecedentedavailabilityofhigh-fidelitymeasurementsfromhis-
torical records, numerical simulations, and experimental data, and although data is
abundant,modelsoftenremainelusive. Modernsystemsofinterest,suchasaturbu-
lentfluid,anepidemiologicalsystem,anetworkofneurons,financialmarkets,orthe
climate,maybecharacterizedashigh-dimensional,nonlineardynamicalsystemsthat
exhibitrichmultiscalephenomenainbothspaceandtime. Howevercomplex,many
ofthesesystemsevolveonalow-dimensionalattractorthatmaybecharacterized by
spatiotemporalcoherentstructures. Inthischapter,wewillintroducethetopicofthis
book,dynamicmodedecomposition(DMD),whichisapowerfulnewtechniquefor
thediscoveryofdynamicalsystemsfromhigh-dimensionaldata.
The DMD method originated in the fluid dynamics community as a method to
decomposecomplexflowsintoasimplerepresentationbasedonspatiotemporalcoher-
entstructures. SchmidandSesterhenn[250]andSchmid[247]firstdefinedtheDMD
algorithmanddemonstrateditsabilitytoprovideinsightsfromhigh-dimensionalflu-
idsdata. ThegrowingsuccessofDMDstemsfromthefactthatitisanequation-free,
data-drivenmethodcapableofprovidinganaccuratedecompositionofacomplexsys-
temintospatiotemporal coherent structuresthatmaybeused forshort-timefuture-
statepredictionandcontrol. Morebroadly,DMDhasquicklygainedpopularitysince
Mezi´c et al. [196, 194, 195] and Rowley et al. [235] showed that it is connected to
theunderlying nonlineardynamics through Koopman operator theory [162]and is
readilyinterpretableusingstandarddynamicalsystemstechniques.
The development of DMD is timely due to the concurrent rise of data science,
encompassing a broad range of techniques, from machinelearning and statisticalre-
gressiontocomputervisionandcompressedsensing. Improvedalgorithms,abundant
data,vastlyexpandedcomputationalresources,andinterconnectednessofdatastreams
makethisafertileground forrapid development. Inthischapter, wewillintroduce
thecoreDMDalgorithm,provideabroaderhistoricalcontext,andlaythemathemat-
icalfoundationforthefutureinnovationsandapplicationsofDMDdiscussedinthe
remainingchapters.
1

2 Chapter1. DynamicModeDecomposition: AnIntroduction
1.1 DMD
DMD is the featured method of thisbook. At itscore, the method can be thought
ofasanidealcombinationofspatialdimensionality-reductiontechniques,suchasthe
proper orthogonal decomposition (POD),1 with Fourier transforms in time. Thus,
correlatedspatialmodesarealsonowassociatedwithagiventemporalfrequency,pos-
siblywithagrowthordecayrate. Themethodreliessimplyoncollectingsnapshotsof
datax fromadynamicalsystematanumberoftimest ,wherek=1,2,3,...,m. As
k k
wewillshow,DMDisalgorithmicallyaregressionofdataontolocallylineardynamics
x =Ax ,whereAischosentominimize(cid:7)x −Ax (cid:7) overthek=1,2,3,...,m−1
k+1 k k+1 k 2
snapshots. Theadvantagesofthismethodarethatitisverysimpletoexecute andit
makesalmostnoassumptionsabouttheunderlyingsystem. Thecostofthealgorithm
isasingularvaluedecomposition(SVD)ofthesnapshotmatrixconstructedfromthe
datax .
k
DMDhasanumberofusesandinterpretations. Specifically,theDMDalgorithm
cangenerallybethoughttoenablethreeprimarytasks.
I.Diagnostics. Atitsinception,theDMDalgorithmwasusedasadiagnostictool
to characterize complex fluid flows [247, 235]. In particular, the algorithm extracts
keylow-rankspatiotemporalfeaturesofmanyhigh-dimensionalsystems,allowingfor
physicallyinterpretableresultsintermsofspatialstructuresandtheirassociatedtem-
poral responses. Interestingly, thisisstillperhaps the primary function ofDMD in
manyapplicationareas. ThediagnosticnatureofDMDallowsforthedata-drivendis-
covery of fundamental, low-rank structures in complex systems analogous to POD
analysisinfluidflows,plasmaphysics,atmosphericmodeling,etc.
II.Stateestimationandfuture-stateprediction. Amoresophisticatedandchal-
lenginguseoftheDMDalgorithmisassociatedwithusingthespatiotemporalstruc-
turesthataredominantinthedatatoconstructdynamicalmodelsoftheunderlying
processesobserved. Thisisamuchmoredifficulttask,especiallyasDMDislimited
toconstructingthebest-fit(least-square)lineardynamicalsystemtothenonlineardy-
namicalsystemgeneratingthedata. Thus,unlikethediagnosticobjective,thegoalis
toanticipatethestateofthesysteminaregimewherenomeasurementsweremade.
Confounding the regressive nature of DMD is the fact that the underlying dynam-
ics can exhibit multiscale dynamics in both time and space. Regardless, there are a
numberofkeystrategies,includingintelligentsamplingofthedataandupdatingthe
regression, that allow DMD to be effective for generating a useful linear dynamical
model. Thisgenerativemodelapproachcanthenbeusedforfuture-statepredictions
ofthedynamicalsystemsandhasbeenusedwithsuccessinmanyapplicationareas.
III.Control. Enablingviableandrobustcontrolstrategiesdirectlyfromdatasam-
plingistheultimate,andmostchallenging, goaloftheDMDalgorithm. Giventhat
we are using a linear dynamical model to predict the future of a nonlinear dynami-
calsystem,itisreasonabletoexpectthatthereisonlyalimited,perhapsshort-time,
windowinthefuturewherethetwomodelswillactuallyagree. Thehopeisthatthis
accurate prediction windowislong enough in duration toenable a control decision
capableofinfluencingthefuturestateofthesystem. TheDMDalgorithminthiscase
1PODisoftencomputedusingthesingularvaluedecomposition(SVD).Itisalsoknownasprincipal
componentanalysis(PCA)instatistics[214,147],empiricalorthogonalfunctions(EOF)inclimateand
meteorology[181],thediscreteKarhunen–Loevetransform,andtheHotellingtransform[134,135].

1.2. FormulatingtheDMDarchitecture 3
allowsforacompletelydata-drivenapproachtocontroltheory,thusprovidingacom-
pelling mathematical framework for controlling complex dynamical systems whose
governingequationsarenotknownoraredifficulttomodelcomputationally.
WhenusingtheDMDmethod,oneshouldalwaysbemindfuloftheintendeduseand
the expected outcome. Further, although it seems quite obvious, the success of the
DMD algorithm will depend largely on which of the above tasks one is attempting
toachieve. Throughoutthisbook,manyofthechapterswilladdressone,two,orall
threeoftheaboveobjectives. Insomeapplications,itisonlyreasonableatthispointto
useDMDasadiagnostictool. Inotherapplications,limitedsuccesshasbeenachieved
evenforthetaskofcontrol.Undoubtedly,manyresearchersareworkinghardtomove
emergingapplicationareasthroughthistasklisttowardachievingaccuratemodeling
andcontrolofdynamicalsystemsinanequation-freeframework.
1.2 Formulating the DMD architecture
IntheDMDarchitecture,wetypicallyconsiderdatacollectedfromadynamicalsys-
tem
dx
=f(x,t;μ), (1.1)
dt
wherex(t)∈(cid:2)n isavectorrepresentingthestateofourdynamicalsystemattime t,
μ containsparameters of thesystem, and f(·) represents thedynamics. Generally, a
dynamicalsystemisrepresentedasacoupledsystemofordinarydifferentialequations
thatareoftennonlinear. Thestatexistypicallyquitelarge,havingdimensionn(cid:13)1;
thisstatemayariseasthediscretizationofapartialdifferentialequationatanumberof
discretespatiallocations. Finally,thecontinuous-timedynamicsfrom(1.1)mayalso
induceacorresponding discrete-timerepresentation, inwhichwesamplethesystem
everyΔt intimeanddenotethetimeasasubscriptsothatx =x(kΔt). Wedenote
k
thediscrete-timeflowmapobtainedbyevolving(1.1)forΔt byF:
x =F(x ). (1.2)
k+1 k
Measurementsofthesystem
y =g(x ) (1.3)
k k
arecollectedattimes t from k =1,2,...,m foratotalof m measurementtimes. In
k
manyapplications,themeasurementsaresimplythestate,sothaty =x . Thedata
k k
assimilationcommunityoftenrepresentsthesemeasurementsbytheimplicitexpres-
sionG(x,t)=0. Theinitialconditionsareprescribedasx(t )=x .
0 0
Asalreadyhighlighted,xisann-dimensionalvector(n(cid:13)1)thatarisesfromeither
discretizationofacomplexsystem,orinthecaseofapplicationssuchasvideostreams,
fromthetotalnumberofpixelsinagivenframe. Thegoverningequationsandinitial
conditionspecifyawell-posedinitialvalueproblem.
In general, it is not possible to construct a solution to the governing nonlinear
evolution(1.1),sonumericalsolutionsareusedtoevolvetofuturestates. TheDMD
frameworktakestheequation-freeperspective,wherethedynamicsf(x,t;μ)maybe
unknown. Thus,datameasurementsofthesystemaloneareusedtoapproximatethe
dynamics and predict the future state. The DMD procedure constructs the proxy,
approximatelocallylineardynamicalsystem
dx
=Ax (1.4)
dt

| 4   | Chapter1. | DynamicModeDecomposition: |     | AnIntroduction |     |
| --- | --------- | ------------------------- | --- | -------------- | --- |
withinitialconditionx(0)andwell-knownsolution[33]
(cid:7)n
|     | x(t)= | φ exp(ω | t)b =Φexp(Ωt)b, |     | (1.5) |
| --- | ----- | ------- | --------------- | --- | ----- |
|     |       | k       | k k             |     |       |
k=1
whereφ andω aretheeigenvectorsandeigenvaluesofthematrixA,andthecoef-
k arethecoordinatesofx(0)intheeigenvectorbasis. k
ficientsb
k
Givencontinuousdynamicsasin(1.4),itisalwayspossibletodescribeananalo-
gousdiscrete-timesystemsampledeveryΔt
intime:
|     |     | x =Ax | ,   |     | (1.6) |
| --- | --- | ----- | --- | --- | ----- |
|     |     | k+1   | k   |     |       |
where
A=exp(AΔt).
(1.7)
A
refers tothematrixin thecontinuous-time dynamicsfrom (1.4). Thesolution to
simplyintermsoftheeigenvaluesλ
thissystemmaybeexpressed andeigenvectors
k
φ ofthediscrete-timemapA:
k
(cid:7)r
|     | x   | = φ λkb | =ΦΛkb. |     | (1.8) |
| --- | --- | ------- | ------ | --- | ----- |
|     |     | k j     | j j    |     |       |
j=1
Asbefore,barethecoefficientsoftheinitialconditionx intheeigenvectorbasis,so
=Φb. 1
thatx TheDMDalgorithmproducesalow-rankeigendecomposition(1.8)of
1
the matrix A that optimally fits the measured trajectory x for k = 1,2,...,m in a
k
least-squaresensesothat
|     |     | (cid:7)x −Ax | (cid:7) |     | (1.9) |
| --- | --- | ------------ | ------- | --- | ----- |
|     |     | k+1          | k 2     |     |       |
isminimizedacrossallpointsfork=1,2,...,m−1.
Theoptimalityoftheapproxima-
tionholdsonlyoverthesamplingwindowwhereAisconstructed,andtheapproxi-
matesolutioncanbeusedtonotonlymakefuturestatepredictionsbutalsodecompose
thedynamicsintovarioustimescales,sincetheλ
areprescribed.
k
Arriving at the optimally constructed matrixA for the approximation (1.6) and
thesubsequenteigendecompositionin(1.8)isthefocusoftheremainderofthisintro-
ductory chapter. In subsequent chapters, adeeper theoretical understanding willbe
pursued,alongwithvariousdemonstrationsofthepowerofthismethodology.
=1,2,...,m,
Tominimizetheapproximationerror(1.9)acrossallsnapshotsfromk
itispossibletoarrangethemsnapshotsintotwolargedatamatrices:
⎡ ⎤
X=⎣ ⎦
|     |     | x x       | ··· x ,   |     | (1.10a) |
| --- | --- | --------- | --------- | --- | ------- |
|     |     | 1         | 2 m−1     |     |         |
|     |     | ⎡         | ⎤         |     |         |
|     |     | (cid:5)=⎣ | ⎦         |     |         |
|     |     | X x       | x ··· x . |     | (1.10b) |
|     |     | 2         | 3 m       |     |         |
Recallthatthesedatasnapshotsarelikelysampledfromanonlineardynamicalsystem
(1.1),althoughwearefindinganoptimallocallinearapproximation. Thelocallylinear
approximation(1.6)maybewrittenintermsofthesedatamatricesas
(cid:5)≈AX.
|     |     | X   |     |     | (1.11) |
| --- | --- | --- | --- | --- | ------ |

1.2. FormulatingtheDMDarchitecture 5
Thebest-fitAmatrixisgivenby
A=X (cid:5) X†, (1.12)
where†istheMoore–Penrosepseudoinverse. Thissolutionminimizestheerror
(cid:7)X (cid:5)−AX(cid:7) , (1.13)
F
where(cid:7)·(cid:7) istheFrobeniusnorm,givenby
F
(cid:12)
(cid:13)
(cid:13)(cid:7)n (cid:7)m
(cid:7)X(cid:7) =(cid:14) X 2. (1.14)
F jk
j=1 k=1
It is important to note that (1.13) and the solution (1.12) may be thought of as
a linear regression of data onto the dynamics given by A. However, there is a key
difference between DMD and alternative regression-based system identification and
model reduction techniques. Importantly, weareassuming thatthesnapshotsx in
k
ourdatamatrixXarehighdimensionalsothatthematrixistallandskinny,meaning
thatthesizenofasnapshotislargerthanthenumberm−1ofsnapshots. Thematrix
Amaybehighdimensional; if n =106,thenAhas1012 elements, sothatitmaybe
difficulttorepresentordecompose. However,therankofAisatmostm−1,sinceit
isconstructedasalinearcombinationofthem−1columnsofX (cid:5) . Insteadofsolving
forAdirectly,wefirstproject ourdataontoalow-ranksubspacedefinedbyatmost
m−1PODmodesandthensolveforalow-dimensionalevolutionA˜ thatevolveson
thesePOD mode coefficients. TheDMD algorithm then uses thislow-dimensional
operatorA˜ toreconstructtheleadingnonzeroeigenvaluesandeigenvectorsofthefull-
dimensionaloperatorAwithouteverexplicitlycomputingA.Thisisdiscussedin§1.3
below.
1.2.1 Defining DMD
TheDMDmethodprovidesaspatiotemporaldecompositionofdataintoasetofdy-
namicmodesthat arederivedfrom snapshotsormeasurementsofagiven system in
time.AschematicoverviewisprovidedinFigure1.1. Themathematicsunderlyingthe
extractionofdynamicinformationfromtime-resolvedsnapshotsiscloselyrelatedto
theideaoftheArnoldialgorithm[247],oneoftheworkhorsesoffastcomputational
solvers. Thedatacollectionprocessinvolvestwoparameters:
n=numberofspatialpointssavedpertimesnapshot,
m=numberofsnapshotstaken.
The DMD algorithm was originally designed to collect data at regularly spaced in-
tervals of time, as in (1.10). However, new innovations allow for both sparse spa-
tial [48] and sparse temporal [289] collections of data, as well as irregularly spaced
collectiontimes. Indeed,Tuetal.[290]providesthemostmoderndefinitionofthe
DMDmethodandalgorithm.
Definition: Dynamicmodedecomposition(Tuetal. 2014[290]): Supposewehavea

| 6   |     |            | Chapter1. | DynamicModeDecomposition: |     |     | AnIntroduction |     |     |
| --- | --- | ---------- | --------- | ------------------------- | --- | --- | -------------- | --- | --- |
|     |     | Experiment |           | Collect Data              |     |     | DMD            |     |     |
a) Diagnostics
|     |     |     |     | ⎡   | ⎤   |     |     | pastfuture |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ---------- | --- |
x
|     |     |     | m    |        |     | sedom cimanyD |     |     |               |
| --- | --- | --- | ---- | ------ | --- | ------------- | --- | --- | ------------- |
|     |     | t   | X=⎣x |        | ⎦   |               |     |     | Time dynamics |
|     |     |     |      | x ···x |     |               |     |     |               |
|     |     | .   |      | 1 2    | m−1 | A=X(cid:2)X†  |     |     |               |
.
.
|     |     |     |             | ⎡   | ⎤          |     |     |     |     |
| --- | --- | --- | ----------- | --- | ---------- | --- | --- | --- | --- |
|     |     |     | Data        |     | Regression |     |     |     |     |
|     |     |     | X(cid:2)=⎣x | x   | ···x ⎦     |     |     |     |     |
|     |     |     |             | 2 3 | m          |     |     |     | t   |
1 m
|     |     | x   |     |     |     | b) Future state prediction |     |     |     |
| --- | --- | --- | --- | --- | --- | -------------------------- | --- | --- | --- |
3
x
|     |     | 2   |     |     |     |     |     | x   | =Ax |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     |     |     |     |     | k+1 | k   |
x
1
Figure1.1. SchematicoverviewofDMDonafluidflowexamplethatwillbeexplored
furtherinChapter2. NotethattheregressionstepdoesnottypicallyconstructAbutinsteadcon-
structsA˜,whichevolvesthedynamicsonalow-ranksubspaceviaPOD.Theeigendecompositionof
A˜ isthenusedtoapproximatetheeigendecompositionofthehigh-dimensionalmatrixA.
dynamicalsystem(1.1)andtwosetsofdata,
|     |     |     |     | ⎡             |                   | ⎤                 |     |     |         |
| --- | --- | --- | --- | ------------- | ----------------- | ----------------- | --- | --- | ------- |
|     |     |     |     | X=⎣           | ···               | ⎦                 |     |     |         |
|     |     |     |     | x             | x                 | x m−1 ,           |     |     | (1.15a) |
|     |     |     |     | 1             | 2                 |                   |     |     |         |
|     |     |     |     | ⎡             |                   | ⎤                 |     |     |         |
|     |     |     |     | X (cid:5)=⎣ x | (cid:5) x (cid:5) | ··· x (cid:5) ⎦ , |     |     | (1.15b) |
m−1
|     |     |     |     |     | 1 2 |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
sothatx (cid:5) =F(x ),whereFisthemapin(1.2)correspondingtotheevolutionof (1.1)for
k
timeΔt. k
DMDcomputestheleadingeigendecompositionofthebest-fitlinearoperatorA
(cid:5)≈AX:
relatingthedataX
|     |     |     |     | A=X | (cid:5) X†. |     |     |     |     |
| --- | --- | --- | --- | --- | ----------- | --- | --- | --- | --- |
(1.16)
TheDMD modes, also calleddynamic modes, are theeigenvectorsof A, andeachDMD
modecorrespondstoaparticulareigenvalueofA.
| 1.2.2 | DMD | and the Koopman |     | operator |     |     |     |     |     |
| ----- | --- | --------------- | --- | -------- | --- | --- | --- | --- | --- |
Koopmanoperator.
|     | TheDMDmethodapproximates |     |     | themodesoftheso-called |     |     |     |     | The |
| --- | ------------------------ | --- | --- | ---------------------- | --- | --- | --- | --- | --- |
Koopmanoperatorisalinear,infinite-dimensionaloperatorthatrepresentstheaction
ofanonlineardynamicalsystemontheHilbertspaceofmeasurementfunctionsofthe
state[235,195].
ItisimportanttonotethattheKoopmanoperatordoesnotrelyon
linearizationofthedynamicsbutinsteadrepresentstheflowofthedynamicalsystem
onmeasurementfunctionsasaninfinite-dimensionaloperator.
TheDMDmethodcanbeviewedascomputing,fromtheexperimentaldata,the
eigenvalues and eigenvectors (low-dimensional modes) of a finite-dimensional linear
model that approximates theinfinite-dimensional Koopman operator. Sincethe op-
erator is linear, thedecomposition gives the growth rates and frequencies associated
witheachmode. Iftheunderlyingdynamicsin(1.1)arelinear,thentheDMDmethod
recoverstheleadingeigenvaluesandeigenvectorsnormallycomputedusingstandard
solutionmethodsforlineardifferentialequations.

1.3. TheDMDalgorithm 7
Mathematically,theKoopmanoperator(cid:3)
isaninfinite-dimensionallinearoper-
atorthatactsontheHilbertspace(cid:2)
containingallscalar-valuedmeasurementfunc-
tions g :(cid:4)n →(cid:4)ofthestatex. TheactionoftheKoopmanoperatoronameasure-
mentfunction g equatestocompositionofthefunction g withtheflowmapF:
|     | (cid:3)    | = g◦F        |            |         |
| --- | ---------- | ------------ | ---------- | ------- |
|     |            | g            |            | (1.17a) |
|     | =⇒ (cid:3) | g(x )= g(F(x | ))= g(x ). |         |
|     |            |              | k+1        | (1.17b) |
k k
Inotherwords,theKoopmanoperator,alsoknownasthecompositionoperator,ad-
vancesmeasurementsalongwiththeflowF. Thisisincrediblypowerfulandgeneral,
sinceitholdsforallmeasurementfunctions g evaluatedatanystatevectorx.
TheapproximationoftheKoopmanoperatorisattheheartoftheDMDmethod-
overΔt
ology. Asalreadystated,themapping islineareventhough theunderlying
dynamicsthatgenerated x maybenonlinear. Itshould benoted thatthisisfunda-
k
mentallydifferentthanlinearizingthedynamics. However,thequalityofanyfinite-
dimensionalapproximationtotheKoopmanoperatordependsonthemeasurements
| y=g(x)chosen. ThiswillbediscussedindepthinChapter3. |     |     |     |     |
| --------------------------------------------------- | --- | --- | --- | --- |
1.3 The DMD algorithm
Inpractice, when thestatedimension n islarge,thematrixAmaybeintractableto
analyzedirectly. Instead,DMDcircumventstheeigendecompositionofAbyconsid-
eringarank-reducedrepresentationintermsofaPOD-projectedmatrixA. ˜ TheDMD
algorithm,alsoshowninAlgorithm1.1asafunction,proceedsasfollows[290]:
1. First,takethesingularvaluedecomposition(SVD)ofX[283]:
∗
|     |     | X≈UΣV | ,   | (1.18) |
| --- | --- | ----- | --- | ------ |
where∗denotestheconjugatetranspose,U∈(cid:4)n×r,Σ∈(cid:4)r×r,andV∈(cid:4)m×r.
Here r istherankofthereducedSVDapproximation toX. Theleftsingular
∗ U=I;
| vectorsUarePODmodes. |     | ThecolumnsofUareorthonormal, |     | soU |
| -------------------- | --- | ---------------------------- | --- | --- |
∗ V=I.
similarly,V
TheSVDreductionin(1.18)isexploitedatthisstageinthealgorithmtoperform
alow-rank truncation ofthedata. Specifically, iflow-dimensionalstructure is
ofΣwilldecreasesharplytozerowith
| present inthedata, | thesingularvalues |     |     |     |
| ------------------ | ----------------- | --- | --- | --- |
perhapsonlyalimitednumberofdominantmodes. Aprincipledwaytotrun-
catenoisydataisgivenbytherecenthard-thresholdingalgorithmofGavishand
Donoho[106],asdiscussedin§8.2.
2. The matrix A from (1.16) may be obtained by using the pseudoinverse of X
obtainedviatheSVD:
|     |     | A=X (cid:5) VΣ−1U | ∗   |        |
| --- | --- | ----------------- | --- | ------ |
|     |     |                   | .   | (1.19) |
Inpractice,itismoreefficientcomputationallytocomputeA˜,ther×r
projec-
tionofthefullmatrixAontoPODmodes:
|     |     | ∗       | ∗ (cid:5) VΣ−1. |        |
| --- | --- | ------- | --------------- | ------ |
|     | A˜  | =U AU=U | X               | (1.20) |
ThematrixA˜ definesalow-dimensionallinearmodelofthedynamicalsystem
onPODcoordinates:
=A˜x˜
|                                                    |     | x˜  | .    | (1.21) |
| -------------------------------------------------- | --- | --- | ---- | ------ |
|                                                    |     | k+1 | k    |        |
| Itispossibletoreconstructthehigh-dimensionalstatex |     |     | =Ux˜ | .      |
|                                                    |     |     | k    | k      |

8 Chapter1. DynamicModeDecomposition: AnIntroduction
3. ComputetheeigendecompositionofA˜:
A˜W=WΛ, (1.22)
wherecolumnsofWareeigenvectorsandΛisadiagonalmatrixcontainingthe
correspondingeigenvaluesλ .
k
4. Finally, we may reconstruct the eigendecomposition of A from W and Λ. In
particular,theeigenvaluesofAaregivenbyΛandtheeigenvectorsofA(DMD
modes)aregivenbycolumnsofΦ:
Φ=X (cid:5) VΣ−1W. (1.23)
Notethat(1.23)from[290]differsfromtheformulaΦ=UWin[247],althoughthese
(cid:5)
willtendtoconvergeifXandX havethesamecolumnspaces. Themodesin(1.23)
areoftencalledexactDMDmodes,becauseitwasproveninTuetal.[290]thatthese
areexacteigenvectorsofthematrixA.ThemodesΦ=UWarereferredtoasprojected
DMD modes [247]. To find a dynamic mode of A associated with a zero eigenvalue
λ =0,theexactformulationin(1.23)maybeusedifφ=X (cid:5) VΣ−1w(cid:18)=0. Otherwise,
k
theprojectedDMDformulationφ=Uw shouldbeused[290].
Withthelow-rankapproximationsofboththeeigenvaluesandtheeigenvectorsin
hand,theprojected futuresolutioncan beconstructed foralltimeinthefuture. By
firstrewritingforconvenienceω =ln(λ )/Δt,theapproximatesolutionatallfuture
k k
timesisgivenby
(cid:7)r
x(t)≈ φ exp(ω t)b =Φexp(Ωt)b, (1.24)
k k k
k=1
whereb istheinitialamplitudeofeachmode,Φisthematrixwhosecolumnsarethe
k
DMD eigenvectors φ , and Ω = diag(ω) is a diagonal matrix whose entries are the
k
eigenvaluesω . Theeigenvectorsφ arethesamesizeasthestatex,andbisavector
k k
ofthecoefficients b .
k
As discussed earlier, it is possible to interpret (1.24) as the least-square fit, or re-
gression,ofabest-fitlineardynamicalsystemx =Ax forthedatasampled. The
k+1 k
matrixAisconstructedsothat(cid:7)x −Ax (cid:7) isminimizedacrossallsnapshots.
k+1 k 2
It only remains to compute the initial coefficient values b . If we consider the
k
initialsnapshotx attimet =0,then(1.24)givesx =Φb.Thematrixofeigenvectors
1 1 1
Φisgenericallynotasquarematrixsothattheinitialconditions
b=Φ†x (1.25)
1
canbefoundusingapseudoinverse. Indeed,Φ†denotestheMoore–Penrosepseudoin-
versethatcanbeaccessedinMATLABviathepinvcommand. Thepseudoinverseis
equivalenttofindingthebest-fitsolutionbintheleast-squaressense.
AMATLABimplementationoftheDMDalgorithm(DMD.m)isprovidedinAlgo-
rithm1.1. TheDMDalgorithmpresentedheretakesadvantageoflowdimensionality
inthedatatomakealow-rankapproximationofthelinearmappingthatbestapprox-
imatesthenonlineardynamicsofthedatacollectedforthesystem. Oncethisisdone,
apredictionofthefuturestateofthesystemisachievedforalltime.UnlikethePOD-
Galerkin method, which requires solving a low-rank set of dynamical quantities to
predictthefuturestate,noadditionalworkisrequiredforthefuturestateprediction
besides plugging the desired future time into (1.24). Thus, the advantages of DMD

1.3. TheDMDalgorithm 9
revolvearoundthefactthat(i)itisanequation-freearchitectureand(ii)afuture-state
prediction ispossible toconstruct foranytime t (ofcourse, provided theDMDap-
proximationholds).
AkeybenefitoftheDMDframeworkisthesimpleformulationintermsofwell-
established techniquesfrom linearalgebra. Thismakes DMDamenable toavariety
ofpowerfulextensions,includingmultiresolution(Chapter5),actuationandcontrol
(Chapter6),time-delaycoordinatesandprobabilisticformulations(Chapter7),noise
mitigation(Chapter8),andsparsemeasurementsviacompressedsensing(Chapter9).
Another important advantage of DMD is that it is formulated entirely in terms of
measurement data. For this reason, it may be applied to a broad range of applica-
tions,includingfluiddynamics(Chapter2),videoprocessing(Chapter4),epidemiol-
ogy(Chapter11),neuroscience(Chapter12),andfinance(Chapter13).
ALGORITHM1.1.DMDfunction(DMD.m).
| function   | [Phi,omega,lambda,b,Xdmd] |         |     |      |               | = DMD(X1,X2,r,dt) |                 |     |
| ---------- | ------------------------- | ------- | --- | ---- | ------------- | ----------------- | --------------- | --- |
| % function | [Phi,omega,lambda,b,Xdmd] |         |     |      |               | =                 | DMD(X1,X2,r,dt) |     |
| % Computes | the                       | Dynamic |     | Mode | Decomposition |                   | of X1, X2       |     |
%
% INPUTS:
| % X1 =       | X, data     | matrix |           |           |           |     |        |     |
| ------------ | ----------- | ------ | --------- | --------- | --------- | --- | ------ | --- |
| % X2 =       | X’, shifted |        | data      | matrix    |           |     |        |     |
| % Columns    | of          | X1 and | X2        | are state | snapshots |     |        |     |
| % r = target |             | rank   | of SVD    |           |           |     |        |     |
| % dt =       | time        | step   | advancing | X1        | to X2     | (X  | to X’) |     |
%
% OUTPUTS:
| % Phi,    | the DMD | modes           |            |               |                 |     |             |     |
| --------- | ------- | --------------- | ---------- | ------------- | --------------- | --- | ----------- | --- |
| % omega,  | the     | continuous-time |            |               | DMD eigenvalues |     |             |     |
| % lambda, | the     | discrete-time   |            |               | DMD eigenvalues |     |             |     |
| % b, a    | vector  | of              | magnitudes |               | of modes        | Phi |             |     |
| % Xdmd,   | the     | data            | matrix     | reconstructed |                 | by  | Phi, omega, | b   |
%% DMD
| [U, S,       | V] =            | svd(X1, | ’econ’);        |                   |           |             |             |     |
| ------------ | --------------- | ------- | --------------- | ----------------- | --------- | ----------- | ----------- | --- |
| r = min(r,   | size(U,2));     |         |                 |                   |           |             |             |     |
| U_r = U(:,   | 1:r);           |         | % truncate      |                   | to rank-r |             |             |     |
| S_r = S(1:r, |                 | 1:r);   |                 |                   |           |             |             |     |
| V_r = V(:,   | 1:r);           |         |                 |                   |           |             |             |     |
| Atilde       | = U_r’          | * X2    | * V_r           | / S_r;            | %         | low-rank    | dynamics    |     |
| [W_r, D]     | = eig(Atilde);  |         |                 |                   |           |             |             |     |
| Phi = X2     | * V_r           | /       | S_r *           | W_r;              | % DMD     | modes       |             |     |
| lambda       | = diag(D);      |         | % discrete-time |                   |           | eigenvalues |             |     |
| omega =      | log(lambda)/dt; |         |                 | % continuous-time |           |             | eigenvalues |     |
| %% Compute   | DMD             | mode    | amplitudes      |                   | b         |             |             |     |
| x1 = X1(:,   | 1);             |         |                 |                   |           |             |             |     |
b = Phi\x1;
%% DMD reconstruction
| mm1 = size(X1, |     | 2);        | % mm1 | = m   | - 1 |     |     |     |
| -------------- | --- | ---------- | ----- | ----- | --- | --- | --- | --- |
| time_dynamics  |     | = zeros(r, |       | mm1); |     |     |     |     |

| 10                |     | Chapter1. |        | DynamicModeDecomposition: |     |     |     | AnIntroduction |     |
| ----------------- | --- | --------- | ------ | ------------------------- | --- | --- | --- | -------------- | --- |
| t = (0:mm1-1)*dt; |     | % time    | vector |                           |     |     |     |                |     |
for iter = 1:mm1,
| time_dynamics(:,iter) |     |     |     | = (b.*exp(omega*t(iter))); |     |     |     |     |     |
| --------------------- | --- | --- | --- | -------------------------- | --- | --- | --- | --- | --- |
end;
Xdmd = Phi * time_dynamics;
| 1.3.1 Historical | perspective |     | on the | DMD | algorithm |     |     |     |     |
| ---------------- | ----------- | --- | ------ | --- | --------- | --- | --- | --- | --- |
Historically,theoriginalDMDalgorithm[247]wasformulatedinthecontext ofits
connection toKrylov subspaces andtheArnoldialgorithm. Inthiscontext, itisas-
sumedthatthedataissampledfromasingletrajectoryinphasespace, although this
assumptionhassubsequentlybeenrelaxedinthegeneraldefinitionpresentedin§1.2.1.
Forcompleteness,aswellasunderstandingthisconnection,wepresenttheDMDal-
gorithmasoriginallypresentedbySchmid[247]. Toillustratethealgorithm,consider
thefollowingregularlyspacedsamplingintime:
=t +Δt,
|     |     | datacollectiontimes: |     |     | t   |     |     |     | (1.26) |
| --- | --- | -------------------- | --- | --- | --- | --- | --- | --- | ------ |
|     |     |                      |     |     | k+1 | k   |     |     |        |
where the collection time starts at t and ends at t and the interval between data
|     |     |     |     | 1   |     | m   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
collectiontimesisΔt.
Asbefore,thedatasnapshotsarethenarrangedintoann×mmatrix
|     |     |     | ⎡   |       |       |     | ⎤   |     |        |
| --- | --- | --- | --- | ----- | ----- | --- | --- | --- | ------ |
|     |     | X=⎣ | x(t | ) x(t | ) ··· | x(t | )⎦  |     |        |
|     |     |     |     |       |       |     | ,   |     | (1.27) |
|     |     |     |     | 1     | 2     | m   |     |     |        |
where the vector x contains the n measurements of the state variable of the system
of interest at the datacollection points. The objective isto minethe datamatrixX
for important dynamical information. For the purposes of the DMD method, the
followingmatrixisalsodefined:
|     |     |       | ⎡   |       |       |     | ⎤   |     |        |
| --- | --- | ----- | --- | ----- | ----- | --- | --- | --- | ------ |
|     |     | Xk =⎣ | x(t | ) x(t | ) ··· | x(t | )⎦  |     |        |
|     |     |       |     |       | j+1   |     | .   |     | (1.28) |
|     |     | j     |     | j     |       |     | k   |     |        |
Thus,thismatrixincludescolumns j throughk oftheoriginaldatamatrix.
To construct the Koopman operator that best represents the data collected, the
matrixXm isconsidered:
1
|     |     |      | ⎡   |       |       |     | ⎤   |     |        |
| --- | --- | ---- | --- | ----- | ----- | --- | --- | --- | ------ |
|     |     | Xm=⎣ |     |       |       |     | )⎦  |     |        |
|     |     |      | x(t | ) x(t | ) ··· | x(t | .   |     | (1.29) |
|     |     | 1    |     | 1     | 2     |     | m   |     |        |
Makinguseof(1.6),thismatrixreducesto
|     |     |      | ⎡   |     |     |       | ⎤   |     |        |
| --- | --- | ---- | --- | --- | --- | ----- | --- | --- | ------ |
|     |     | Xm=⎣ |     |     | ··· | Am−1x | ⎦   |     |        |
|     |     |      | x   | Ax  |     |       | .   |     | (1.30) |
|     |     | 1    |     | 1 1 |     |       | 1   |     |        |
Here is where the DMD method connects to Krylov subspaces and the Arnoldi al-
gorithm. Specifically, thecolumnsofXm areeach elementsinaKrylovspace. This
1

| 1.4. | Examplecodeanddecomposition |     |     |     |     |     | 11  |
| ---- | --------------------------- | --- | --- | --- | --- | --- | --- |
m−1
matrixattempts tofit the first datacollection points using the matrixA that
approximatestheKoopmanoperator. IntheDMDtechnique,thefinaldatapointx
m
isrepresented,asbestaspossible,intermsofthisKrylovbasis;thus
m(cid:7)−1
|     |     |     |     | x = | b x +r, |     | (1.31) |
| --- | --- | --- | --- | --- | ------- | --- | ------ |
|     |     |     |     | m   | k k     |     |        |
k=1
wherethe b arethecoefficientsoftheKrylovspacevectorsandristheresidual(or
k
error) that lies outside (orthogonal to) theKrylov space. Ultimately, thisbest fit to
thedatausingthisDMDprocedurewillbedoneinan(cid:2) senseusingapseudoinverse.
2
Inthisnotation,wehavethekeyresult(comparetothedefinition(1.16)):
Xm=AXm−1,
(1.32)
|     |     |     |     | 2   | 1   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
wheretheoperatorAischosentominimizetheFrobeniusnormof(cid:7)Xm−AXm−1(cid:7)
.
|     |     |     |     |     |     | 2   | 1 F |
| --- | --- | --- | --- | --- | --- | --- | --- |
Inotherwords,theoperatorAadvanceseachsnapshotcolumninXm−1asingletime
1
step, Δt, resulting in the future snapshot columns in Xm. The DMD outlined pre-
2
viouslycanthenbeenacted. ThisdefinitionofDMDissimilartothemoremodern
|     | definitionwithX→Xm−1, |     |     | (cid:5) →Xm, | andtheformulaAXm−1 | =Xm        |     |
| --- | --------------------- | --- | --- | ------------ | ------------------ | ---------- | --- |
|     |                       |     |     | X            |                    | equivalent | to  |
|     |                       |     | 1   | 2            |                    | 1 2        |     |
(1.16). However,thisformulationcanbethoughtofmorebroadlyanddoesnotnec-
essarilyneedtorelatedirectlyto(1.1).
| 1.4 | Example | code | and decomposition |     |     |     |     |
| --- | ------- | ---- | ----------------- | --- | --- | --- | --- |
TodemonstratetheDMDalgorithm,weconsiderasimpleexampleoftwomixedspa-
tiotemporalsignals. Inparticular,ourobjectiveistodemonstratetheabilityofDMD
toefficientlydecompose thesignal intoitsconstituentparts. Tobuild intuition,we
alsocompareDMDagainstresultsfromprincipalcomponentanalysis(PCA)andin-
dependentcomponentanalysis(ICA).
Thetwosignalsofinterestare
|     |     | f(x,t)= | (x,t)+f | (x,t) |     |     |     |
| --- | --- | ------- | ------- | ----- | --- | --- | --- |
f
|     |     |     | 1   | 2   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
=sech(x+3)exp(i2.3t)+2sech(x)tanh(x)exp(i2.8t).
(1.33)
|     |     |     |     |     | (x,t)andf (x,t)areillustratedinFigure1.2(a)– |     |     |
| --- | --- | --- | --- | --- | -------------------------------------------- | --- | --- |
Theindividualspatiotemporalsignalsf
|     |     |     |     | 1   | 2   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
(b). Thetwofrequenciespresentareω =2.3andω =2.8,whichhavedistinctspatial
|     |             |                |     | 1       | 2                                         |     |     |
| --- | ----------- | -------------- | --- | ------- | ----------------------------------------- | --- | --- |
|     |             |                |     | f(x,t)= | (x,t)+f (x,t)isillustratedinFigure1.2(c). |     |     |
|     | structures. | Themixedsignal |     |         | f                                         |     |     |
|     |             |                |     |         | 1 2                                       |     |     |
ThefollowingcodeinMATLABconstructsthespatiotemporalsignals.
ALGORITHM1.2.Mixingoftwospatiotemporalsignals.
|     | %% Define | time | and space | discretizations |     |     |     |
| --- | --------- | ---- | --------- | --------------- | --- | --- | --- |
xi = linspace(-10,10,400);
t = linspace(0,4*pi,200);
|     | dt = t(2)          | - t(1);            |     |                    |     |     |     |
| --- | ------------------ | ------------------ | --- | ------------------ | --- | --- | --- |
|     | [Xgrid,T]          | = meshgrid(xi,t);  |     |                    |     |     |     |
|     | %% Create          | two spatiotemporal |     | patterns           |     |     |     |
|     | f1 = sech(Xgrid+3) |                    | .*  | (1*exp(1j*2.3*T)); |     |     |     |
f2 = (sech(Xgrid).*tanh(Xgrid)).*(2*exp(1j*2.8*T));
|     | %% Combine | signals | and | make data | matrix |     |     |
| --- | ---------- | ------- | --- | --------- | ------ | --- | --- |

| 12  |     |     | Chapter1. | DynamicModeDecomposition: |             | AnIntroduction |
| --- | --- | --- | --------- | ------------------------- | ----------- | -------------- |
|     |     | (a) | f (x,t)   |                           | (b) f (x,t) |                |
1 2
|     |     | t   |      |     | t         |     |
| --- | --- | --- | ---- | --- | --------- | --- |
|     |     |     |      | x   |           | x   |
|     |     | (c) | x(t) |     | (d) x (t) |     |
DMD
|     |     | t   |     |     | t   |     |
| --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     | x   |     | x   |
(x,t)and(b)
|     |     | Figure1.2. | Anexampleofspatiotemporal |     | dynamicsoftwosignals(a) | f   |
| --- | --- | ---------- | ------------------------- | --- | ----------------------- | --- |
1
f (x,t)of (1.33)thataremixedin(c) f(x,t)= f (x,t)+ f (x,t). Thefunction f(x,t)canbe
|     | 2   |     |     |     | 1 2 |     |
| --- | --- | --- | --- | --- | --- | --- |
representedinsteadbyx(t).TheDMDofxwascomputed,andarank-2approximatereconstruction
(t)isshowninpanel(d).
(1.24)ofthesignalx DMD Thereconstructionisalmostperfect, withthe
(x,t)and (x,t).
DMDmodesandspectracloselymatchingthoseoftheunderlyingsignals f f
1 2
|     | f = | f1 + f2;    |             |     |     |     |
| --- | --- | ----------- | ----------- | --- | --- | --- |
|     | X = | f.’; % Data | Matrix      |     |     |     |
|     | %%  | Visualize   | f1, f2, and | f   |     |     |
figure;
subplot(2,2,1);
surfl(real(f1));
|     | shading  | interp;                                         | colormap(gray);           |     | view(-20,60); |     |
| --- | -------- | ----------------------------------------------- | ------------------------- | --- | ------------- | --- |
|     | set(gca, | ’YTick’,                                        | numel(t)/4                |     | * (0:4)),     |     |
|     | set(gca, | ’Yticklabel’,{’0’,’\pi’,’2\pi’,’3\pi’,’4\pi’}); |                           |     |               |     |
|     | set(gca, | ’XTick’,                                        | linspace(1,numel(xi),3)), |     |               |     |
|     | set(gca, | ’Xticklabel’,{’-10’,                            |                           |     | ’0’, ’10’});  |     |
subplot(2,2,2);
surfl(real(f2));
|     | shading  | interp;                                         | colormap(gray);           |     | view(-20,60); |     |
| --- | -------- | ----------------------------------------------- | ------------------------- | --- | ------------- | --- |
|     | set(gca, | ’YTick’,                                        | numel(t)/4                |     | * (0:4)),     |     |
|     | set(gca, | ’Yticklabel’,{’0’,’\pi’,’2\pi’,’3\pi’,’4\pi’}); |                           |     |               |     |
|     | set(gca, | ’XTick’,                                        | linspace(1,numel(xi),3)), |     |               |     |
|     | set(gca, | ’Xticklabel’,{’-10’,                            |                           |     | ’0’, ’10’});  |     |
subplot(2,2,3);
surfl(real(f));
|     | shading | interp; | colormap(gray); |     | view(-20,60); |     |
| --- | ------- | ------- | --------------- | --- | ------------- | --- |

1.4. Examplecodeanddecomposition 13
| set(gca, | ’YTick’,                                        | numel(t)/4                | * (0:4)),    |
| -------- | ----------------------------------------------- | ------------------------- | ------------ |
| set(gca, | ’Yticklabel’,{’0’,’\pi’,’2\pi’,’3\pi’,’4\pi’}); |                           |              |
| set(gca, | ’XTick’,                                        | linspace(1,numel(xi),3)), |              |
| set(gca, | ’Xticklabel’,{’-10’,                            |                           | ’0’, ’10’}); |
This code produces the data matrix X of (1.10). X is the starting point for the
decompositionalgorithmofDMD,PCA,andICA.Thefollowingcodeimplements
DMDfollowingthestepsoutlined in thelastsubsection. Inthisparticular case, we
alsoperform arank-2 decomposition toillustrate thelow-dimensional natureof the
decomposition.
ALGORITHM1.3.PerformDMDondata.
| %% Create         | DMD data          | matrices    |     |
| ----------------- | ----------------- | ----------- | --- |
| X1 = X(:,         | 1:end-1);         |             |     |
| X2 = X(:,         | 2:end);           |             |     |
| %% SVD            | and rank-2        | truncation  |     |
| r = 2;            | % rank truncation |             |     |
| [U, S,            | V] = svd(X1,      | ’econ’);    |     |
| Ur = U(:,         | 1:r);             |             |     |
| Sr = S(1:r,       | 1:r);             |             |     |
| Vr = V(:,         | 1:r);             |             |     |
| %% Build          | Atilde and        | DMD Modes   |     |
| Atilde            | = Ur’*X2*Vr/Sr;   |             |     |
| [W, D]            | = eig(Atilde);    |             |     |
| Phi = X2*Vr/Sr*W; |                   | % DMD Modes |     |
%% DMD Spectra
| lambda     | = diag(D);      |     |     |
| ---------- | --------------- | --- | --- |
| omega =    | log(lambda)/dt; |     |     |
| %% Compute | DMD Solution    |     |     |
| x1 = X(:,  | 1);             |     |     |
b = Phi\x1;
| time_dynamics         | = zeros(r,length(t)); |                            |     |
| --------------------- | --------------------- | -------------------------- | --- |
| for iter              | = 1:length(t),        |                            |     |
| time_dynamics(:,iter) |                       | = (b.*exp(omega*t(iter))); |     |
end;
| X_dmd = | Phi*time_dynamics; |     |     |
| ------- | ------------------ | --- | --- |
subplot(2,2,4);
surfl(real(X_dmd’));
| shading  | interp; colormap(gray);                         |                           | view(-20,60); |
| -------- | ----------------------------------------------- | ------------------------- | ------------- |
| set(gca, | ’YTick’,                                        | numel(t)/4                | * (0:4)),     |
| set(gca, | ’Yticklabel’,{’0’,’\pi’,’2\pi’,’3\pi’,’4\pi’}); |                           |               |
| set(gca, | ’XTick’,                                        | linspace(1,numel(xi),3)), |               |
| set(gca, | ’Xticklabel’,{’-10’,                            |                           | ’0’, ’10’});  |
This code computes several important diagnostic features of the data, including the
Φ,
singular values of the data matrix X, the DMD modes and the continuous-time
DMD eigenvalues ω. The eigenvalues ω match the underlying frequencies exactly,

| 14  |     |     | Chapter1. DynamicModeDecomposition: |     |     | AnIntroduction |
| --- | --- | --- | ----------------------------------- | --- | --- | -------------- |
wheretheirimaginarycomponentscorrespondtothefrequenciesofoscillation:
|     | omega  | =         |     |     |     |     |
| --- | ------ | --------- | --- | --- | --- | --- |
|     | 0.0000 | + 2.8000i |     |     |     |     |
|     | 0.0000 | + 2.3000i |     |     |     |     |
Following(1.24),arank-2DMDreconstructionX ispossible,separatingthe
DMD
dataXintoasumofcoupledspatiotemporalmodes. Thisreconstructionisshownin
Figure1.2(d). Figure1.3(a)showsthedecayofsingularvaluesofX,whichrevealsthat
thedatamaybeappropriatelyrepresented asrank r =2. Figure1.3(a)comparesthe
temporal andspatial modesasextracted by DMDwiththetruemodes; theseDMD
modesalmostexactlymatchthetruesolutionmodes f (x,t)and f (x,t).
|     |     |     |     |     | 1   | 2   |
| --- | --- | --- | --- | --- | --- | --- |
To built intuition for DMD, we compare it against two commonly used modal
decomposition techniques, PCA and ICA. The following code computes the PCA
modesandtheirtemporalevolution.
ALGORITHM1.4.PCAcomputedbySVD.
|     | [U, S, V]  | = svd(X);    |            |           |        |     |
| --- | ---------- | ------------ | ---------- | --------- | ------ | --- |
|     | pc1 = U(:, | 1); % first  | PCA mode   |           |        |     |
|     | pc2 = U(:, | 2); % second | PCA mode   |           |        |     |
|     | time_pc1   | = V(:, 1);   | % temporal | evolution | of pc1 |     |
|     | time_pc2   | = V(:, 2);   | % temporal | evolution | of pc2 |     |
Inasimilarfashion,wecanalsoperformanICAdecomposition. Thereexistseveral
implementationsofICA;hereweusefasticafromaMATLABpackage[105].
ALGORITHM1.5.FastICA.
|     | [IC, ICt,   | ~] = fastica(real(X)’); |            |           |        |     |
| --- | ----------- | ----------------------- | ---------- | --------- | ------ | --- |
|     | ic1 = IC(1, | :); % first             | ICA mode   |           |        |     |
|     | ic2 = IC(2, | :); % second            | ICA mode   |           |        |     |
|     | time_ic1    | = ICt(:, 1);            | % temporal | evolution | of ic1 |     |
|     | time_ic2    | = ICt(:, 2);            | % temporal | evolution | of ic2 |     |
PCA and ICA extract modal structures contained in the data matrix X; Figure
1.3showsthesemodesascomparedtoDMDmodesandthetruesolution. PCAhas
nomechanismtoseparatetheindependentsignals f (x,t)and f (x,t). Itdoes,how-
|     |     |     |     |     | 1 2 |     |
| --- | --- | --- | --- | --- | --- | --- |
ever, produce the correct rank-2 structure. The PCA modes produced in a rank-2
decomposition are chosen to maximize the variance in the data. They mix the two
spatiotemporal modes, as shown in Figure 1.3(e) and (f). Thetime dynamics of the
PCA modes arealso shown in Figure 1.3(c) and (d). TheICA resultsare much bet-
terthanthePCAresultssinceICAattemptstoaccountfortheindependentnatureof
thetwosignals [166]. TheICA modesand timedynamicsare alsoshownin Figure
1.3(c)–(f).
To make quantitative comparisons among DMD, PCA, and ICA, Figure 1.3(b)
showsthe(cid:2)
-norm ofthedifference between thetwotruespatial modes andmodes
2
extractedbythethreealgorithms. ThePCAmodeshavethelargesterror,whilethe
DMDmodesareaccuratetonearlymachineprecision. TheICAerrorislessthanhalf
theerror associated with PCA.Thiscomparison showsthe relativemeritsofDMD
anditsefficiencyindecomposingspatiotemporaldata.

1.5. LimitationsoftheDMDmethod 15
(a)SingularValues (b)ModeError
0.6 DMD Mode1
PCA
ICA
σ 0.4
k
DMD Mode2
0.2
PCA
ICA
0
0 10 20 0 0.5 1
k E
(c) Mode1:Temporal
1
0
-1
(d) 0 π 2π 3π t 4π
Mode2:Temporal
1
0.5
0
-0.5
0 π 2π 3π t 4π
(e)
0.1 Mode1:Spatial
True
DMD
0
PCA
ICA
-0.1
x
-10 -5 0 5 10
(f)
0.15 Mode2:Spatial
0.1
0.05
0
-0.05
-10 -5 0 5 x 10
Figure1.3. AcomparisonofDMDwithPCAandICAasappliedtoexampledatagen-
eratedwith(1.33). Thesingularvaluesin(a)showthatarank-2truncationisappropriate. Panels
(c)–(f)comparethetemporalandspatialaspectsofthetwomodes,wherethetruemodesareplotted
alongwithmodesextractedbyDMD,PCA, andICAfromthedata. DMDproducesresultsthat
areexactly(tonumericalprecision)alignedwiththetruesolution.ICAmodesapproximatethetrue
modesbetterthanPCAdoes,butbothdeviatefromthetruesolution. The(cid:2) -normdifferencebe-
2
tweenthetwotruespatialmodesandmodesextractedbyDMD,PCA,andICAareshownin(b).
DMDmodesmatchthetruemodesexactlyandhavezeroerror.
1.5 Limitations of the DMD method
TheDMDmethod,muchlikePCA,isbasedonanunderlyingSVDthatextractscor-
related patterns in the data. It is well known that a fundamental weakness of such

| 16  |             | Chapter1. | DynamicModeDecomposition: |     | AnIntroduction |            |
| --- | ----------- | --------- | ------------------------- | --- | -------------- | ---------- |
|     | (a) f (x,t) |           | (b) f (x,t)               |     | (c)x(t)        |            |
|     | 1           |           | 2                         |     |                |            |
|     | (d)x        | (t),r =2  | (e)x (t),r                | =5  | (f)x           | (t), r =10 |
|     | DMD         |           | DMD                       |     | DMD            |            |
t
x
Figure1.4.Anexampleofspatiotemporaldynamicswithtranslation(1.34).Panels(a)–
(c)illustratetherealpartsofthetwosignalsandtheirmixture. Panels(d)–(f)showreconstructions
ofthesignalx (t)usingrank-2,rank-5,andrank-10approximations. Althoughthedynamicsare
DMD
constructedfromatwo-modeinteraction,thereconstructionnowrequiresapproximately10modes
togettherightdynamics.
SVD-based approaches is the inability to efficiently handle invariances in the data.
Specifically,translationaland/orrotationalinvariancesoflow-rankobjectsembedded
inthedataarenotwellcaptured. Moreover, transienttimephenomenaarealsonot
wellcharacterizedbysuchmethods. Thiswillbeillustratedinvariousexamplesthat
follow.
| 1.5.1 Translational |     | and rotational | invariances |     |     |     |
| ------------------- | --- | -------------- | ----------- | --- | --- | --- |
TodemonstratetheDMDalgorithmandsomeofitslimitations,weonceagaincon-
siderthesimpleexampleoftwomixedspatiotemporalsignals. Inthiscase,however,
oneofthesignalsistranslatingataconstantvelocityacrossthespatialdomain. The
twosignalsofinterestare
|     | f(x,t)= | (x,t)+f (x,t) |     |     |     |     |
| --- | ------- | ------------- | --- | --- | --- | --- |
f
1 2
=sech(x+6−t)exp(i2.3t)+2sech(x)tanh(x)exp(i2.8t).
(1.34)
Asbefore, thetwofrequenciespresentareω =2.3andω =2.8,withgivencorre-
|     |     |     |     | 1   | 2        |        |
| --- | --- | --- | --- | --- | -------- | ------ |
|     |     |     |     |     | (x,t)and | (x,t), |
spondingspatialstructures. Theindividualspatiotemporalsignals f f
|     |     |     |     |     | 1   | 2   |
| --- | --- | --- | --- | --- | --- | --- |
along with the mixed solution f(x,t) = f (x,t)+ f (x,t), are illustrated in Figure
|     |     |     | 1   | 2   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
1.4(a)–(c), respectively. In this case, the MATLAB code is reevaluated using rank-2,
rank-5, and rank-10 reconstruction. The rank-2 reconstruction is no longer able to
characterizethedynamicsduetothetranslation. Indeed,itnowtakesnearly10modes
toproduceanaccurate reconstruction. Thisartificial inflationofthedimensionisa
resultoftheinabilityofSVDtocapturetranslationalinvariancesandcorrelateacross
snapshotsoftime.
Tovisualizethisartificialinflationindimension,Figure1.5(a)showsthesingular
valuesofX,whichareusedinbothDMDandPCA.Althoughtherearestillonlytwo

1.5. LimitationsoftheDMDmethod 17
(a)
0.4 SingularValues
0.3
σ
k 0.2
0.1
0
0 10 20
k
(b)
0.3
Mode1:Spatial
0.2
True
0.1 DMD
0 PCA
ICA
-0.1
-10 -5 0 5 x 10
(c)
0.3
Mode2:Spatial
0.2
0.1
0
-10 -5 0 5 x 10
Figure1.5.ComparisonofDMDwithPCAandICAforspatiotemporaldynamicswith
translation. Thesingularvaluedecayin(a)showsthatarank-2truncationisnolongerappropriate
duetothetranslation ofoneofthemodes. The(b)firstand(c)secondmodes(normalizedbythe
maximumvalue)generated from all three methods are compared to the truesolution. None are
alignedwiththetruesolution.
true modes, the SVD suggests that at least 10 modes are required to converge to an
accuratesolution. Figure1.5(c)and(d)illustratethefirsttwomodesgenerated from
DMD,PCA,andICA.Notethesignificantlydifferentmodalstructuresgeneratedby
each algorithm in thiscase. Ultimately, noneof themethods handlethetranslation
in any viable way. Any continuous symmetry in a data set will produce similarly
poorlow-rankcharacterizations. ThediscussionofmultiresolutionDMD(mrDMD)
inChapter5includesonewaytohandlethisissueinpractice.
1.5.2 Transient time behavior
TransientphenomenaarealsodifficultforDMD,PCA,and/orICAmethodstohan-
dle.Todemonstratetheimpactofthetransienttimedynamics,weonceagainconsider
thesimpleexampleoftwomixedspatiotemporalsignals,withoneturningonandoff
duringthetimedomain. Inthiscase,thesignalsare
f(x,t)= f (x,t)+f (x,t)
1 2
=0.5sech(x+5)exp(i2.3t)[tanh(t−π)−tanh(t−3π)]
+2sech(x)tanh(x)exp(i2.8t). (1.35)

| 18  |     | Chapter1. | DynamicModeDecomposition: |             | AnIntroduction |
| --- | --- | --------- | ------------------------- | ----------- | -------------- |
|     | (a) | f (x,t)   |                           | (b) f (x,t) |                |
1 2
|     | t   |      |     | t     |     |
| --- | --- | ---- | --- | ----- | --- |
|     |     |      | x   |       | x   |
|     |     | x(t) |     | (t)   |     |
|     | (c) |      |     | (d) x |     |
DMD
|     | t   |     |     | t   |     |
| --- | --- | --- | --- | --- | --- |
|     |     |     | x   |     | x   |
Figure1.6. Examplespatiotemporal dynamics(realpart) oftwosignalsof (1.35)that
(t)fromarank-
havetransientdynamics. Panel(d)illustratesthereconstructionofthesignalx
DMD
10approximation(1.24).Thereconstructionfailstocapturetheon-offnatureofthemode.
Asbefore, thetwofrequenciespresentareω =2.3andω =2.8,withgivencorre-
1 2
(x,t)and (x,t),
spondingspatialstructures. Theindividualspatiotemporalsignals f f
1 2
alongwiththemixedsolution f(x,t),areillustratedinFigure1.6(a)–(c),respectively.
WecanonceagaintrytoreconstructthesolutionusingDMD.Interestingly,regardless
=10inthefigure),DMDisincapableofcorrectlygettingtherightturn-
oftherank(r
onandturn-offbehaviorofthefirstmode. Theresultshownisthesameforanyrank
approximation above two. Unlike the translational or rotational invariance, which
simplycreatedanartificiallyhighdimensioninDMD,inthiscaseDMDcompletely
failstocharacterizethecorrectdynamics. mrDMDinChapter5presentsapotential
strategytohandlethisissue.
| 1.6 Broader | context | of equation-free |     | methods |     |
| ----------- | ------- | ---------------- | --- | ------- | --- |
OnemayconsiderDMDasanequation-freewaytoapproximateanonlineardynam-
icalsystem. Often,(1.1)arisesasadiscretizationofapartialdifferentialequation
|     |     | =N(q,q |         | ,...,ξ,t;μ), |        |
| --- | --- | ------ | ------- | ------------ | ------ |
|     |     | q      | ξ ,q ξξ |              | (1.36) |
t
whereq(ξ,t)representsavectorofthevariablesofinterest,thesubscriptsdenotepar-
tialdifferentiationwithrespecttoeithertimeorspace,andN(·)determinesthenonlin-
eargoverningevolutionequations. Theevolutionequationsdependgenericallyupon
time,t,andthespatialvariable,ξ,andderivativesofthequantityofinterestq. Forin-
stance,thevectorq(ξ,t)mightrepresentthevelocity,temperature,andpressurefields
inacomplex,three-dimensionalfluidflowsystem. Thus,therewouldbeasetoffive

1.6. Broadercontextofequation-freemethods 19
coupled partial differential equations governing the overall dynamics of the system.
The vector μ determines the values of one or more parameters in the complex sys-
tem;astheseparametersvary,thesystemmayexhibitdrasticallydifferentbehaviors,
characterized bybifurcations. Inthefluidexampleabove, thebifurcation parameter
μwouldrepresentcriticalquantitiesliketheReynoldsnumber.
Equation (1.36) provides a very general model framework for studying complex
systems. Intraditionaldynamicalsystemsmodelingandscientificcomputing,acriti-
calassumptionismadeabout(1.36). Namely,weknowthegoverningequations,and
thusthenonlinearfunctionN(·). However,itisalmostalwaysthecasethattheright-
handsideisapproximatedusingasymptoticargumentsorneglectingwhatarethought
tobeunimportantphysicalterms. Forinstance,wetypicallyneglecttheeffectsofair
frictionwhenmodelingasimplependuluminourdifferentialequationscourses. For
sufficientlycomplexsystems,constructinganaccuratesetofgoverningequationsand
functionN(·)isextremelychallengingandconfoundedbymultiscalephysicseffects.
Indeed, understanding the interaction of microscale and macroscale phenomena in
many engineering, physical, and biological systems is at the forefront of current re-
search methods. DMD reverses this process and instead uses the abundance of data
collectedtoreverse-engineerthegoverningequationsdirectlyfromdata.
Theriseofequation-freemodelingtechniqueschallengesthefoundationalnotion
that N(·) is known. In particular, equation-free strategies seek to relax the assump-
tionconcerningknowledgeofN(·)byexploitingsamplinganddatacollectioninthe
complexsystem. Suchdata-drivenstrategiesarecapableoftransformativeimpact,es-
peciallyinsystemswheretraditionalmodelingmethodsfailduetolackofinformation
andinsightintotheevolutionequation(1.36). Asaspecificexample,atmosphericsci-
encesandweatherforecastinghaveseentremendousperformancegainsinprediction
byusingdata-assimilationtechniques, e.g., ensembleKalmanfiltering. Interestingly,
thefield of weatherforecasting has along history of model development. Thus the
continueddevelopmentoftraditionalfirst-principlesmodelingtechniques,especially
thosethatmodelthemyriadofmultiscalephysicseffects,areaimedatimprovingour
constructionofN(·)in(1.36). Inemergingfieldssuchascomputationalneuroscience,
itisextremelydifficultatthistimetoconstructfirst-principlesequations(1.36). Such
systems are known to be both dynamical and highly networked, with only limited
knowledgeofthenetworkarchitecturecurrentlyavailable. Thus,forsuchasystem,
constructing an accurate N(·) is a challenging proposition. Both of these examples
highlightthecrucialneedtointegratedata-drivenstrategiesinmodelingefforts. More-
over,giventheirsensitivitytoinitialconditions,evenhavinganaccurateN(q)poses
significant problems in accurate future-state prediction, thus again highlighting the
needtointegratedatameasurementswithinthemodelingarchitecture.
Data-driventechniquesfordealingwithcomplexsystems(1.36)areofgrowingin-
terestinthemathematicalsciencescommunity. Moreover,theyarehavingsignificant
impact across the engineering, physical, and biological sciences. DMD is only one
ofahandful ofdifferent techniques available fordata-driven modeling. Assuch, we
highlight a number of example techniques that are at the forefront of mathematical
developmentsformodelingandcomputinghigh-dimensionalcomplexsystems(1.36).
Themethodshighlightedareillustrativeoftechniquesandphilosophies,andthisisby
nomeansanexhaustivelist.

20 Chapter1. DynamicModeDecomposition: AnIntroduction
1.6.1 Equation-free, multiscale projections
Kevrekidisandco-workers[107,161,260,160]havedevelopedanequation-freearchi-
tecture with the moniker equation-free methods (EFMs) that capitalizes on inherent
multiscalephenomena. Thecentralthemeofthemethodisthefactthatthemacroscale
evolution dynamics and/or variables are unknown. Thus, evolving (1.36) to future
states is not viable given the ambiguity in the macroscale dynamics. However, the
methodalsoassumesthatthemicroscalephysicsdrivingthelargermacroscopicevolu-
tion,whichisoftenstochasticinnature,isinfactknown. Thefundamentalquestion
arisesastohowtoconnectthemicroscaledynamicstothelargermacroscale. Thus,
thetermequation-freereferstotheunknownmacroscaleevolutiondynamics.
TheEFMreliesonamultistepprocedureofliftingandrestriction,whicharemeth-
ods for moving from microscale to macroscale variables and vice versa. Mathemat-
ically, the problem formulation results in an attempt to computationally construct
themacroscopic,orcoarse-grained, dynamicalevolution(1.36),wherethegoverning
equationsdeterminedbyN(·)in(1.36)areunknown. Importantly,oneneedsonlya
computationalapproximationtoN(·)tocomputeafuturestate. Inparticular,anEu-
lertime-steppingalgorithmsimplymakesuseofaslopeformulaandthedefinitionof
derivativetocomputethefuturestatet fromstatet :
k+1 k
q(ξ,t )=q(ξ,t )+ΔtN˜(q(ξ,t ),ξ,t ), (1.37)
k+1 k k k
whereΔt = t −t andN˜ isamacroscale, typicallylow-dimensional,approxima-
k+1 k
tion of the full nonlinearity N(·). As such, the Euler method essentially provides a
template,orprotocol,forafuture-stateestimation.
Thealgorithmbeginswithmicroscalesimulationordatacollectionofthesystem
ofinterest. Therestrictionsteplooksformethodsthatcanperformadimensionality
reductionofthedatathrough,forexample,anSVD.ItisassumedintheEFMthatthe
unknown governing equations (1.36) have an underlying slow manifold that all the
dynamicscollapseonto. Thegoalofthedimensionalityreductionstepistorepresent
the dynamics on this low-rank attractor in the natural variables of the system (e.g.,
POD modes). Once the microscale dynamics have collapsed to the slow manifold,
then the reduced variables are used to take a time step represented by (1.37) with a
computed value of N˜ that is evaluated on the low-rank attractor. This time step is
in the macroscopic variables and is much larger than any time step allowed in the
microscaledynamics. Aftertakingalargemacroscaletimestep,theliftingprocedure
isusedtoreinitializeamicroscalesimulationbasedonthestateofthetime-advanced
macroscopicevolution. Thisalgorithmadvancesthesolutionbyalternatingbetween
themicroscopicandmacroscopicvariablesthroughrestrictionandliftingsteps.
1.6.2 Reduced-order models
Reduced-ordermodels(ROMs) areplayinganincreasinglyimportantroleinsimula-
tionstrategiesandfuture-statepredictionforhigh-dimensional,complexsystems[228].
Althoughnotinherentlyequationfree, ROMsaimtocapitalizeonlow-dimensional
structures in the dynamics, much as the DMD and EFM strategies do. Specifically,
ROMslooktoconstructrepresentationsofthesolutionq(ξ,t)insomeoptimal ba-
sis(e.g., PODmodes). Similarlytoboth DMDandEFM,snapshotsoftheevolving
systemareacquiredandthelow-ranksubspaceonwhichq(ξ,t)evolvesisextracted.
Oftenthisstrategyofdataacquisitionisdoneinanoff-linemannergivenhowcompu-
tationallyexpensive itcan betosamplethehigh-dimensional simulation space. The

1.6. Broadercontextofequation-freemethods 21
low-ranksubspaces,oncecomputed,canthenbeusedinanonlinefashiontocompute
futurestates.
TheROMarchitecturecaneasilybecombinedwiththeEFM[260]andwithDMD
[300]. Indeed,themethodspartnernaturallysincetheybothaimtoexploitlow-rank
dynamics. ROMsandEFMscan alsotakeadvantageoflimitedmeasurements [108]
to advance the solution in time. Interestingly, the state-of-the-art ROM techniques
make a point to capitalize on limited measurements. The gappy POD [92], for ex-
ample,constructsaccurateGalerkin-PODapproximationsofcomplexsystems[133]
fromlimited,incomplete, orcorrupted measurements. Firstintroduced byEverson
andSirovich[92],thegappymethoddidnotadvocateaprincipledsensorplacemental-
gorithmuntiltheworksofWillcox[298],Karniadakis[309],Sorenson[63],andtheir
co-workers. Morerecently,thelow-rankPODapproximationswerecombinedwith
compressed sensing to perform sensor tasks and ROM computations [36, 49, 242].
Sensor placement based on alternative criteria, such as providing accurate classifica-
tion or clusteringof data[280,304,68, 43, 14], may also be important in modeling
efforts. WewillalsoconsidertheroleoflimitedmeasurementsintheDMDmethod
inChapter9,asitisclearthatsuchtechniquescanbecriticallyenablinginmanyap-
plications.
1.6.3 Stochastic-statisticaldynamical systems methods
DMDandEFMsattempttoprovideapproximationsto(1.36)byeitherabest-fitregres-
siontoalineardynamicalsystemthroughthesampleddataoratime-scaleseparation
algorithmthatalternatesbetweenliftingandrestrictiontonumericallyconstructN(·),
respectively. Anotheremergingsetoftechniquesthatacknowledgefromthestartthe
lackofanaccurategoverningsetofequationsrevolvearoundtheconceptofstochastic-
statisticaldynamicalsystems[188,35]. Theideaofsuchmethodsistousemultimodel
ensembleforecaststoimprovethestatisticalaccuracyofimperfectpredictionsthrough
combininginformationfromacollectionofROMs.
Thisinformation-theoreticframeworkcapitalizesonacollectionofimperfect,po-
tentiallylow-fidelitymodels,suchasROM-typemodels,toimprovefuture-statepre-
dictionsinastatisticalway. Innovationsinthisareacenteraroundunderstandingun-
certaintyquantificationmetricsandtheirroleinweightingthevariousROMpredic-
tions. Interestingly,thephilosophical leaningsofthisapproacharecloselyrelatedto
thedevelopmentsofthemachinelearningmethodofboosting. Inparticular,Kearns
and Valiant [155, 156] formulated the question: Can a set of weak learners create a
singlestronglearner? Aweaklearnerisdefinedtobeaclassifierthatisonlyslightly
correlatedwiththetrueclassification(itcanlabelexamplesbetterthanrandomguess-
ing). Incontrast,astronglearnerisaclassifierthatisarbitrarilywellcorrelatedwith
thetrueclassification. In1990,Schapire [246]showedthatthiswasindeedthecase.
Not onlywerethere significant ramifications in machinelearning and statistics,but
alsothisseemstohaveimportantimplicationsforcomplexdynamicalsystems.
Fromtheviewpointofcomplexsystems,itisappropriatetorestateaninsightful
quotefromareviewarticleofA.Majdaconcerningclimatemodeling[188]:
Thecentraldifficultyinclimatechangescienceisthatthedynamicalequa-
tionsfortheactualclimateareunknown. Allthatisavailablefromthetrue
climate in nature are some coarse-grained observations of functions suchas
meanorvarianceoftemperature,tracergreenhousegasessuchascarbondiox-
ide, or the large-scale horizontal winds. Thus, climate change science must

22 Chapter1. DynamicModeDecomposition: AnIntroduction
copewithpredictingthecoarse-graineddynamicchangesofanextremelycom-
plexsystem only partially observedfrom a suite of imperfect models forthe
climate.
1.7 Interdisciplinary connections of DMD
TheunderlyingideasoftheDMDalgorithmhaveastrongintuitiveappeal. Indeed,the
Koopmanconstructionconceptdatesbacktothe1930sandprovidesasimpleframe-
work for understanding the flow of measurements on the state of a system into the
future. Giventhelonghistoryoftheidea,itisnotsurprisingthatmanyfieldshavede-
velopedsimilarideasforspecificapplicationsofinterest. Inwhatfollows,weillustrate
afewexampleapplicationsthatarecloselyrelatedtoDMD.
1.7.1 ARIMA: Autoregressive integrated moving average
Instatisticsandeconometrics,andinparticularintime-seriesanalysis,autoregressive
movingaverage(ARMA)modelsandthegeneralizedautoregressiveintegratedmoving
average(ARIMA)models[32]arecommonlyused. Thesemodelsarefittedtotime-
seriesdataeithertobetterunderstandthedataortopredictfuturepointsintheseries
(forecasting). ARIMAmodelsare often applied todatathat showsevidenceofnon-
stationarity,whereaninitialdifferencingstep(correspondingtothe“integrated”part
ofthemodel)canbeappliedtoreducethenonstationarity. Suchmodelsarecharacter-
izedbyanumberofkeyparameters,oneofthembeingthenumberofpasttimepoints
usedtoforecastafuturepoint. ThisissimilartowhatDMDaccomplishes. However,
DMDlinkseachtimesnapshotdirectlytotheprevioustimesnapshot.
AnumberofvariationsontheARIMAmodelarecommonlyemployedandallow
ustoconnectthemethodmorecloselytoDMD.Ifmultipletimeseriesareused,which
wouldbethecaseforDMD,thenARIMAcanbegeneralizedtoavectorframework,
i.e.,theVARIMA(vectorARIMA)model. Sometimesaseasonaleffectisexemplified
in the time series, in which case oscillatory behavior should be modeled. For such
cases,itisgenerallycommontousetheSARIMA(seasonalARIMA)modelinsteadof
increasingtheorderoftheARorMApartofthemodel.IntheDMDarchitecture,sea-
sonalvariationsareautomaticallyincluded. Moreover,ifthemeanofthedatamatrix
Xissubtracted,thenDMDhasbeenshowntobeequivalenttoaFourierdecomposi-
tionofthevectorfieldintime[64]. DMDcanbethoughtofastakingadvantageof
boththevectornatureofthedataandanyoscillatory(seasonal)variations. Further,
therealpartoftheDMDspectrum allowsonetoautomaticallycaptureexponential
trendsinthedata.
1.7.2 LIM: Linear inverse modeling
Linearinversemodeling(LIM)wasdevelopedintheclimatesciencecommunity. LIM
isessentiallyidenticaltotheDMDarchitectureundercertainassumptions[290]. By
construction, LIM relies on low-rank modeling, like DMD, using the empirical or-
thogonal functions (EOFs) first introduced in 1956 by Lorenz [181]. Used in the
climate science literature, EOFs are the result of applying PCA to meteorological
data[215];thus,EOFsareessentiallyPODmodes. Nearlytwodecadesbeforethefirst
DMDpapersappeared,Penland[215]derivedamethodtocomputealineardynamical
systemthatapproximatesdatafromastochasticlinearMarkovsystem;thesesystems
willberevisitedinChapter7. ThismethodlatercametobeknownasLIM[216].

1.7. InterdisciplinaryconnectionsofDMD 23
Undercertaincircumstances,DMDandLIMmaybeconsideredasequivalental-
gorithms. LIMisalsoperformedinthelow-dimensionalspaceofEOF/PODcoeffi-
cientscomputedonthefirstm−1snapshotsinXm−1.
SinceLIMconsiderssequential
1
snapshotdatawhereXm−1andXmonlydifferbyasinglecolumn,itoftenmakeslittle
1 2
differencewhichmatrixisusedtocomputeEOFs[216]. Giventheseassumptions,the
equivalenceofprojectedDMDandLIMgivesusyetanotherwaytointerpretDMD
analysis. Ifthedatameanisremoved,thenthelow-rankmapthatgeneratestheDMD
eigenvaluesandeigenvectorsissimplytheonethatyieldsthestatisticallymostlikely
state in the future. This is the case for both exact and projected DMD, as both are
built on thesame low-orderlinear map. LIM istypically performed fordata where
themeanhasbeensubtracted,whereasDMDisvalidwithorwithoutmeansubtrac-
tion. Regardless, there is a strong enough similarity between the two methods that
theDMD community may benefit from further investigatingthe use ofLIM in the
climatescienceliterature. Similarly,climatesciencemaybenefitfromrecentalgorith-
micdevelopmentsandextensionstoDMD.
1.7.3 PCR: Principal component regression
Instatistics,principalcomponentregression(PCR)isaregressionanalysistechnique
thatisonceagainbased on PCA.PCRregresses theoutcome(also knownasthere-
sponseorthedependentvariable)ontheprincipalcomponentsofasetofcovariates
(alsoknownaspredictorsorexplanatoryvariablesorindependentvariables)basedon
astandardlinearregressionmodel.
InPCR,whichpredatesDMDbyalmostthreedecades[148],insteadofregressing
thedependentvariableontheexplanatoryvariablesdirectly,theprincipalcomponents
oftheexplanatory variables are used as regressors. Onetypically usesonly asubset
ofalltheprincipalcomponentsforregression,thusmakingPCRaregularizedproce-
dure. Oftentheprincipalcomponentswithlargervariancesareselectedasregressors;
theseprincipalcomponentscorrespondtoeigenvectorswithlargereigenvaluesofthe
samplevariance-covariancematrixoftheexplanatoryvariables. However,forthepur-
poseofpredictingtheoutcome,principalcomponentswithlowvariancesmayalsobe
important,insomecasesevenmoreimportant[148,143].
UnliketheDMD/LIMliterature,whichhastraditionallybeensteepedindynam-
ics,thestatisticsliteratureisoftenconcernedwithregressionofstaticdata. PCRisa
linearregressionthatfindsrelationshipsoftheoutputvariablesintermsofthePCA
oftheinputvariables. TypicallyPCRisnotspecificallyappliedtotime-seriesdatabut
isinsteadageneralregressionprocedurethatmayormaynotbeappliedtodatafrom
adynamicalsystem. Insomesense,thefirsttwostepsoftheDMDalgorithmmaybe
viewedasperformingPCRonsnapshotdatafromahigh-dimensionaldynamicalsys-
tem. However,PCRdoesnotincludetheadditionalstepsofeigendecomposition of
thematrixA˜ orthereconstructionofhigh-dimensionalcoherentmodes. Thislaststep
iswhatrelatesDMDtotheKoopmanoperator,connectingdataanalysistononlinear
dynamics.
1.7.4 System identification methods
Systemidentificationmethodsfromthecontrolcommunityareintimatelyconnected
toDMD.PreviousworkhasestablishedtheconnectionbetweenDMDandtheeigen-
system realization algorithm (ERA) [151, 290]. Subsequently, DMD with control
(DMDc)wasalsolinkedtoERAandtheobserverKalmanfilteridentificationmeth-

24 Chapter1. DynamicModeDecomposition: AnIntroduction
ods(OKID)[222],aswillbediscussedinChapters6and7. ERAandOKIDconstruct
input-output models using impulse response data and continuous disturbance data,
respectively[151,152,220,218,150]. Bothofthesemethodsweredevelopedtocon-
struct input-output state-space models for aerospace applications where the systems
tend to have higher rank than the number of sensor measurements [132, 151]. In
contrast,DMDandDMDcweredevelopedforsystemswithalargenumberofmea-
surementsandlow-rankdynamics. Further,theDMDmethodshavebeenconnected
totheanalysisofnonlinearcomplexsystems[162,196,235,195].
ERAandOKIDhavealsobeencategorizedassubspaceidentificationmethods[226].
AnumberofsignificantconnectionshavebeenidentifiedbetweenDMDcandother
prominentsubspaceidentificationmethods[222]. Thesemethodsincludethenumer-
ical algorithms for subspace system identification (N4SID), multivariable output er-
rorstate space (MOESP), and canonical variate analysis(CVA) [292,293, 154, 226].
Algorithmically, these methods involve regression, model reduction, and parameter
estimationstepssimilartoDMDc. Thereareimportantcontrastsregardingthepro-
jectionscalingbetweenallofthesemethods[222]. Similarresearchhascombinedsys-
temidentificationmethodsandbalancedtruncationtoconstructROMsofnonlinear
input-outputsystems[201,123].
Recent advances in machinelearning, compressed sensing, and datascience have
resultedinpowerfulnonlineartechniquesinsystemidentification. Geneticprogram-
ming[165],alsoknownassymbolicregression, hasprovidedamethodofdetermin-
ingnonlineardynamicalsystemsfrommeasurementdata[31,252]. Itisalsopossible
touse an elasticnet for fast symbolic regression [193]toidentifynonlinear dynam-
ics [227]. Alternatively, compressed sensing may be used to reconstruct dynamical
systemsfromdatatopredictcatastrophes[295]. Thesparseidentificationofnonlin-
eardynamics(SINDy)algorithm[47]usessparseregression[280]inanonlinearfunc-
tionspacetodeterminetherelevanttermsinthedynamics. Thismethodhasrecently
been connected to DMD and the Koopman operator [45]. Thismay be thought of
as a generalization of earlier methods that employ symbolic regression (i.e., genetic
programming)toidentifydynamics. Thisfollowsagrowingtrendtoexploitsparsity
indynamics[211,245,186]anddynamicalsystems[15,221,49]. Othermethodsan-
alyzecausalityindynamicalsystemsusingtime-delayembedding[307,269],whichis
related to the delay coordinates introduced in Chapter 7. Theconnection of DMD
tothese system identification methodsisan exciting future direction ofresearch for
complexnonlinearsystems.

Chapter 2
Fluid Dynamics
DMDoriginatedinthefluiddynamicscommunityasapromisingnewtechniqueto
extractspatiotemporalcoherentpatternsfromhigh-dimensionalfluidsdata[247].The
subsequent connection betweenDMD modesandeigenvectors oftheKoopman op-
eratormadethemethodevenmorepromisingasanapproachtoanalyzedatafroma
nonlineardynamicalsystem,suchastheNavier–Stokesequations[235]. Intheshort
timefollowingthesetwoseminalpapers,DMDhasbeenusedextensivelyinfluiddy-
namicstoinvestigateawiderangeofflowphenomena.
Here,wewillexploremanyoftheadvancedapplicationsofDMDinfluiddynam-
ics. Inaddition,wedemonstratetheuseofDMDonalargedatasetthatistypicalin
fluiddynamics: atimeseriesofvorticityfieldsnapshotsforthewakebehindacircu-
larcylinderatReynoldsnumber100. DMDwillbecomparedwithPOD,whichisa
workhorsedatamethodinfluids[27,133].
2.1 Modal decomposition in fluids
Thereisarichhistoryinfluiddynamicsofinnovationsthatextractrelevantfeatures
from large-scale datasets. Although a fluid represents an immensely complex, high-
dimensionaldynamicalsystem,ithaslongbeenobservedthatdominantpatternsexist
intheflowfield,givingrisetolarge-scalecoherentstructures. Thesecoherentstruc-
tureswerefamouslydepicted byLeonardodaVinciinthedrawingshowninFigure
2.1. Efficiently characterizing these energetic structures from data, with either full
orlimitedmeasurements,hasbeenacentraleffortinmakingfluidsmoretractableto
analysis,engineeringdesign,andmorerecentlycontrol[133].
TheNavier–Stokesequationsrepresentahighlyaccuratepartialdifferentialequa-
tionmodelforagivenfluidsystem,yetitistypicallydifficulttousetheseequations
directlyfor engineering design. The need for an alternativedescription of fluid sys-
temsthatrepresentsflowinteractionsintheaggregateisnicelysummarizedbyRichard
Feynmaninhislectureonfluidmechanics[93]:
Thetestofscienceisitsabilitytopredict. Hadyounevervisitedtheearth,
couldyoupredictthethunderstorms,thevolcanos,theoceanwaves,theauro-
ras,andthecolorfulsunset?
Coherentstructureanalysishasbecomecentralinfluiddynamics. Insteadofcon-
sideringeverysubtledetailinaflowandanalyzingequationsofmotioninisolation,
25

26 Chapter2. FluidDynamics
Figure2.1.Illustrationsofturbulentmixing,byLeonardodaVincic.1508,in“Studies
ofWater Passing Obstaclesand Falling.” Large-scalecoherentstructurescanbeobservedinthese
sketches.
dataiscollectedfromrelevantflowconfigurationsandsynthesizedintorepresentative
structures and a hierarchy of models to describe their interactions. POD [27, 133]
is one of the earliest data-driven modal decompositions in fluids. It is a form of di-
mensionalityreduction,oftencomputedusingSVD[114,116,261],thatidentifiesthe

2.1. Modaldecompositioninfluids 27
linearsubspace thatbestspansthedata. Themethod benefitsfromthefactthatim-
portantdirectionsinthissubspacecorrespond tohigh-dimensionalvectorsthatmay
be thought of as “eigen” flows. POD has been widely accepted because of its ease
of interpretation and broad applicability to data from both simulations and experi-
ments. ROMshavebeenespeciallyimportantinobtainingcomputationallyefficient
representationssuitableforclosed-loopfeedbackcontrolofhigh-dimensionalfluidsys-
tems[46]. Inmanyways,thesefundamentaltechniquesindimensionalityreduction
forfluidsareamongthefirstuseofdatascienceincomplexsystems.
2.1.1 Experimental and numerical flow measurements
Inthepasthalfcentury,theabilitytocollectandanalyzelarge-scalemeasurementsof
fluidsystemshasrapidlyadvanced. Theseadvancesmayroughlybecategorizedinto
computationaltechniquestosimulatefluidsandexperimentaltechniquestomeasure
flowsinthelaboratory.
Withtheadventofscientificcomputing,computationalfluiddynamics(CFD)[125]
hastransformedtheanalysisoffluidsystems,providingtheunprecedentedabilityto
noninvasivelyprobeandmeasurefullyresolvedfluidvelocityfields. Thereisawide
varietyofnumericalmethodsforflowsimulation,includinggeneralmultiphysicsen-
ginesaswellasmethodsthatarehighlytailoredforaspecificscenario. Directnumer-
icalsimulations(DNSs)numericallysolvetheNavier–Stokesequations,resolvingall
spatialandtemporal scales. ThelargestDNSsarerunonmassivelyparallel comput-
ingarchitectures,andtheyresolveimmenselycomplexflows. Forexample,aparticu-
larlylargesimulationofawall-boundedturbulentchannelflowinvolvesover1011flow
statesandrunsonnearly106processorsinparallel[174]. Inadditiontoprovidingfull
spatialflowmeasurements,CFDenablesnonphysicalnumericalexperiments,suchas
investigatingthelinearized Navier–Stokes equationsor simulatingadjoint equations
forsensitivityanalysis,uncertaintyquantification,optimization,andcontrol. These
examplesinvolveeithersimulatingequationsthatarenonphysicalorinitializingarbi-
traryflowstates,bothofwhicharenotpossibleinexperiments.
Inexperimentalfluiddynamics,thegrowthoflasertechnologyhasenabledincreas-
inglydetailedmeasurements,includingthetrackingofscalarquantities(heat,density,
chemicals)aswellasfullvelocityfields. AroundthesametimeastheriseofCFD,laser
Dopplervelocimetry(LDV)[308,96]wasinvented,resultinginnoninvasivepointve-
locitymeasurements. Later, theparticle imagevelocimetry (PIV)[4]technique was
introduced,resultinginfulltwo-dimensionalorthree-dimensionalvelocityfieldmea-
surements. PIV has quickly become a standard experimental technique, providing
largequantitiesofflowdatafromreal-worldengineeringfluids.
Bothcomputationalandexperimentalmethodshaverelativestrengthsandweak-
nesses. CFDprovidesextremelyhighresolutionflowdata,butinvestigationofmany
engineering-scale flows is still decades away, even with the expected exponential in-
crease in computing power over time. Moreover, CFD is often applied to idealized
geometriesandflowconditions,makingitusefulasaresearch andprototypingtool,
but limited in theinvestigation of manyphysical systems. Atthesame time, exper-
imental techniques, such as PIV,may be applied toextremely complex and realistic
flows,butthesemethodsarelimitedbydatatransferratesaswellaslaserandcamera
technology. Thus,thespatialandtemporalresolutionofPIVsystemsremainslimited.
Asmorecompletemeasurementsbecomeavailableformorecomplicatedfluidsys-
tems,thedataassociatedwiththeseinvestigationswillbecomeincreasinglylargeand
unwieldy. Data-drivenmethodsarecentraltomanagingandanalyzingthisdata,and,

| 28  |     |     |     |     |     |     | Chapter2. |     | FluidDynamics |     |
| --- | --- | --- | --- | --- | --- | --- | --------- | --- | ------------- | --- |
generally,weconsiderdatamethodstoincludetechniquesthatapplyequallywellto
datafromnumericalorexperimentalsystems. Thisprecludesanynonphysicalknowl-
edgeofthesystem,includingadjoints,arbitraryinitialconditions,iterationsthrough
anevolutionoperator,etc.
| 2.1.2 | Snapshot-based |     | methods |     |     |     |     |     |     |     |
| ----- | -------------- | --- | ------- | --- | --- | --- | --- | --- | --- | --- |
Whenanalyzing atimeseriesofdatacontainingeithervelocityorvorticity fieldsat
agridofspatiallocations,itisoftenbeneficialtousesnapshot-basedmethods. First,
two-dimensional or three-dimensional vector field data at time t is flattened into a
k
singletallcolumnvector:
|     |     |     |          | ⎡     |      |       |         |     | ⎤      |       |
| --- | --- | --- | -------- | ----- | ---- | ----- | ------- | --- | ------ | ----- |
|     |     |     |          | x(r   | )    | x(r   | ) ···   | x(r | )      |       |
|     |     |     |          |       | ,t   | ,t    |         |     | ,t     |       |
|     |     |     |          | 1,1   | k    | 1,2 k |         | 1,p | k      |       |
|     |     |     |          | ⎢ x(r | )    | x(r   | ) · · · | x(r | )⎥     |       |
|     |     |     |          | ⎢     | ,t k | ,t k  |         | p   | ,t k ⎥ |       |
|     |     |     | x(r,t )= | ⎢ 2,  | 1    | 2, 2  |         | 2,  | ⎥      |       |
|     |     |     | k        | ⎣     | .    | .     | .       | .   | ⎦      | (2.1) |
|     |     |     |          |       | . .  | . .   | . .     | . . |        |       |
|     |     |     |          | x(r   | )    | x(r   | ) ···   | x(r | )      |       |
|     |     |     |          |       | ,t   | ,t    |         |     | ,t     |       |
|     |     |     |          | ⎡ q,1 | k ⎤  | q,2 k |         | q,p | k      |       |
|     |     |     |          | x(r   | ,t ) |       |         |     |        |       |
1,1 k
|     |     |     |     | ⎢ ⎢x(r | )⎥  |     |     |     |     |     |
| --- | --- | --- | --- | ------ | --- | --- | --- | --- | --- | --- |
,t ⎥
|     |     |     |     | ⎢ 1,2 | k ⎥  |     |     |     |     |       |
| --- | --- | --- | --- | ----- | ---- | --- | --- | --- | --- | ----- |
|     |     |     |     | ⎢     | . ⎥  |     |     |     |     |       |
|     |     |     |     | ⎢     | . ⎥  |     |     |     |     |       |
|     |     | =⇒  |     | =⎢    | . ⎥  |     |     |     |     |       |
|     |     |     | x   | ⎢x(r  | )    | .   |     |     |     | (2.2) |
|     |     |     | k   |       | ,t ⎥ |     |     |     |     |       |
|     |     |     |     | ⎢ 2,1 | k ⎥  |     |     |     |     |       |
|     |     |     |     | ⎢     | . ⎥  |     |     |     |     |       |
|     |     |     |     | ⎣     | . ⎦  |     |     |     |     |       |
.
|     |     |     |     | x(r | ,t ) |     |     |     |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- | --- | --- |
q,p k
Forthistwo-dimensionalvectorfieldexample,xdenotestheflowvariableofinterest,
rdenotesthespatialcoordinate,andtheindexkdenotesthekthtimestep. Thevector
x ∈ (cid:2)n is called a snapshot of data. This removes the spatial relationship between
k
neighbors,butitalsoallowssnapshotsatdifferenttimestobecomparedusingvector
inner products. Thesize n of a snapshot depends on the original size of the vector
fieldaswellasthenumberofflowvariablesofinterest,easilyconsistingofhundreds
ofthousands,ifnotmillionsorbillions,ofstates. Thesesnapshotsmaybesynthesized
intoadatamatrixX:
|     |     |     |     | ⎡   |     |     | ⎤   |     |     |       |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ----- |
|     |     |     |     | X=⎣ |     |     | ⎦   |     |     |       |
|     |     |     |     |     | x x | ··· | x . |     |     | (2.3) |
|     |     |     |     |     | 1   | 2   | m   |     |     |       |
This data matrix is a common starting place for snapshot-based methods. In fluid
systems,thestatedimensionnistypicallymuchlargerthanthenumberofsnapshots
m, so that X is a tall and skinny matrix. The case where spatial measurements are
collectedascolumnvectorsdiffersfromthestatisticsliterature,whereacollectionof
measurementsintimearetypicallyarrangedasrowvectorsinashortandfatmatrix.
2.1.3 POD
POD[27,133]isacentralmethodfordimensionalityreductioninfluids,resultingina
hierarchicaldecompositionofflowdataintoanorthogonalbasisofspatiallycorrelated
|     |            |          |            |     | takingtheSVD[114, |     |     |          | 119]of |         |
| --- | ---------- | -------- | ---------- | --- | ----------------- | --- | --- | -------- | ------ | ------- |
|     | modes. POD | is often | formulated |     | by                |     |     | 54, 116, |        | thedata |
matrixX:
∗
|     |     |     |     |     | X=UΣV | .   |     |     |     | (2.4) |
| --- | --- | --- | --- | --- | ----- | --- | --- | --- | --- | ----- |

2.1. Modaldecompositioninfluids 29
Notethatsincethestatedimensionnismuchlargerthanthenumberofsnapshotsm,
therankofXisatmostm,sothatthereisatmostanm×mnonzeroblockofsingular
valuesΣ.
SVDisapowerfulandnumericallystablemethodofdecomposingadatamatrix.
Inpractice,itiscommontousethemethodofsnapshots[261]tocomputetheleading
termsintheSVDforhigh-dimensionaldataassociatedwithfluidvelocityorvorticity
fields.Inparticular,itispossibletoconstructanm×mcolumnwisecorrelationmatrix
∗
X XconsistingofinnerproductsofthecolumnsofX.Theeigendecompositionofthis
matrixisrelatedtotheSVD:
X ∗ X=VΣU ∗ UΣV ∗=VΣ2V ∗ (2.5)
=⇒ X ∗ XV=VΣ2. (2.6)
Aftercomputing Vand Σfrom thespectral decomposition ofX ∗ X, itispossible to
constructtheleadingmcolumnsofU(i.e.,PODmodes)by
U=XVΣ−1.
(2.7)
Inmanycases,itiscustomarytosubtractthemeanofX(i.e.,themeanvelocityorvor-
ticityfield)beforecomputingPODmodes,inwhichcasePODisequivalenttoPCA
fromstatistics[214,147]. Itisinterestingtonotethat themethod ofsnapshotswas
publishedbySirovichinthesameyearasthebreakthroughoneigenfacesbySirovich
andKirby[262]. Thispaperprovidedamethodtoextractdominantpatternsinhu-
man facesfrom data; facial recognition has sincebecome acentral machine-learning
task.
PODseparatesthespaceandtimecorrelationsintothematricesUandV,respec-
tively. The matrix U only contains the spatial correlations in the data, whereas all
temporalinformationisfoundinV. Manymethods,suchasGalerkinprojection,dis-
regardtheremaininginformationfromΣandV.Infact,ifonlyUisdesired,PODmay
be computed on non-time-resolved data X, where the V matrix is essentially mean-
ingless. For time-resolved data, DMD capitalizes on the time correlations in V to
rearrange the leading column of U, resulting in the dominant patterns in the POD
subspacethatremaincoherentinbothspaceandtime.
2.1.4 Galerkin projection of Navier–Stokes equations
GivenanorthogonalbasisfromPOD,itispossibletoobtainaROMofadynamical
systemthrough Galerkinprojection. Inthisapproach, thestatevectorxisapproxi-
matedbyafinitesumofPODmodes,andthisexpansionissubstituteddirectlyintothe
dynamicalsystem. BytheorthogonalityofthePODcoordinatesystem,itispossible
toobtain an induced dynamical system on the POD mode coefficients. The result-
ingdynamical system typicallyhas amuch smallerdimension r compared with the
dimensionnofthestate-space.
Asanexample,considertheincompressibleNavier–Stokesequations,whereq(ξ,t)
representsacontinuousvectorfieldofvelocitycomponentsofthefluidinspaceand
time:
∂q 1
+(q·∇)q=−∇p+ ∇2q, (2.8a)
∂t Re
∇·q=0. (2.8b)

| 30  |     |     |     |     |     |     |     | Chapter2. | FluidDynamics |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --------- | ------------- | --- |
Inthisnondimensionalizedformulation,theonlyparameteristheReynoldsnumber
| Re=LU/ν,whereLisalengthscale,U |     |     |     |     |     | isavelocityscale,andν |     |     |     |     |
| ------------------------------ | --- | --- | --- | --- | --- | --------------------- | --- | --- | --- | --- |
isthekinematicfluid
viscosity.
Writtenincoordinates,theNavier–Stokesequationsbecome
|     |     |     | ∂q  | (cid:7) | ∂   | ∂   |       | (cid:7) ∂2 |     |        |
| --- | --- | --- | --- | ------- | --- | --- | ----- | ---------- | --- | ------ |
|     |     |     | j + |         | =−  |     | p + 1 |            |     |        |
|     |     |     |     | q       | q   |     |       |            | q , | (2.9a) |
|     |     |     | ∂t  | i∂ξ     | j   | ∂ξ  | Re    | ∂ξ2        | j   |        |
|     |     |     |     |         | i   |     | j     |            |     |        |
|     |     |     |     | i       |     |     |       | i          | i   |        |
(cid:7)∂q
j =0.
(2.9b)
∂ξ
|     |     |     | j   | j   |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
Itispossible towritethisasadynamical system in termsofahigh-dimensional dis-
cretizationxofthecontinuousvariableq:
x˙=Lx+Q(x,x),
(2.10)
whereLisalinearoperatorandQisabilinearoperator. Thequadraticnonlinearity
correspondstotheconvectionterm(q·∇)qin(2.8a).
Thestatexnearanequilibriumx¯maybeapproximatedbyexpandingthevelocity
fieldasasumofx¯andthePODmodes{ψ }r (ψarethecolumnsofUfrom(2.4)):
i=1
i
(cid:7)r
|     |     |     |     |     | x≈x¯+ |     | ψ   |     |     |        |
| --- | --- | --- | --- | --- | ----- | --- | --- | --- | --- | ------ |
|     |     |     |     |     |       | a   | .   |     |     | (2.11) |
|     |     |     |     |     |       |     | i i |     |     |        |
i=1
Typically, r ischosentobelargeenoughthattheapproximationisaccurate,yetsmall
enoughthat r (cid:20)n.
SubstitutingthePODexpansion(2.11)into(2.10)yields
|     |      |                 |                  | (cid:4)            |         |                   | (cid:5) |            |       |        |
| --- | ---- | --------------- | ---------------- | ------------------ | ------- | ----------------- | ------- | ---------- | ----- | ------ |
|     | a˙ ψ | =L(x¯+a         | ψ                | )+Q x¯+a           | ψ       | ,x¯+a             | ψ       |            |       | (2.12) |
|     | k    | k               | i i              |                    | i       | i                 | j j     |            |       |        |
|     |      | =Lx¯+a          | Lψ               | +Q(x¯,x¯)+a        |         | Q(x¯,ψ            | )+a Q(ψ | ,x¯)+a     | a Q(ψ | ,ψ )   |
|     |      |                 | i i              |                    |         | j                 | j i     | i          | i j   | i j    |
|     |      | =Lx¯+Q(x¯,x¯)+a |                  | [Lψ                | +Q(x¯,ψ |                   | )+Q(ψ   | ,x¯)]+a    | a Q(ψ | ,ψ ),  |
|     |      | (cid:17)        | (cid:18)(cid:19) | (cid:20) i(cid:17) | i       | (cid:18)(cid:19)i |         | i (cid:20) | i j   | i j    |
|     |      |                 | =0               |                    |         | =L˜ψ              |         |            |       |        |
i
| wheresummationovertheindicesi |     |     |     |     | and | j isassumed. |     |     |     |     |
| ----------------------------- | --- | --- | --- | --- | --- | ------------ | --- | --- | --- | --- |
Finally,becausethemodesψ
areorthonormal,wetaketheinnerproductofboth
i
sideswithψ :
k
|     |     |     |     | =a 〈L˜ψ | ,ψ 〉+a |       | 〈Q(ψ ,ψ | ),ψ | 〉   |         |
| --- | --- | --- | --- | ------- | ------ | ----- | ------- | --- | --- | ------- |
|     |     |     | a˙  |         |        | a     |         |     |     | (2.13a) |
|     |     |     | k   | i       | i k    | i j   | i       | j k |     |         |
|     |     |     |     | =Lˆ     | +Qˆ    |       |         |     |     |         |
|     |     |     |     | a       |        | a a , |         |     |     | (2.13b) |
|     |     |     |     | ik      | i ijk  | i j   |         |     |     |         |
whereLˆ andQˆ arenewlinearandbilinearoperators onmodecoefficients. The
|     | ij  |     | ijk |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
pressure term in (2.8a) disappears in this POD-Galerkin procedure because each of
thePOD modessatisfiesincompressibility, andsotheinnerproduct ofthepressure
gradientwithψ
vanishes.
k
GalerkinprojectionontoPODmodesgeneratesaROMforanonlineardynamical
system. Thesesystemsmaybemodifiedtoincludebothanequilibriumandamean
[207].
flow in a mean-field approximation Despite thebenefits, there are challenges
associatedwiththeclassicalPOD-Galerkinmethod:

2.2. ApplicationsofDMDinfluids 31
• TheoperatorsLˆandQˆ aredense,sothatevenforarelativelysmalldimensionr,
theseGalerkinsystemsmaybecomputationallyexpensivetosimulate. Incon-
trast, although afluidstatemaybehigh dimensional, theassociated equations
aregenerallysparse,enablingfastnumericalschemessuchasspectralmethods.
• POD-Galerkin systems are often unstable, and analyzing these nonlinear sys-
temsisdifficult[231].
• Computingthesystemin(2.10)andtheexpansionin(2.12)requiressignificant
computationalmachinery. Theseoperatorsandinnerproductsareusuallycom-
putedusingaworkingDNScode.
2.2 Applications of DMD in fluids
SincetheintroductionoftheDMDalgorithm[247]inthefluiddynamicscommunity
and its subsequent connection to nonlinear dynamical systems [235], DMD has be-
comeawidelyusedtechniqueinfluiddynamics[248]. Twoexcellent reviewsofthe
Koopmanspectraltheoryarefoundin[52,195].TheoriginalpresentationofDMDas
ageneralizationofglobalstabilityanalysishasframedmanyofthesubsequentstudies
influiddynamics.
2.2.1 DMD to extract structure from fluids data
DMDhasbeenappliedtoawidevarietyofflowgeometries(jets,cavityflow,wakes,
channel flow, boundary layers, etc.) to study mixing, acoustics, and combustion,
amongotherphenomena. Intheoriginal paperofSchmid[247], bothacavityflow
andajetwereconsidered. IntheoriginalpaperofRowleyetal.[235],ajetincross-
flowwasinvestigated.ItisnosurprisethatDMDhassubsequentlybeenusedwidelyin
bothcavityflowsandjets. ThefollowingsummaryofapplicationsofDMDinfluids
isnotexhaustive,asnewexamplesareconstantlybeingdeveloped.
In a number of jet studies, POD and DMD were compared [23, 254]. In [249],
Schlieren imagesofahelium jet wereused withDMD;interestingly, thisisan early
demonstrationthatDMDcouldbeusedwithphotographicimagesinadditiontoquan-
titativevectorfields. In[251],time-resolvedtomographicPIVwasusedtoinvestigate
ajet,andavariantofDMDwasintroducedusingaspatialvariableinplaceofthetime
variabletoanalyzecoherencewithagivenspatialwavenumber.
DMD has been used to study various aspects of cavity flows [247, 183, 19]. In
particular, DMD has been used to study self-sustained oscillations arising from the
unsteadyboundarylayerseparationattheleadingedge[253]. Time-resolvedPIVmea-
surementsofanincompressiblecavity[20]havealsobeenusedtocomputeDMD.
WakeflowshavealsobeeninvestigatedusingDMD.Anearlyexampleinvolveda
finite-thicknessflatplatewithellipticleadingedgeandactiveblowing/suctiontoin-
vestigateflowseparation. Inparticular,DMDwasusedtoidentifyamodeassociated
withthefrequencylock-onofahigh-frequencyseparatedshearlayerinstabilityassoci-
atedwiththeseparationbubbleandthelow-frequencywakemodes[288]. Thewake
pastagurneyflaphasalsobeeninvestigated[212]. In[13],thecylinderwakewasan-
alyzedusingKoopmananalysis,strengtheningtheconnectiontodynamicalsystems.
Recently, flow past wind turbines has been investigated using DMD, including dy-
namicstall[87]andwakeprediction[141].
DMDhasalsobeenappliedtoboundarylayerflows,providinginsightintorough
walls[173],compressibleturbulentboundarylayerinteractionwithaflutteringpanel

32 Chapter2. FluidDynamics
[210],andnear-wallstructuresinatransitionalboundarylayer[244]. Turbulentchan-
nelflowshavealsobeeninvestigated[199].
In acoustics, DMD has been used to capture the near-field and far-field acoustics
thatresultfrominstabilitiesobservedinshearflows[264]. DMDhasalsobeenusedto
analyzenonnormalgrowthmechanismsinthermoacousticinteractionsinaRijketube
[190]. Incombustion,DMDhasbeenusedtounderstandthecoherentheatreleasein
turbulentswirlflames[200]andtoanalyzearocketcombustor[138]. DMDhasbeen
comparedwithPODforreactingflows[239].
DMDhasalsobeenusedtoanalyzemoreexoticflows,includingasimulatedmodel
ofahigh-speedtrain[202]. Shockturbulentboundarylayerinteraction(STBLI)has
alsobeen investigated, and DMDwasused toidentifyapulsatingseparation bubble
thatisaccompanied byshockwave motion[120]. DMDhasalsobeenused tostudy
self-excitedfluctuationsindetonationwaves[191]. Otherproblemsincludeidentify-
inghairpinvortices[275],decomposingtheflowpastasurface-mountedcube[203],
modeling shallow-water equations [30], studying nanofluids past a square cylinder
[243],andmeasuringthegrowthrateofinstabilitiesinannularliquidsheets[85].
2.2.2 Model reduction and system identification
AmajorpromiseofDMDinfluidsistheabilitytosynthesizedatafromsimulations
orexperimentsintoaccurateandcomputationallytractableROMs. Therehavebeen
manyimportantadvancesinthisdirection[282],althoughmanyavenuesarestillbeing
developed. Inoneexample,theDMDalgorithmwasusedtoidentifyslowmodesto
morerapidlycomputebalancedPODmodels[287].DMDwaslaterrelatedconcretely
tobalancedmodelreductionviatheERA[182,290]. Thepubliclyavailablesoftware
package MODRED integrates numerous techniques for model reduction, including
DMD [24]. Other advances include the use of DMD and POD to create a hybrid
ROMforfuture-stateprediction[300]andaDMDerroranalysis[86].
2.2.3 Control-oriented methods
Manydata-driven methodsformodel reduction andsystem identificationarespecif-
ically tailored for control. The balanced POD (BPOD) [299, 233] combines bal-
anced truncation [201] with POD to yield balanced input-output dynamics and a
bi-orthogonal set of modes based on high-dimensional data. This method relies on
adjointsimulationsandisthereforeonlyapplicabletonumericalinvestigation. How-
ever,theERA[151]wasrecentlyshowntoyieldequivalentbalanced modelspurely
fromdata,withouttheneedforadjointsimulations[184]. ERAhasdeepconnections
withDMDthatwillbediscussedinChapter7.
2.2.4 Innovations of DMD in fluid dynamics
Numerous innovations to the DMD method have been developed in the context of
fluiddynamics. Theintegrationofcompressedsensingandfluidshaslargelycentered
aroundapplicationsinDMD[149,289,48,122]; thisdevelopment willbediscussed
further in Chapter 9. The optimal mode decomposition [306] is an iterative proce-
durethatsimultaneouslydeterminesthelow-rankdynamicsandtheoptimalsubspace
tominimizesystemresidualerror. Modeselectionwasalsoexploredin[64]. Asmen-
tionedearlier,DMDapplicationsinthejethaveresultedininnovationssurrounding
theuseofimagesforDMD[249]andthesubstitutionofaspatialvariableintherole
ofthetimevariableinDMD[251].

| 2.3. Example: | Re=100flowaroundacylinderwake |     |     |     |     | 33  |
| ------------- | ----------------------------- | --- | --- | --- | --- | --- |
| (a)           | (cid:3)                       |     |     | (b) |     |     |
|               |                               | s   |     | 2   |     | s   |
|               |                               | 1   |     |     |     | 1   |
|               | (cid:2)                       |     |     | 1   |     |     |
ω
| y   | (cid:1) |     |     | 0   |     |     |
| --- | ------- | --- | --- | --- | --- | --- |
(cid:239)(cid:2)
|     |     |     | s 2 |     |     | s 2 |
| --- | --- | --- | --- | --- | --- | --- |
(cid:239)(cid:3)
(cid:239)(cid:2) (cid:1) (cid:2) (cid:3) (cid:4) (cid:5) (cid:6) (cid:7) (cid:8) (cid:9) 0 5 10 15 20 25 30
|     |     | x   |     |     | Time[s] |     |
| --- | --- | --- | --- | --- | ------- | --- |
Figure 2.2. Example of vorticity field (a) and two sensors (b) for the wake behind a
cylinderatRe=100.Algorithm2.3plotsthevorticityfield.
| 2.2.5 Relationship |     | to the | Perron–Frobenius | operator | and |     |
| ------------------ | --- | ------ | ---------------- | -------- | --- | --- |
| almost-invariant   |     | sets   |                  |          |     |     |
[79,
TheKoopman operator is the dual tothe Perron–Frobenius operator 100, 102,
101],andtherearedeepmathematicalconnectionsbetweentheseoperators. Itisno
surprise that DMD computations are related to the calculation of almost-invariant
sets[102,103,274,303],usingset-orientedmethods[79,80]toidentifyeigenvectors
of thePerron–Frobenius operator. Almost-invariant sets have been useful tounder-
standsensitivityandcoherenceinfluidsystemsandalsohaverelevancetouncertainty
quantification.
| 2.3 Example: |     | Re = 100 | flow around | a cylinder | wake |     |
| ------------ | --- | -------- | ----------- | ---------- | ---- | --- |
Inthisexample,wedemonstrateDMDonadatasetrepresentingatimeseriesoffluid
vorticityfieldsforthewakebehindacircularcylinderatReynoldsnumberRe=100.
TheReynoldsnumberquantifiestheratioofinertialtoviscousforcesandisdefinedas
| Re=DU |     | /ν,whereD |                         | isthefree-streamvelocity,andν |     |     |
| ----- | --- | --------- | ----------------------- | ----------------------------- | --- | --- |
|       | ∞   |           | isthecylinderdiameter,U | ∞                             |     |     |
Re=100ischosenbecauseitislargerthanthecritical
isthekinematicfluidviscosity.
ReynoldsnumberRe ≈47atwhichpointtheflowundergoesasupercriticalHopf
crit
bifurcationresultinginlaminarvortexshedding[142,313].
Thislimitcycleisstable
andisrepresentativeofthethree-dimensionalflow[208,207].
The two-dimensional Navier–Stokes equations are simulated using an immersed
boundary projection method (IBPM) fluid solver2 based on the fast multidomain
methodofTairaandColonius[272,70]. Thecomputationaldomaincomprisesfour
gridsthatarenestedsothatthefinestgridcoversadomainof9×4andthelargestgrid
coversadomainof72×32,wherelengthsarenondimensionalizedbythecylinderdi-
gridcontains450×200points,
| ameter; | each               |     |                                         | sothatthereare50pointspercylinder |     |     |
| ------- | ------------------ | --- | --------------------------------------- | --------------------------------- | --- | --- |
|         | WeuseatimestepofΔt |     | =0.02,whichissmallenoughtosatisfytheCFL |                                   |     |     |
diameter.
condition[71].
| 2.3.1 Snapshots |     | of data |     |     |     |     |
| --------------- | --- | ------- | --- | --- | --- | --- |
Asnapshot of thecylinder wakedataisshown inFigure 2.2. Contours of vorticity
areshownontheleft,andatimehistoryofvorticityprobesensorss ands isshown
|     |     |     |     |     | 1 2 |     |
| --- | --- | --- | --- | --- | --- | --- |
on the right. Aftersimulations converge tosteady-state vortex shedding, wecollect
m=150snapshotsatregularintervalsintime,10Δt,samplingfiveperiodsofvortex
|     | 2The |             |                              |                      | https://github.com/ |     |
| --- | ---- | ----------- | ---------------------------- | -------------------- | ------------------- | --- |
|     | IBPM | codeused to | generatedata for thischapter | is publiclyavailable | at                  |     |
cwrowley/ibpm.

| 34  |            |                   |     |     |                         |        | Chapter2.               | FluidDynamics |        |
| --- | ---------- | ----------------- | --- | --- | ----------------------- | ------ | ----------------------- | ------------- | ------ |
|     | shedding.3 |                   |     |     |                         |        | 300Δt,withΔt            |               | =0.02, |
|     |            | Theperiodofvortex |     |     | sheddingisapproximately |        |                         |               |        |
|     |            |                   |     |     |                         | = fA/U | =0.16,whichisconsistent |               |        |
correspondingtoaStrouhalnumberofaboutSt
∞
withexperimentalresults. Algorithms2.1and2.2loadthedataforthissimulation.
Each vorticity field snapshot from the finest computational domain is reshaped
,andthesevectorscomprisecolumnsofthematricesXm−1
|     | intoalargevectorx |     |     |     |     |     |     |     | and |
| --- | ----------------- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |                   |     | k   |     |     |     |     |     | 1   |
Xm,asdescribedinChapter1.
Samplingawholenumberofperiodsisimportantto
2
recoversymmetricsolutions. Itisalsopossibletoaugmentthesnapshotmatrixwith
thenegativevorticityfields,therebyenforcingsymmetry.
ALGORITHM2.1.Load asinglevorticityfieldfromIBPMcode(loadIBPM.m).
|     | function | [X,Y,U,V,VORT]  |     |       | = loadIBPM(fname,nx,ny) |         |     |     |     |
| --- | -------- | --------------- | --- | ----- | ----------------------- | ------- | --- | --- | --- |
|     | fileID   | = fopen(fname); |     |       | % open                  | file    |     |     |     |
|     | % remove | first           | 6   | lines | of text                 | in file |     |     |     |
TEXT = textscan(fileID,’%s’,6,’delimiter’,char(460));
|     | % pull                          | out all                        | data |     |     |               |     |     |     |
| --- | ------------------------------- | ------------------------------ | ---- | --- | --- | ------------- | --- | --- | --- |
|     | FDATA =                         | fscanf(fileID,’%f’,[5,nx*ny]); |      |     |     |               |     |     |     |
|     | X = reshape(FDATA(1,:),nx,ny)’; |                                |      |     |     | % x positions |     |     |     |
|     | Y = reshape(FDATA(2,:),nx,ny)’; |                                |      |     |     | % y positions |     |     |     |
|     | U = reshape(FDATA(3,:),nx,ny)’; |                                |      |     |     | % u velocity  |     |     |     |
|     | V = reshape(FDATA(4,:),nx,ny)’; |                                |      |     |     | % v velocity  |     |     |     |
|     | VORT =                          | reshape(FDATA(5,:),nx,ny)’;    |      |     |     | % vorticity   |     |     |     |
fclose all
ALGORITHM2.2.Load allvorticityfieldsfromIBPMcode(loadDATA.m).
|     | nx = 199; | %                   | number | of  | grid      | points in y-direction |     |     |     |
| --- | --------- | ------------------- | ------ | --- | --------- | --------------------- | --- | --- | --- |
|     | ny = 449; | %                   | number | of  | grid      | points in x-direction |     |     |     |
|     | % create  | space               | for    | 150 | snapshots |                       |     |     |     |
|     | VORTALL   | = zeros(nx*ny,150); |        |     |           | % vorticity           |     |     |     |
|     | % extract | data                | from   | 150 | snapshots | files                 |     |     |     |
for count=1:150
|     | num              | = count*10; |                                      | % load                   | every                  | 10th file |     |     |     |
| --- | ---------------- | ----------- | ------------------------------------ | ------------------------ | ---------------------- | --------- | --- | --- | --- |
|     | % load           | file        |                                      |                          |                        |           |     |     |     |
|     | fname            | =           | [’ibpm’,num2str(num,’%05d’),’.plt’]; |                          |                        |           |     |     |     |
|     | [X,Y,U,V,VORT]   |             |                                      | = loadIBPM(fname,nx,ny); |                        |           |     |     |     |
|     | VORTALL(:,count) |             |                                      | =                        | reshape(VORT,nx*ny,1); |           |     |     |     |
end
ALGORITHM2.3.Plotvorticity fieldforcylinderwake(plotCylinder.m).
|     | function | f1  | = plotCylinder(VORT,ny,nx) |     |     |     |     |     |     |
| --- | -------- | --- | -------------------------- | --- | --- | --- | --- | --- | --- |
f1 = figure
|     | vortmin            | = -5; | %   | only plot  | what | is in -5 | to 5 range |     |     |
| --- | ------------------ | ----- | --- | ---------- | ---- | -------- | ---------- | --- | --- |
|     | vortmax            | = 5;  |     |            |      |          |            |     |     |
|     | VORT(VORT>vortmax) |       |     | = vortmax; |      | % cutoff | at vortmax |     |     |
3The
data collected for this example may be downloaded without running the IBPM code at
www.siam.org/books/ot149/flowdata.

| 2.3. | Example: Re=100flowaroundacylinderwake |     |      |           |     |        |            |     | 35  |
| ---- | -------------------------------------- | --- | ---- | --------- | --- | ------ | ---------- | --- | --- |
|      | VORT(VORT<vortmin)                     |     | =    | vortmin;  | %   | cutoff | at vortmin |     |     |
|      | imagesc(VORT);                         | %   | plot | vorticity |     | field  |            |     |     |
load CCcool.mat
|     | colormap(CC);      | %       | use | custom  | colormap |     |         |            |     |
| --- | ------------------ | ------- | --- | ------- | -------- | --- | ------- | ---------- | --- |
|     | % clean            | up axes |     |         |          |     |         |            |     |
|     | set(gca,’XTick’,[1 |         | 50  | 100 150 | 200      | 250 | 300 350 | 400 449],’ |     |
XTickLabel’,{’-1’,’0’,’1’,’2’,’3’,’4’,’5’,’6’,’7’,’8’})
set(gca,’YTick’,[1 50 100 150 199],’YTickLabel’,{’2’,’1’,’0’,’-1
’,’-2’});
|     | set(gcf,’Position’,[100 |     |     | 100 | 300 | 130]) |     |     |     |
| --- | ----------------------- | --- | --- | --- | --- | ----- | --- | --- | --- |
axis equal
hold on
|     | % add contour             | lines              | (positive |                                  | =                            | solid, | negative | = dotted) |     |
| --- | ------------------------- | ------------------ | --------- | -------------------------------- | ---------------------------- | ------ | -------- | --------- | --- |
|     | contour(VORT,[-5.5:.5:-.5 |                    |           | -.25                             | -.125],’:k’,’LineWidth’,1.2) |        |          |           |     |
|     | contour(VORT,[.125        |                    | .25       | .5:.5:5.5],’-k’,’LineWidth’,1.2) |                              |        |          |           |     |
|     | theta =                   | (1:100)/100’*2*pi; |           |                                  |                              |        |          |           |     |
x = 49+25*sin(theta);
y = 99+25*cos(theta);
|     | fill(x,y,[.3                        | .3  | .3]) | % place | cylinder |          |          |     |     |
| --- | ----------------------------------- | --- | ---- | ------- | -------- | -------- | -------- | --- | --- |
|     | plot(x,y,’k’,’LineWidth’,1.2)       |     |      |         | %        | cylinder | boundary |     |     |
|     | set(gcf,’PaperPositionMode’,’auto’) |     |      |         |          | %        |          |     |     |
print(’-depsc2’, ’-loose’, ’figures/cylinder’); % eps are vector
images
| 2.3.2 | POD modes | for the | cylinder |     | wake |     |     |     |     |
| ----- | --------- | ------- | -------- | --- | ---- | --- | --- | --- | --- |
Figure2.3showsthePODforthecylinderwakedatadescribedabove. Inthisexam-
ple,thePODmodescomeinenergeticpairs,asshowninpanel(b),whichdepictsthe
singularvalues. AlthoughtheSVDisaseparationofvariablesresultinginaspatiotem-
poraldecomposition,itisabletoapproximatetherelevantstructuresrequiredforthe
travelingwavesolutiontothecylinderwake. NotethatPODmaybeappliedtofluid
velocityfieldorvorticityfielddata;inthiscase,weareusingvorticityfields.
ALGORITHM2.4.ComputePODmodesforcylinderwake(computePOD.m).
X = VORTALL;
Y = [X X];
|     | %% augment | matrix | with | mirror | images | to  | enforce | symmetry/ |     |
| --- | ---------- | ------ | ---- | ------ | ------ | --- | ------- | --------- | --- |
antisymmetry
for k=1:size(X,2)
|     | xflip            | = reshape(flipud(reshape(X(:,k),nx,ny)),nx*ny,1); |     |           |     |     |     |     |     |
| --- | ---------------- | ------------------------------------------------- | --- | --------- | --- | --- | --- | --- | --- |
|     | Y(:,k+size(X,2)) |                                                   |     | = -xflip; |     |     |     |     |     |
end
|     | %% compute                        | mean         | and subtract; |     |     |        |         |      |     |
| --- | --------------------------------- | ------------ | ------------- | --- | --- | ------ | ------- | ---- | --- |
|     | VORTavg                           | = mean(Y,2); |               |     |     |        |         |      |     |
|     | f1 = plotCylinder(VORTavg,nx,ny); |              |               |     |     | % plot | average | wake |     |

| 36  |     |     |     |     |     | Chapter2. | FluidDynamics   |     |
| --- | --- | --- | --- | --- | --- | --------- | --------------- | --- |
|     |     | 2   |     | (b) |     |           | 1               |     |
|     | (a) |     |     | 103 |     |           |                 |     |
|     |     | 1   |     |     |     |           | ygrenElatoT 0.8 |     |
σ 102
|     | y   | 0   |     | k   |     |     | 0.6 |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     | 101 |     |     | 0.4 |     |
0.2
|     |     | 0 1 2 | 3 4 5 6 | 7 8 0 | 10  | 20  | 0 10 | 20  |
| --- | --- | ----- | ------- | ----- | --- | --- | ---- | --- |
|     |     |       |         |       | k   |     | k    |     |
x
|     | (c) | 2     |         | (d) | 2   |     |         |     |
| --- | --- | ----- | ------- | --- | --- | --- | ------- | --- |
|     |     | 1     |         |     | 1   |     |         |     |
|     | y   |       |         | y   |     |     |         |     |
|     |     | 0     |         |     | 0   |     |         |     |
|     |     | 0 1 2 | 3 4 5 6 | 7 8 | 0   | 1 2 | 3 4 5 6 | 7 8 |
|     |     |       | x       |     |     |     | x       |     |
|     |     | 2     |         |     | 2   |     |         |     |
|     | (e) |       |         | (f) |     |     |         |     |
|     |     | 1     |         |     | 1   |     |         |     |
|     | y   | 0     |         | y   | 0   |     |         |     |
|     |     | 0 1 2 | 3 4 5 6 | 7 8 | 0   | 1 2 | 3 4 5 6 | 7 8 |
|     |     |       | x       |     |     |     | x       |     |
|     | (g) | 2     |         | (h) | 2   |     |         |     |
|     |     | 1     |         |     | 1   |     |         |     |
|     | y   | 0     |         | y   | 0   |     |         |     |
|     |     | 0 1 2 | 3 4 5 6 | 7 8 | 0   | 1 2 | 3 4 5 6 | 7 8 |
|     |     |       | x       |     |     |     | x       |     |
|     |     | 2     |         |     | 2   |     |         |     |
|     | (i) |       |         | (j) |     |     |         |     |
|     |     | 1     |         |     | 1   |     |         |     |
|     | y   | 0     |         | y   | 0   |     |         |     |
|     |     | 0 1 2 | 3 4 5 6 | 7 8 | 0   | 1 2 | 3 4 5 6 | 7 8 |
|     |     |       | x       |     |     |     | x       |     |
Figure2.3. Meanvorticityfield(a)andPODsingularvalues(b)forthewakebehinda
cylinderatRe=100.Thefirst8PODmodesareshownin(c)–(j).
|       | %%                               | compute POD                                | after subtracting | mean | (i.e.,        | do  | PCA) |     |
| ----- | -------------------------------- | ------------------------------------------ | ----------------- | ---- | ------------- | --- | ---- | --- |
|       | [PSI,S,V]                        | = svd(Y-VORTavg*ones(1,size(Y,2)),’econ’); |                   |      |               |     |      |     |
|       | % PSI                            | are POD                                    | modes             |      |               |     |      |     |
|       | semilogy(diag(S)./sum(diag(S))); |                                            |                   | %    | plot singular |     | vals |     |
| 2.3.3 | DMD                              | of the cylinder                            | wake              |      |               |     |      |     |
Applying DMD to the cylinder wake requires the same basic snapshot information
asPOD,makingthisadata-drivenmethod,sinceitappliesequallywelltodatafrom
simulationsorexperiments. Figure2.4showsaschematicoftheDMDalgorithm. A
moredetailedanalysisoftheKoopmananalysisappliedtothecylinderwakemaybe

2.3. Example: Re=100flowaroundacylinderwake 37
foundin[13].
UnlikePOD,DMDprovidesnotonlymodesbutalsoasetofassociatedeigenval-
uesthatdeterminealow-dimensionaldynamicalsystemforhowthemodeamplitudes
evolveintime. Moreover, unlikePOD,themeanisnotsubtracted intheDMDcal-
culation,andthefirstmode(shownasmode1inthemiddlepanel),correspondstoa
backgroundmodethatisnotchanging(i.e.,ithaszeroeigenvalue). TheDMDmodes
looksimilartothePODmodesforthisexamplebecausethePODprovidesaharmonic
decomposition,sothatthemodalamplitudesareapproximatelysinusoidalintimeat
harmonicfrequenciesofthedominantvortexshedding.
ALGORITHM2.5.ComputeDMDmodesforcylinderwake(computeDMD.m).
X = VORTALL(:,1:end-1);
X2 = VORTALL(:,2:end);
[U,S,V] = svd(X,’econ’);
%% Compute DMD (Phi are eigenvectors)
r = 21; % truncate at 21 modes
U = U(:,1:r);
S = S(1:r,1:r);
V = V(:,1:r);
Atilde = U’*X2*V*inv(S);
[W,eigs] = eig(Atilde);
Phi = X2*V*inv(S)*W;
%% Plot DMD modes
for i=10:2:20
plotCylinder(reshape(real(Phi(:,i)),nx,ny),nx,ny);
plotCylinder(reshape(imag(Phi(:,i)),nx,ny),nx,ny);
end
%% Plot DMD spectrum
figure
theta = (0:1:100)*2*pi/100;
plot(cos(theta),sin(theta),’k--’) % plot unit circle
hold on, grid on
scatter(real(diag(eigs)),imag(diag(eigs)),’ok’)
axis([-1.1 1.1 -1.1 1.1]);

| 38  |     |     |     |     |     |     | Chapter2. |     | FluidDynamics |     |
| --- | --- | --- | --- | --- | --- | --- | --------- | --- | ------------- | --- |
m e
ti
|     | Snapshots |     | ⎡   |     | ⎤   | Time-shifted  |     | ⎡   |     | ⎤   |
| --- | --------- | --- | --- | --- | --- | ------------- | --- | --- | --- | --- |
Snapshots
|     |     | X=⎣x |     | x ··· | x ⎦ |     | X(cid:2) | =⎣x | x   | ··· x ⎦ |
| --- | --- | ---- | --- | ----- | --- | --- | -------- | --- | --- | ------- |
|     |     |      | 1   | 2     | m−1 |     |          |     | 2 3 | m       |
X(cid:2)≈AX
|     | Data |     |     |     |     | 1. Approximate map |     |     |     |     |
| --- | ---- | --- | --- | --- | --- | ------------------ | --- | --- | --- | --- |
X=UΣV∗
2. Take SVD of X
A˜ ≈U∗X(cid:2)VΣ−1
3. Reduced matrix
A˜W=WΛ
4. Eigendecomposition
|     | Dynamic Mode Decomposition |     |     |     |     | 5. Compute modes |     |     | Φ=X(cid:2)VΣ−1W |     |
| --- | -------------------------- | --- | --- | --- | --- | ---------------- | --- | --- | --------------- | --- |
|     |                            | 9   | 8   | 1   |     |                  |     |     |                 |     |
|     | C                          |     | 7 6 |     |     | 2                |     |     | 3               |     |
(cid:3)
5
4
|     | (cid:2)(cid:1)(cid:4) |     | 3   |     |     |     |     |     |     |     |
| --- | --------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |                       |     | 2   | 4   |     | 5   |     |     | 6   |     |
1
(cid:2)
(cid:239)(cid:2)(cid:1)(cid:4)
9
|     |     |     |     | 7   |     | 8   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
(cid:239)(cid:3)
|     | (cid:239)(cid:3) | (cid:2) | (cid:3) |     |     |     |       |                 |     |     |
| --- | ---------------- | ------- | ------- | --- | --- | --- | ----- | --------------- | --- | --- |
|     | Eigenvalues      |         | Λ       |     |     |     | Modes | Φ=X(cid:2)VΣ−1W |     |     |
Predictive Reconstruction
|     |     |     |     |     | ⎡   | modes | ⎤⎡amplitudes⎤⎡ |         | dynamics  | ⎤             |
| --- | --- | --- | --- | --- | --- | ----- | -------------- | ------- | --------- | ------------- |
|     |     |     |     |     |     |       | b              | 0 · · · | 1 λ       | · · · λ m − 2 |
|     |     |     |     |     |     |       | · · · 1        |         | 1         | 1             |
|     |     |     |     |     | ⎣φ  |       | ⎦⎢ 0           | b · · · | ⎥ ⎢       | m − 2⎥        |
|     |     |     |     |     | X≈  | φ     | · · · ⎣        | 2       | ⎦ ⎣ 1 λ 2 | · · · λ ⎦     |
|     |     |     |     |     | 1   | 2     | .              | . .     | . .       | 2 .           |
|     |     |     |     |     |     |       | · · · .        | . ..    | . .       | . . .         |
|     |     |     |     |     |     |       | .              | .       | . .       | . .           |
Figure2.4.SchematicofdataprocessinginDMDalgorithmforthecylinderwakeexample.

Chapter 3
Koopman Analysis
MuchoftheinterestsurroundingDMDisduetoitsstrongconnectiontononlinear
dynamicalsystemsthroughKoopmanspectraltheory[196,194,235,195]. TheKoop-
manoperator,introducedin1931byB.O.Koopman[162],isaninfinite-dimensional
linearoperatorthatdescribeshowmeasurementsofadynamicalsystemevolvethrough
thenonlineardynamics. Becausethesemeasurementsarefunctions,theyformaHilbert
space,sotheKoopmanoperatorisinfinitedimensional.
In 2009, Rowley et al. [235] demonstrated that under certain conditions, DMD
provides a finite-dimensional approximation to eigenvalues and eigenvectors of the
infinite-dimensional Koopman operator. In this chapter, we begin by providing an
overviewofspectraltheoryandeigenfunctionexpansions,firstforfinite-dimensional
matricesandthenforinfinite-dimensional operators. Next, weintroducetheKoop-
manoperatorandprovideconnectionstoDMD.Finally,wedemonstratethetheory
ontwoexampledynamicalsystems.
3.1 Spectral theory and eigenfunction expansions
BeforediscussingtheKoopmanoperatoranditsconnectiontoDMD,itisimportant
toreviewthebasicideasassociatedwithspectraltheoryandeigenfunctionexpansion
solutions of differential equations [98, 266]. We can consider this concept for both
ordinarydifferentialequationsonvectorspaces(cid:2)n andpartialdifferentialequations
onfunctionspaces(cid:2). Recallthatinthevectorcase,weareingeneralconsideringthe
nonlineardifferentialequation
dx
=f(x,t;μ). (3.1)
dt
Thestatex∈(cid:2)n maybeobtainedbydiscretizingthestateuofapartialdifferential
equation(1.36)atafinitecollectionofdiscretespatiallocations. Inthiscase,thedy-
namics approximatethepartialdifferentialequation(1.36)atthesediscretelocations.
3.1.1 Vector spaces
Atraditionalsolutiontechniqueforsuchaproblemistouseaneigenfunctionexpan-
sion corresponding toa matrixA associated with eitherthelinearization of (3.1) or
39

| 40  |     |     |     |     |     |     | Chapter3. | KoopmanAnalysis |     |
| --- | --- | --- | --- | --- | --- | --- | --------- | --------------- | --- |
a natural coordinate system used to represent the dynamics (e.g., Fourier, Legendre
|     | polynomials). | Thus,onecanconsidertheeigenvalueproblem |     |     |        |     |     |     |       |
| --- | ------------- | --------------------------------------- | --- | --- | ------ | --- | --- | --- | ----- |
|     |               |                                         |     |     | AW=WΛ, |     |     |     | (3.2) |
andΛisadiagonal
|     | wherecolumns |     | ofWare | thecollection |     | ofeigenvectors(w |     | )   | ma- |
| --- | ------------ | --- | ------ | ------------- | --- | ---------------- | --- | --- | --- |
k
trixwhose entries are the associated eigenvalues (λ ). In addition to this eigenvalue
k
problem,itisalsonecessarytoconsidertheadjointeigenvalueproblem
|     |     |     |     |     | A ∗ W˜ | =W˜Λ˜, |     |     | (3.3) |
| --- | --- | --- | --- | --- | ------ | ------ | --- | --- | ----- |
∗
where A is the complex conjugate transpose of the matrix A. More formally, the
adjointisdefinedsuchthat
|     |     |     |     |     | (cid:21) (cid:22) | (cid:21) | (cid:22) |          |       |
| --- | --- | --- | --- | --- | ----------------- | -------- | -------- | -------- | ----- |
|     |     |     |     |     |                   | =        | ∗        |          |       |
|     |     |     |     |     | Ax ,x             | x ,A     | x ,      |          | (3.4) |
|     |     |     |     |     | j k               | j        | k        |          |       |
|     |     |     |     |     |                   |          | (cid:21) | (cid:22) |       |
where the inner product for vectors is defined by x ,x =x ∗ x . As before, the
|     |     |     |     |     |     |     |     | j k j |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ----- | --- |
k
|     | columnsofW˜ |     |     |     |     |     | ),andΛ˜isadiagonalmatrixwhose |     |     |
| --- | ----------- | --- | --- | --- | --- | --- | ----------------------------- | --- | --- |
arethecollectionofeigenvectors(w˜
k
entriesaretheassociatedeigenvalues(λ˜ ). IfthematrixAisself-adjoint,thenthetwo
k
= ∗
eigenvalue problems are equivalent, since A A . Note that the eigenvectors and
adjointeigenvectorssatisfytheorthonormalityconditions
|     |     |     |     | (cid:21) | (cid:22) | (cid:23) |     |     |     |
| --- | --- | --- | --- | -------- | -------- | -------- | --- | --- | --- |
=k,
|     |     |     |     |       | =δ  | =   | 1, j        |     |       |
| --- | --- | --- | --- | ----- | --- | --- | ----------- | --- | ----- |
|     |     |     |     | w ,w˜ |     |     | (cid:18)=k, |     | (3.5) |
|     |     |     |     | j     | k   | jk  | 0, j        |     |       |
δ
where is the Dirac delta function. This can be easily seen by taking the inner
jk
product of Aw = λ w withrespect tow˜ , using thedefinition ofthe adjoint, and
|     |             |             | j j | j   |     | k   |     |     |     |
| --- | ----------- | ----------- | --- | --- | --- | --- | --- | --- | --- |
|     | notingthatλ | (cid:18)=λ˜ | .   |     |     |     |     |     |     |
j k
Spectraltheoryinvolvesrepresentingthesolutiontothedifferentialequation(3.1)
bytheadjointeigenvectorsofthematrixA. Specifically, onecanposit asolutionof
theform
(cid:7)n
|     |     |     |     |     | x(t)= | a (t)w | ,   |     | (3.6) |
| --- | --- | --- | --- | --- | ----- | ------ | --- | --- | ----- |
|     |     |     |     |     |       | k      | k   |     |       |
k=1
|     |     |     |     | =   | (t) |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
where the coefficients a a determine the time evolution of each eigenvector
|     |     |     |     | k   | k   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
w . Thisisanexpression oftheseparationofvariables. Forlinearsystems,thetime
k
evolutionofeacheigenvectorisdirectlylinkedtoitseigenvalueλ
,thusgivingriseto
k
theterminology spectral theory. Such spectral expansions can alsobeused tosolvea
linearsystemofequationsfortheunknownvectorx:
Ax=b.
(3.7)
|     | Takingtheinnerproductofbothsidesof(3.7)withrespecttow˜ |     |     |     |     |     |     | gives |     |
| --- | ------------------------------------------------------ | --- | --- | --- | --- | --- | --- | ----- | --- |
j
|     |     | (cid:21) | (cid:22) | (cid:21) (cid:22) |     |     |     |     |     |
| --- | --- | -------- | -------- | ----------------- | --- | --- | --- | --- | --- |
=
|     |     | Ax,w˜    |            | b,w˜       | ,        |     |     |     |     |
| --- | --- | -------- | ---------- | ---------- | -------- | --- | --- | --- | --- |
|     |     | (cid:21) | j (cid:22) | (cid:21) j | (cid:22) |     |     |     |     |
∗ =
|     |     | x,A      | w˜        | b,w˜               |     |     | (definitionofadjoint), |     |     |
| --- | --- | -------- | --------- | ------------------ | --- | --- | ---------------------- | --- | --- |
|     |     | (cid:21) | j(cid:22) | (cid:21) j(cid:22) |     |     |                        |     |     |
x,λ˜ =
|     |     |           | w˜         | b,w˜       |          |     | (use(3.3)), |     |     |
| --- | --- | --------- | ---------- | ---------- | -------- | --- | ----------- | --- | --- |
|     |     | (cid:21)j | j (cid:22) | (cid:21) j | (cid:22) |     |             |     |     |
∗
|     |     | λ˜         |          | =         |          |          |                    |     |     |
| --- | --- | ---------- | -------- | --------- | -------- | -------- | ------------------ | --- | --- |
|     |     |            | x,w˜     | b,w˜      |          |          | (pulloutconstant), |     |     |
|     |     | j (cid:24) | j        | (cid:25)j |          |          |                    |     |     |
|     |     |            | (cid:7)n |           | (cid:21) | (cid:22) |                    |     |     |
∗
|     |     | λ˜  |     |       | =    |     |                    |     |     |
| --- | --- | --- | --- | ----- | ---- | --- | ------------------ | --- | --- |
|     |     |     | a   | w ,w˜ | b,w˜ |     | (expandwith(3.6)), |     |     |
|     |     | j   | k   | k j   | j    |     |                    |     |     |
k=1(cid:21)
(cid:22)
λ˜ ∗
|     |     | a   | = b,w˜ |     |     |     | (orthonormality). |     |     |
| --- | --- | --- | ------ | --- | --- | --- | ----------------- | --- | --- |
|     |     | j   | j      | j   |     |     |                   |     |     |

3.1. Spectraltheoryandeigenfunctionexpansions 41
Thefinalexpression allowsforanexplicitanduniquecomputationoftheweighting
| coefficients |     |     |     |     | (cid:21) (cid:22) |     |     |
| ------------ | --- | --- | --- | --- | ----------------- | --- | --- |
b,w˜
j
|     |     |     |     | a = |     | .   | (3.8) |
| --- | --- | --- | --- | --- | --- | --- | ----- |
|     |     |     |     | j   | ∗   |     |       |
λ˜
j
These n coefficients characterize the projection of the solution (3.6) onto the space
(cid:2)n spannedbytheeigenvectors. NotethatwhenAisself-adjoint(i.e.,A=A ∗ ),then
λ˜ ∗
=λ .
j j
Whentheexpansion(3.6)isappliedtothelineardynamicalsystem
|     |     |     |     | dx  | =Ax, |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- |
(3.9)
dt
thedynamicsarediagonalized. Specifically,takingtheinnerproductofthisequation
| withrespecttow˜ |     | gives |     |     |     |     |     |
| --------------- | --- | ----- | --- | --- | --- | --- | --- |
j
| (cid:26) | (cid:27) | (cid:21) | (cid:22) |     |     |     |     |
| -------- | -------- | -------- | -------- | --- | --- | --- | --- |
dx
=
|     | ,w˜ | Ax,w˜ | ,   |     |     |     |     |
| --- | --- | ----- | --- | --- | --- | --- | --- |
| dt  | j   | j     |     |     |     |     |     |
(cid:26) (cid:27)
|     |     | (cid:21) | (cid:22) |     |     |     |     |
| --- | --- | -------- | -------- | --- | --- | --- | --- |
dx
|     | ,w˜ | = x,A ∗ w˜ |     |     |     | (definitionofadjoint), |     |
| --- | --- | ---------- | --- | --- | --- | ---------------------- | --- |
|     | j   |            | j   |     |     |                        |     |
dt
| (cid:26) | (cid:27) | (cid:21) | (cid:22) |     |     |     |     |
| -------- | -------- | -------- | -------- | --- | --- | --- | --- |
dx
= x,λ˜
|     | ,w˜ | w˜  |     |     |     | (use(3.3)), |     |
| --- | --- | --- | --- | --- | --- | ----------- | --- |
| dt  | j   | j   | j   |     |     |             |     |
(cid:26) (cid:27)
|          |         | (cid:21) | (cid:22) |          |          |                    |     |
| -------- | ------- | -------- | -------- | -------- | -------- | ------------------ | --- |
| dx       |         | =λ˜∗     |          |          |          |                    |     |
|          | ,w˜     | x,w˜     |          |          |          | (pulloutconstant), |     |
|          | j       | j        | j        |          |          |                    |     |
| dt       | (cid:2) |          | (cid:24) |          | (cid:25) |                    |     |
| (cid:28) |         | (cid:29) |          |          |          |                    |     |
| d        | n a     | w        |          | (cid:7)n |          |                    |     |
|          | k=1     | k k      | =λ˜∗     |          |          |                    |     |
|          |         | ,w˜      |          | a        | w ,w˜    | (expandwith(3.6)), |     |
|          | dt      | j        | j        | k        | k j      |                    |     |
k=1
| (cid:24) |     | (cid:25) | (cid:24) |     | (cid:25) |     |     |
| -------- | --- | -------- | -------- | --- | -------- | --- | --- |
| (cid:7)n |     |          | (cid:7)n |     |          |     |     |
da
|     | kw  | ,w˜ =λ˜∗ |     | a w | ,w˜ | (derivativeofcoefficients), |     |
| --- | --- | -------- | --- | --- | --- | --------------------------- | --- |
|     |     | k j      |     | k   | k j |                             |     |
|     | dt  |          | j   |     |     |                             |     |
| k=1 |     |          | k=1 |     |     |                             |     |
da
j =λ˜∗
|     | a   |     |     |     |     | (orthonormality). |     |
| --- | --- | --- | --- | --- | --- | ----------------- | --- |
|     | j j |     |     |     |     |                   |     |
dt
Thelastequationshowsthatthedynamicsarediagonalizedinthespaceoftheadjoint
eigenvectors.
Nonlinear dynamics (3.1) can also be represented by such eigenfunction expan-
sions. Inthiscase,takingtheinnerproductof(3.1)withrespecttow˜ gives
j
|     |     |     | da  | (cid:21) |     | (cid:22) |     |
| --- | --- | --- | --- | -------- | --- | -------- | --- |
j
|     |     |     |     | =   | f(x,t;μ),w˜ | ,   | (3.10) |
| --- | --- | --- | --- | --- | ----------- | --- | ------ |
j
dt
where the right-hand side mixes eigenvectors through the inner product with the
nonlinearity,i.e.,thedynamicsarenolongerdiagonalizable. Thus,theevolutionof
| (t)dependsingeneralonalla |     |     |     | (t),wherek=1,2,...,n. |     |                        |     |
| ------------------------- | --- | --- | --- | --------------------- | --- | ---------------------- | --- |
| a                         |     |     |     |                       |     | Innumericalschemes,one |     |
| j                         |     |     | k   |                       |     |                        |     |
canoftenchoosealargeenoughsetofbasismodes(n(cid:13)1)toaccuratelycomputethe
dynamicsgeneratedbythenonlinearity.
3.1.2 Function spaces
To set the foundations of Koopman theory, we must also consider function spaces
andspectraltheoryforinfinite-dimensionalvectorspaces. Weneedonlyconsiderthe

| 42  |     |     |     |     |     | Chapter3. | KoopmanAnalysis |     |
| --- | --- | --- | --- | --- | --- | --------- | --------------- | --- |
linearpartialdifferentialequationforq(x,t)
dq
|     |     |     |     |     | =(cid:21)q, |     |     | (3.11) |
| --- | --- | --- | --- | --- | ----------- | --- | --- | ------ |
dt
where (cid:21) is a linear operator acting on an infinite-dimensional Hilbert space (cid:2) of
scalar functions on x. As with vector spaces, spectral theory revolves around two
eigenvalueproblems:
|     |     |     |     | (cid:21)q | =λ  | q ,  |     | (3.12a) |
| --- | --- | --- | --- | --------- | --- | ---- | --- | ------- |
|     |     |     |     |           | k   | k k  |     |         |
|     |     |     |     | (cid:21)∗ | =λ˜ |      |     |         |
|     |     |     |     |           | q˜  | q˜ , |     | (3.12b) |
|     |     |     |     |           | k   | k k  |     |         |
(λ˜
where(cid:21)∗ istheadjointlinearoperatorandq (q˜ )andλ )aretheeigenfunctions
|     |     |     |     |     | k   | k k k |     |     |
| --- | --- | --- | --- | --- | --- | ----- | --- | --- |
(adjointeigenfunctions)andeigenvalues(adjointeigenvalues),respectively.
Theeigenfunctionsolutioncanthenbeconstructedasfollows:
(cid:7)∞
|     |     |     | q(x,t)= |     | a   | (t)q (x), |     | (3.13) |
| --- | --- | --- | ------- | --- | --- | --------- | --- | ------ |
|     |     |     |         |     | k   | k         |     |        |
k=1
wherethea (t)determinetheweightingofeachmodeinthespectralrepresentation
k
ofq(x,t).
Theexpansioncanbeusedtosolvethecanonicalproblemequivalenttothe
vectorspaceproblemAx=b,
(cid:21)q=
|     |     |     |     |     | f,  |     |     | (3.14) |
| --- | --- | --- | --- | --- | --- | --- | --- | ------ |
foragivenright-handsidefunction f(x). Forexample,thisrepresentationreducesto
Laplace’sequationwhen(cid:21) =∇2and f =0andPoisson’sequationfornonzero f.
Wedefinetheinnerproductforfunctionsas
(cid:30)
∞
∗(x)dx.
|     |     |     | 〈f,g〉= |     | f(x)g |     |     | (3.15) |
| --- | --- | --- | ------ | --- | ----- | --- | --- | ------ |
−∞
Takingtheinnerproductoftheabovewithrespecttoq˜ yields
j
|     | (cid:21) | (cid:22) (cid:21) | (cid:22) |     |     |     |     |     |
| --- | -------- | ----------------- | -------- | --- | --- | --- | --- | --- |
(cid:21)q,q˜ =
|     |          |                     | f,q˜ ,     |     |     |     |     |     |
| --- | -------- | ------------------- | ---------- | --- | --- | --- | --- | --- |
|     | (cid:21) | j (cid:22) (cid:21) | j (cid:22) |     |     |     |     |     |
q,(cid:21)∗ =
|     |          | q˜                 | f,q˜      |     |     | (definitionofadjoint), |     |     |
| --- | -------- | ------------------ | --------- | --- | --- | ---------------------- | --- | --- |
|     | (cid:21) | (cid:22)j (cid:21) | (cid:22)j |     |     |                        |     |     |
q,λ˜ =
|     |          | q˜ f,q˜              |           |     |     | (use(3.12)), |     |     |
| --- | -------- | -------------------- | --------- | --- | --- | ------------ | --- | --- |
|     | (cid:21) | j j(cid:22) (cid:21) | j(cid:22) |     |     |              |     |     |
λ˜∗ =
|     |           | q,q˜ f,q˜ |     |          |          | (pulloutconstant), |     |     |
| --- | --------- | --------- | --- | -------- | -------- | ------------------ | --- | --- |
|     | j(cid:24) | j         | j   | (cid:25) |          |                    |     |     |
|     |           |           |     | (cid:21) | (cid:22) |                    |     |     |
(cid:7)∞
|     | λ˜∗ | (t)q | (x),q˜ | =    |     |                     |     |     |
| --- | --- | ---- | ------ | ---- | --- | ------------------- | --- | --- |
|     |     | a    |        | f,q˜ |     | (expandwith(3.13)), |     |     |
|     | j   | k    | k j    |      | j   |                     |     |     |
k=1(cid:21)
(cid:22)
λ˜∗
|     | a   | = f,q˜ |     |     |     | (orthonormality). |     |     |
| --- | --- | ------ | --- | --- | --- | ----------------- | --- | --- |
|     | j   | j j    |     |     |     |                   |     |     |
Thefinalexpressionagainallowsforanexplicitanduniquecomputationoftheweight-
ingcoefficients
|     |     |     |     |     | (cid:21) | (cid:22) |     |     |
| --- | --- | --- | --- | --- | -------- | -------- | --- | --- |
f,q˜
|     |     |     |     |     | =    | j   |     |        |
| --- | --- | --- | --- | --- | ---- | --- | --- | ------ |
|     |     |     |     | a   |      | .   |     | (3.16) |
|     |     |     |     | j   | λ˜ ∗ |     |     |        |
j
Thesecoefficientscharacterizetheprojectionofthesolution(3.13)ontotheinfinite-
dimensionalspacespannedbytheeigenfunctions.

3.2. TheKoopmanoperator 43
Usingasimilarprocedure,thelineardifferentialequation(3.11)canbesolvedwith
aspectralrepresentation. Takingtheinnerproductof(3.11)withrespecttoq˜ yields
j
|     | (cid:28) | (cid:29) | (cid:21) (cid:22) |     |     |
| --- | -------- | -------- | ----------------- | --- | --- |
|     |          | dq =     | (cid:21)q,q˜      |     |     |
|     |          | ,q˜      | ,                 |     |     |
|     |          | dt j     | j                 |     |     |
|     | (cid:28) | (cid:29) |                   |     |     |
|     |          |          | (cid:21) (cid:22) |     |     |
dq
= q,(cid:21)∗
|     |          | ,q˜      | q˜                |     | (definitionofadjoint), |
| --- | -------- | -------- | ----------------- | --- | ---------------------- |
|     |          | dt j     | j                 |     |                        |
|     | (cid:28) | (cid:29) |                   |     |                        |
|     |          |          | (cid:21) (cid:22) |     |                        |
dq
= q,λ˜
|     |          | ,q˜      | q˜  |     | (use(3.12)), |
| --- | -------- | -------- | --- | --- | ------------ |
|     |          | dt j     | j j |     |              |
|     | (cid:28) | (cid:29) |     |     |              |
(cid:21) (cid:22)
dq
|     |     | ,q˜ =λ˜∗ | q,q˜ |     | (pulloutconstant), |
| --- | --- | -------- | ---- | --- | ------------------ |
|     |     | j        | j j  |     |                    |
dt
|     | (cid:24) |          | (cid:25) (cid:24) | (cid:25) |     |
| --- | -------- | -------- | ----------------- | -------- | --- |
|     |          | (cid:7)∞ |                   | (cid:7)∞ |     |
da
|     |     | kq  | ,q˜ =λ˜∗ | a q ,q˜ | (expandwith(3.13)), |
| --- | --- | --- | -------- | ------- | ------------------- |
|     |     |     | k j j    | k k j   |                     |
dt
|     |     | k=1 |     | k=1 |     |
| --- | --- | --- | --- | --- | --- |
da
j =λ˜∗
|     |     | a   |     |     | (orthonormality). |
| --- | --- | --- | --- | --- | ----------------- |
j j
dt
Thelastequationshowsthatthelineardynamicsarediagonalizedinthespaceofthe
adjointeigenfunctions,providingasimplespectralrepresentationofthedynamics.
Thevectorandfunctionspacespectralexpansionsproceedinanalmostidentical
manner. The important difference centers around the dimensionality. Specifically,
thevectorspaceisfinitedimensional,ofdimensionn,whilethefunctionspaceisan
infinite-dimensionalHilbertspace. Inpractice,theinfinite-dimensionalspacemustbe
representedbyafinitesumtobecomputationallytractable. Forexample,theFourier
seriestypically converges with relativelyfew terms. Importantly, theKoopman op-
eratorislinearandactsoninfinite-dimensional functionspaces. Incontrast,theun-
derlying dynamical system we are trying to characterize is typically nonlinear and
constrained to finite vector spaces. Theconsequences of this are developed in what
follows.
| 3.2 The | Koopman |     | operator |     |     |
| ------- | ------- | --- | -------- | --- | --- |
With spectral theory in hand, wecan proceed to posit thefundamental concept be-
1931[162]
hind theKoopman operator. Theoriginal work of Koopman in consid-
ered Hamiltonian systems and formulated the Koopman operator in discrete time;
however,webeginwithcontinuoustimeandthenderivetheassociateddiscrete-time
formulation.
Definition: Koopmanoperator: Consideracontinuous-timedynamicalsystem
dx =f(x),
(3.17)
dt
wherex ∈ (cid:22) is astate on asmooth n-dimensional manifold (cid:22). The Koopman oper-
(cid:3)
ator is an infinite-dimensional linear operator that acts on all observable functions
:(cid:22) →(cid:4)sothat
g
|     |     |     |     | (cid:3) g(x)= g(f(x)). | (3.18) |
| --- | --- | --- | --- | ---------------------- | ------ |
Soonaftertheoriginalpaper,KoopmanandvonNeumannextendedtheseresultsto
dynamicalsystemswithcontinuousspectra[163].

| 44  |     |     |     |     |     | Chapter3. | KoopmanAnalysis |     |
| --- | --- | --- | --- | --- | --- | --------- | --------------- | --- |
Bydefinition,theKoopmanoperatorisalinearoperatorthatactsontheHilbert
(cid:2)
spaceofallscalarmeasurementfunctions g. Assuch,itisaninfinite-dimensional
operator. Thus,thetransformationfromthestate-spacerepresentationofthedynam-
ical system to the Koopman representation trades nonlinear, finite-dimensional dy-
namics for linear, infinite-dimensional dynamics. The advantage of such a trade-off
is that wecan solve linear differential equations using the spectral representation of
thelastsection. Ofcourse,aninfinite-dimensionalrepresentationcanbeproblematic,
butinpracticeasufficientlylarge,butfinite,sumofmodesisusedtoapproximatethe
Koopmanspectralsolution. Itshouldbenotedthatthedefinition(3.18)canbealterna-
tivelyrepresentedbyacompositionoftheobservableswiththenonlinearevolution:
(cid:3) = g◦f.
g
TheKoopmanoperatormayalsobedefinedfordiscrete-timedynamicalsystems,
whicharemoregeneralthancontinuous-timesystems. Infact,thedynamicalsystem
:(cid:22) →
in(3.17)willinduceadiscrete-timedynamicalsystemgivenbytheflowmapF
t
|     | (cid:22),whichmapsthestatex(t |     | )toafuturetimex(t |     | +t): |     |     |     |
| --- | ----------------------------- | --- | ----------------- | --- | ---- | --- | --- | --- |
|     |                               |     | 0                 |     | 0    |     |     |     |
(cid:30)
t+t
0
|     |     | F (x(t | ))=x(t | +t)=x(t | )+  | f(x(τ))dτ. |     | (3.19) |
| --- | --- | ------ | ------ | ------- | --- | ---------- | --- | ------ |
|     |     | t      | 0      | 0       | 0   |            |     |        |
t 0
Thisinducesthediscrete-timedynamicalsystem
|     |          |     |     | x =F | (x ), |     |     | (3.20)  |
| --- | -------- | --- | --- | ---- | ----- | --- | --- | ------- |
|     |          |     |     | k+1  | t k   |     |     |         |
|     | = x(kt). |     |     |      |       |     |     | (cid:3) |
where x The analogous discrete-time Koopman operator is given by
|     | k   |     |     |     |     |     |     | t   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
suchthat(cid:3) g = g◦F .Thus,theKoopmanoperatorsetsupadiscrete-timedynamical
t t
|     | systemontheobservablefunction |     |             | g:        |         |     |     |        |
| --- | ----------------------------- | --- | ----------- | --------- | ------- | --- | --- | ------ |
|     |                               |     | (cid:3) g(x | )= g(F (x | ))= g(x | ).  |     | (3.21) |
|     |                               |     | t k         | t         | k       | k+1 |     |        |
ThespectraldecompositionoftheKoopmanoperatorwillbeinstrumentalinrep-
resentingsolutionstoadynamicalsystemofinterest. Thus,weconsidertheeigenvalue
problem
|     |     |     |     | (cid:3)ϕ =λ | ϕ . |     |     | (3.22) |
| --- | --- | --- | --- | ----------- | --- | --- | --- | ------ |
k k k
Thefunctionsϕ (x)areKoopmaneigenfunctions,whichdefineasetofintrinsicmea-
k
surementcoordinates, onwhichitispossible toadvancethesemeasurementswitha
linear dynamicalsystem. Aswasshownpreviously, onecanrepresent theevolution
of the dynamics, in this case on the observables, using an eigenfunction expansion
solutionoftheKoopmanoperator.
AvectorofobservablesgmaybewrittenintermsofKoopmaneigenfunctionsϕ
as
|     |     |     |     | ⎡ ⎤ |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
g (x)
1
|     |     |     |       | ⎢ ( x)⎥ | (cid:7)∞ |     |     |        |
| --- | --- | --- | ----- | ------- | -------- | --- | --- | ------ |
|     |     |     |       | ⎢ g ⎥   |          |     |     |        |
|     |     |     | g(x)= | ⎢ 2 ⎥=  | ϕ (x)v   |     |     |        |
|     |     |     |       | .       |          | ,   |     | (3.23) |
|     |     |     |       | ⎣ . . ⎦ | k        | k   |     |        |
k=1
(x)
g
p
wherev isthekthKoopmanmodeassociatedwiththekthKoopmaneigenfunction
k
ϕ . In the original theory [162], Koopman considered Hamiltonian flows that are
k

3.2. TheKoopmanoperator 45
measurepreserving,sothattheKoopmanoperatorisunitary. Inthiscase,theeigen-
functionsareallorthonormal,and(3.23)maybewrittenexplicitlyas
⎡ ⎤
〈ϕ ,g 〉
k 1
g(x)= (cid:7)∞ ϕ (x) ⎢ ⎢ ⎢ 〈ϕ k . ,g 2 〉⎥ ⎥ ⎥= (cid:7)∞ ϕ (x)v . (3.24)
k ⎣ . ⎦ k k
.
k=1 k=1
〈ϕ ,g 〉
k p
DMDisusedtoapproximatetheKoopman eigenvaluesλ andmodesv ,aswewill
k k
showinthenextsection.
Thecriticalinsighttobegainedinthistransformationisthatthefinite-dimensional,
nonlineardynamicalsystemdefinedbyfin(3.17)andtheinfinite-dimensional,linear
dynamicsdefinedby(cid:3) in(3.18)aretwoequivalentrepresentationsofthesamefun-
damental behavior. Critical to the success of the Koopman theory is the ability to
link the observables g and the associated Koopman mode expansion to the original
evolutiondefinedbyf. Undersuitableconditions,thiscanbeaccomplished,aswillbe
showninwhatfollows. Notethatthisrepresentationishighlyadvantageous. Specif-
ically, one can either evolve the system in the original state space (3.17), requiring
computational effort sinceitisnonlinear,oronecaninsteadevolveusing(3.18)and
(3.23)sothat
(cid:7)∞ (cid:7)∞ (cid:7)∞
(cid:3)g(x)=(cid:3) ϕ (x)v = (cid:3)ϕ (x)v = λ ϕ (x)v . (3.25)
k k k k k k k
k=1 k=1 k=1
Thus, future solutions can be computed by simple multiplication with the Koop-
maneigenvalue. Importantly,theKoopman operator captureseverything about the
nonlineardynamical system (3.17), and itseigenfunctions definea nonlinearchange
ofcoordinatesinwhichthesystembecomeslinear.
Indeed,ifwerestrictourobservablefunctions g toaninvariantsubspacespanned
by eigenfunctions of the Koopman operator, then this induces a linear operator K
that is finite dimensional and advances these eigenobservable functions on this sub-
space[45]. ThisisillustratedinFigure3.1. FindingeigenfunctionsoftheKoopman
operatorandobtainingfinite-dimensionalmodelsisbothchallengingandrewarding.
Evenknowingwhichtermsinthedynamicalsystemareactivemaybeachallenge,al-
thoughnewtechniquesfrommachinelearningidentifyrelevanttermsinthedynamics
fromdata[252,295,47].
ItwasshownrecentlythatlevelsetsoftheKoopmaneigenfunctionsforminvari-
antpartitionsofthestate-spaceforagivendynamicalsystem[51]. Thisresultimplies
thatKoopmaneigenfunctionsmaybeusedtorepresentandanalyzetheergodicpar-
tition [197, 50]. Another important result shows that Koopman analysis is able to
generalizeand extend theHartman–Grobman theorem totheentirebasin ofattrac-
tionofastableorunstableequilibriumpointorperiodicorbit[170]. Moredetailed
andin-depthdiscussionofthesetopicsarecoveredintheexcellent reviewsbyMezi´c
etal.[52,195].
ItisworthnotingthattheadjointoftheKoopmanoperatoristhePerron–Frobenius
operator,whichisfrequentlyusedtoanalyzetheflowofprobabilitydensitiesthrough
adynamicalsystem[79,100,102,101]. Perron–Frobeniuscomputationsareoftenre-
latedtothecalculationofalmost-invariantsets[102,103,274,303]usingset-oriented
methods[79,80]toidentifyeigenvectorsofthePerron–Frobeniusoperator. Almost-
invariantsetsareuseful tounderstandsensitivityandcoherenceinfluidsystemsand
alsohaverelevancetouncertaintyquantification.

| 46  |     |     |     |     |     |     | Chapter3. |     | KoopmanAnalysis |     |     |
| --- | --- | --- | --- | --- | --- | --- | --------- | --- | --------------- | --- | --- |
Rm
|     |     | x2  |     | M   |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     | x3  |     |     |     |     | y   |     | y   |     |
|     |     | F   |     | xN  |     | g   |     | 2   | y   | N   |     |
|     |     | t   |     |     |     |     |     |     |     | 3   |     |
K
t
x1
y 1
|     |     | K   |     | K   | K   | K                     |     |     |         |              |     |
| --- | --- | --- | --- | --- | --- | --------------------- | --- | --- | ------- | ------------ | --- |
|     |     | t   |     | t y | t   | (cid:2)(cid:2)(cid:2) | t y |     | Fft :xk | (cid:2)→xk+1 |     |
|     | y 1 |     | y 2 | 3   |     |                       | N   |     |         |              |     |
|     |     |     |     |     |     |                       |     |     | :xk     | (cid:2)→     |     |
g g g g g g (cid:1)(cid:1)(cid:1)y(cid:1)k(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)(cid:1)
|     |     |     |     |     |     | (cid:2)(cid:2)(cid:2) |     |     | KU :y | (cid:2)→y |     |
| --- | --- | --- | --- | --- | --- | --------------------- | --- | --- | ----- | --------- | --- |
|     | x1  |     | x2  | x3  |     |                       | xN  |     | tt    | k         | k+1 |
|     |     | F   |     | F   | F   | F                     |     |     |       |           |     |
|     |     | t   |     | t   | t   |                       | t   |     |       |           |     |
Figure 3.1. Schematic illustrating the Koopman operator restricted to a finite-
dimensionalinvariantsubspacespannedbyeigenobservablefunctions. Therestrictionof(cid:3) tothis
subspaceresultsinK,whichinducesafinite-dimensionallinearsystemontheinvariantsubspace.
ReprintedwithpermissionfromthePublicLibraryofScience[45].
| 3.3 Connections |     |     | with | DMD |     |     |     |     |     |     |     |
| --------------- | --- | --- | ---- | --- | --- | --- | --- | --- | --- | --- | --- |
TheDMDalgorithmdeterminestheKoopmaneigenvaluesandmodesdirectlyfrom
dataundersuitableconditions. Specifically,thechoiceofobservableswillplayacrit-
[301].
ical role in the success of the Koopman method Figure 3.2 shows the stan-
dardDMDapproachandcontrastsitwiththeKoopmanmodedecomposition. Before
demonstratingtheconnection,werecallthedefinitionoftheDMDmethod[290].
Definition: DMD(Tu et al. 2014 [290]): Supposewehaveadynamicalsystem(3.17)
andtwosetsofdata,
|     |     |     |     |     | ⎡         |                   |               | ⎤   |     |     |         |
| --- | --- | --- | --- | --- | --------- | ----------------- | ------------- | --- | --- | --- | ------- |
|     |     |     |     | X=⎣ |           |                   |               | ⎦   |     |     |         |
|     |     |     |     |     | x         | x                 | ··· x         | ,   |     |     | (3.26a) |
|     |     |     |     |     | 1         | 2                 | m−1           |     |     |     |         |
|     |     |     |     |     | ⎡         |                   |               | ⎤   |     |     |         |
|     |     |     |     |     | (cid:5)=⎣ |                   |               | ⎦   |     |     |         |
|     |     |     |     | X   | x         | (cid:5) x (cid:5) | ··· x (cid:5) | ,   |     |     | (3.26b) |
|     |     |     |     |     |           | 1 2               | m−1           |     |     |     |         |
(cid:5)
with x an initial condition to (3.17) and x its corresponding output after some pre-
|     |     | k   |     |     |     | k   |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
scribedevolutiontimeΔt,withm−1initialconditionsconsidered. TheDMDmodesare
eigenvectorsof
(cid:5)
|     |     |     |     |     | A   | =X X†, |     |     |     |     | (3.27) |
| --- | --- | --- | --- | --- | --- | ------ | --- | --- | --- | --- | ------ |
X
where†denotestheMoore–Penrosepseudoinverse.
Withthisdefinition,wecannowmoreformallyconsiderthesetof p observables
|     |     |     |     | :(cid:22) | →(cid:4), |     | =1,2,...,p. |     |     |     |        |
| --- | --- | --- | --- | --------- | --------- | --- | ----------- | --- | --- | --- | ------ |
|     |     |     |     | g         |           |     | j           |     |     |     | (3.28) |
j
Weletg= [g g ··· g ]T denotethecolumn vectorof observables. Wenowcon-
|     |     |     | 1 2 | p   |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
structdatamatricesYandY (cid:5) byconsideringasetofinitialconditions{x x ··· x }
|     |     |     |     |     |     |     |     |     |     | 1 2 | m−1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

| 3.3. ConnectionswithDMD |            |      |     |     |            |               |          |     | 47  |
| ----------------------- | ---------- | ---- | --- | --- | ---------- | ------------- | -------- | --- | --- |
|                         |            | Data |     |     |            |               | Dynamics |     |     |
| nampooK                 | Nonlinear  |      |     |     |            | Koopman Model |          |     |     |
|                         |            |      |     | A = | Y(cid:2)Y† |               |          |     |     |
Y
|     | Observables      |     |            |          |     | g(x | ) ≈ | Kg(x | )   |
| --- | ---------------- | --- | ---------- | -------- | --- | --- | --- | ---- | --- |
|     |                  |     |            |          |     |     | k+1 |      | k   |
|     | g(X),g(X(cid:2)) |     | Y,Y(cid:2) |          |     |     |     |      |     |
|     |                  | →   |            | DMD Alg. |     |     |     |      |     |
|     |                  |     |            |          |     |     | K = | A    |     |
Y
|     |               |            |     |              |     | Complex System  |     |     | (cid:3) |
| --- | ------------- | ---------- | --- | ------------ | --- | --------------- | --- | --- | ------- |
|     |               |            |     |              |     | x               | x   | x   |         |
|     | Data Matrices |            |     | Measurements |     | 2               | 3   | m   |         |
|     |               | X,X(cid:2) |     |              |     |                 | x   | = F | (x )    |
|     |               |            |     |              |     |                 | k+1 |     | t k     |
x
1 (unknown dynamics)
|     | Observables |     |     | A = | X(cid:2)X† |     | DMD Model |     |     |
| --- | ----------- | --- | --- | --- | ---------- | --- | --------- | --- | --- |
| DMD |             |     |     | X   |            |     |           |     |     |
|     |             |     |     |     |            |     | x ≈       | Ax  |     |
|     |             |     |     |     |            |     | k+1       | k   |     |
X,X(cid:2)
|     |     |     |     | DMD Alg. |     |     | A = | A   |     |
| --- | --- | --- | --- | -------- | --- | --- | --- | --- | --- |
X
Figure 3.2. Schematicofhowtousedata togeneratedynamical systemsmodelsofan
DMD/Koopman
unknown complexsystem in the framework. Instandard DMD, wetake mea-
surementsofthestatesofthesystemandconstructamodelthatmapsXtoX(cid:5).
Koopmanspectral
analysisenrichesthemeasurementswithnonlinearobservationsy=g(x)toprovideabettermap-
pingfromYtoY(cid:5)thatapproximatestheinfinite-dimensionalKoopmanmapping.Thepredictionof
theobservablesinthefuturefromtheKoopmanmodelmaybeusedtorecoverthefuturestatex ,
m+1
providedthattheobservationfunctiongisinjective. BoththeDMDandKoopmanapproachesare
| equation-free,inthattheydonotrelyonknowingF |     |     |     |     | .   |     |     |     |     |
| ------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
t
to(3.17). ThecolumnsofthematrixYaregivenbyy =g(x ). ThecolumnsofY (cid:5)
|     |     |     |     |     |     | k   | k   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
aregivenbyevolving(3.17)forwardintimeaprescribedtimeΔt
andviewingtheout-
|     |     |     |     |     |     | (cid:5) = g(f(x | )). |     |     |
| --- | --- | --- | --- | --- | --- | --------------- | --- | --- | --- |
put vector through the observables, denoted by y Theresulting DMD
|     |     |     |     |     |     | k   | k   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
=Y (cid:5) Y†,whichgivestherequisite
| algorithmonthedataofobservables |     |     |     | producesA |     |     |     |     |     |
| ------------------------------- | --- | --- | --- | --------- | --- | --- | --- | --- | --- |
Y
Koopmanapproximation. Theprocedure, anditscomparisontothestandardDMD
method,areshowninFigure3.2. NotethatYandY (cid:5) computeDMDonthespaceof
observables insteadofonthestate-space. Wecannowintroducethefollowingtheo-
rem[235,290,237,301].
Theorem: KoopmanmodedecompositionandDMD:Letϕ beaneigenfunctionof
k
| (cid:3) witheigenvalueλ |     | ,andsupposeϕ |         | ∈span{g     | },sothat |           |     |     |        |
| ----------------------- | --- | ------------ | ------- | ----------- | -------- | --------- | --- | --- | ------ |
|                         |     | k            |         | k           | j        |           |     |     |        |
|                         |     | ϕ (x)=w      | g (x)+w | g (x)+···+w |          | g (x)=w·g |     |     | (3.29) |
|                         |     | k            | 1 1     | 2 2         |          | p p       |     |     |        |
forsomew=[w w ··· w ]T ∈(cid:4)p. Ifw∈R(Y),whereRistherange,thenwisaleft
|                | 1   | 2               | p   |          |     |      |     |     |     |
| -------------- | --- | --------------- | --- | -------- | --- | ---- | --- | --- | --- |
|                |     | witheigenvalueλ |     |          | ∗   | =λ ∗ |     |     |     |
| eigenvectorofA |     |                 |     | sothatw˜ | A   | w˜ . |     |     |     |
|                | Y   |                 |     | k        | Y   | k    |     |     |     |

| 48  |     |     |     | Chapter3. KoopmanAnalysis |
| --- | --- | --- | --- | ------------------------- |
ThisthusshowsthattheKoopmaneigenvaluesaretheDMDeigenvaluesprovided
(i)thesetofobservablesissufficientlylargesothatϕ (x)∈span{g }and(ii)thedatais
|     |     |     |     | k j |
| --- | --- | --- | --- | --- |
sufficientlyrichsothatw∈R(X¯).
Thisdirectlyshowsthatthechoiceofobservablesis
criticalinallowingonetoconnectDMDtheorytoKoopmanspectralanalysis. Ifthis
canbedone,thenonecansimplytakedatasnapshotsofafinite-dimensionalnonlinear
dynamicalsystemintimeandreparameterizeitaslinear,infinite-dimensionalsystem
thatisamenabletoasimpleeigenfunction(spectral)decomposition. Thisrepresenta-
tiondiagonalizesthedynamicsandshowsthatthetimeevolutionofeacheigenfunc-
tioncorrespondstomultiplicationbyitscorrespondingeigenvalue.
| 3.3.1 Finite | approximation | of the Koopman | operator |     |
| ------------ | ------------- | -------------- | -------- | --- |
TheabovedefinitionsprovideanabstractframingoftheKoopmantheory. Notethat
tocomputemanyofthemeaningfulquantitiesinFigure3.2wouldrequireknowledge
oftheright-handsidef(·)in(3.17). Butthefactthatwedonotknowtheprescribed
evolutionispreciselywhyweareusingtheDMDframework.
In practice, we must consider three important practical constraints: (i) we have
dataXandX (cid:5) ,butwedonotknowf(·);(ii)wewillhavetomakeafinite-dimensional
(cid:3);
approximation to the infinite-dimensional Koopman operator and (iii) we will
havetojudiciouslyselecttheobservables g(x)tohaveconfidencethattheKoopman
f(·).
operator will approximate the nonlinear dynamics of Points (i) and (ii) go nat-
urally together. Specifically, thenumber of measurementsin each column of X and
X (cid:5) is n, while thenumber of total columns (time measurements) is m. Thus finite-
dimensionalityisimposedsimplyfromthedatacollectionlimitations.Thedimension
canbeincreasedwithalargesetofobservables, oritcanbedecreasedviaalow-rank
truncationduringtheDMDprocess. Theobservablesaremoredifficulttodealwith
in a principled way. Indeed, a good choice of observables can make the method ex-
tremelyeffective, butitwould alsorequireexpert knowledgeofthesystemathand.
Thiswillbediscussedfurtherintheexamples.
Thefollowinggivesapracticaldemonstrationofhowtousethedataandtheob-
servablestoproduceaKoopmanoperatorandafuture-statepredictionofthenonlin-
ear evolution (3.17). It should be compared to the DMD algorithm on the space of
state-space variables introduced in the introduction. Essentially, the algorithm now
needstobeappliedinthespaceofobservables.
|     | 1. First,fromthedatamatricesXandX,createthedatamatricesofobservables |     | (cid:5) |     |
| --- | -------------------------------------------------------------------- | --- | ------- | --- |
(cid:5)
YandY:
|     |     | ⎡       |             | ⎤      |
| --- | --- | ------- | ----------- | ------ |
|     |     | Y=⎣ g(x | ) g(x ) ··· | g(x )⎦ |
m−1 , (3.30a)
1 2
|     |     | ⎡             |                       | ⎤                  |
| --- | --- | ------------- | --------------------- | ------------------ |
|     |     | (cid:5)=⎣ g(x | (cid:5)) g(x (cid:5)) | ··· g(x (cid:5) )⎦ |
Y , (3.30b)
|     |     |     | 1 2       | m−1                    |
| --- | --- | --- | --------- | ---------------------- |
|     |     |     | =g(x )ory | (cid:5) =g(x (cid:5)). |
whereeachcolumnisgivenbyy
|     |     |     | k k | k k |
| --- | --- | --- | --- | --- |
2. Next,performtheDMDalgorithmtocompute
(cid:5)
A =Y Y† (3.31)
Y

3.4. Exampledynamicalsystems 49
alongwiththelow-rankcounterpart A˜ . Theeigenvaluesandeigenvectorsof
Y
A mayapproximateKoopmaneigenvaluesandmodes,dependingonthesetof
Y
observableschosen.
3. DMDcan beused tocompute theaugmented modesΦ , whichmay approxi-
Y
matetheKoopmanmodes,by(seestep4intheDMDalgorithm)
Φ =Y (cid:5) VΣ−1W, (3.32)
Y
whereWcomesfromtheeigenvalueproblemA ˜ W=WΛandY=UΣV ∗ .
Y
4. Thefuturestateinthespaceofobservablesisthengivenbythelinearevolution
y(t)=Φ diag(exp(ωt))b, (3.33)
Y
whereb=Φ†y isdeterminedbyprojectingbacktotheinitialdataobservable,
Y 1
andω arethesetofeigenvaluesλ generated fromthematrixΛ,whereω =
k k
ln(λ )/Δt.
k
5. Transformfromobservablesbacktostate-space:
y =g(x ) → x =g −1(y ). (3.34)
k k k k
Thislaststepcanbetrivialifoneoftheobservablesselectedtocompriseg(x )is
k
thestatevariablex itself. Ifonlynonlinearobservablesofx arechosen,then
k k
theinversionprocesscanbedifficult.
This process shows that the DMD algorithm is closely related to the Koopman
operator. Indeed, it is the foundational piece for practical evaluation of the finite-
dimensional Koopman operator. We stress once again that selection of appropriate
observablesiscriticalforthealgorithmtogenerategoodapproximationtothefuture
state.
3.4 Example dynamical systems
ThesuccessoftheKoopmantheoryreliesprimarilyonexpert-in-the-loopchoicesof
theobservables g(x). In what follows, weintroduce acouple of examples where an
attemptismadetoshowhowafuturestateisapproximatedusingstandardDMDon
statevariablesversus theKoopman decomposition on theobservables. Thestarting
point is a one-dimensional example that can be worked out in complete detail. We
finish with apartial differential equationsexample using thecompletely data-driven
approachillustratedinFigure3.2.
3.4.1 One-degree-of-freedom system
ThesimplestexampleoftheKoopmanframeworkcanbedemonstratedwiththesta-
ble,one-degree-of-freedomsystem
dx
=−μx (3.35)
dt
whose solution is x(t) = x(0)exp(−μt), where x(0) is the initial condition. Thus,
thefuturestateofthesystemcanbefoundinthestate-spacerepresentationbysimple
multiplicationoftheinitialconditionbyexp(−μt).

| 50  |     |     |     | Chapter3. | KoopmanAnalysis |     |
| --- | --- | --- | --- | --------- | --------------- | --- |
Forthisexample,wedefinetheobservable
g(x)=x
(3.36)
andnotethat
|     | (cid:3) g(x)= | g(xexp(−μt)) | → (cid:3)x=xexp(−μt). |     |     | (3.37) |
| --- | ------------- | ------------ | --------------------- | --- | --- | ------ |
ThisshowsthattheKoopmaneigenfunctionandeigenvaluearegivenby
|     |     |     | ϕ =x, |     |     | (3.38a) |
| --- | --- | --- | ----- | --- | --- | ------- |
1
|     |     |     | λ =−μ. |     |     | (3.38b) |
| --- | --- | --- | ------ | --- | --- | ------- |
1
Thisresultillustratesthefactthattheeigenvaluesforlinearlystablesystemsarecon-
tainedwithinthespectrumoftheKoopmanoperator[235].
However,thesetofeigenvaluesoftheKoopmanoperatorislargerthanthatofthe
linearones,anditdependsonthespaceoffunctionsinwhichtheevolutionistaking
place[104].
Todemonstratethis,considerinsteadtheobservable
g(x)=xn,
(3.39)
wheren∈(cid:5)+
. Inthiscase,
|     | (cid:3) g(x)= | g(xexp(−μt)) | → (cid:3)xn=xnexp(−nμt) |     |     | (3.40) |
| --- | ------------- | ------------ | ----------------------- | --- | --- | ------ |
or,inobservablenotation,
|     |     | (cid:3) g(x)=exp(−nμt)g(x). |     |     |     | (3.41) |
| --- | --- | --------------------------- | --- | --- | --- | ------ |
ThisgivestheKoopmaneigenfunctionandeigenvalue
|     |     |     | ϕ =xn, |     |     | (3.42a) |
| --- | --- | --- | ------ | --- | --- | ------- |
n
|     |     |     | λ =−nμ. |     |     | (3.42b) |
| --- | --- | --- | ------- | --- | --- | ------- |
n
Anyobservablecanthenbefoundbytheexpansion
(cid:7)∞
|     |     | g(x)= | v xk |     |     | (3.43) |
| --- | --- | ----- | ---- | --- | --- | ------ |
k
k=1
withsolutionattimet inthefuturegivenby
(cid:7)∞
|     |     | (cid:3) g(x)= | v exp(−kμt)xk. |     |     | (3.44) |
| --- | --- | ------------- | -------------- | --- | --- | ------ |
k
k=1
ThissimplestofexamplesillustrateshowtheKoopmanspaceofeigenfunctionsisac-
tually infinite dimensional, with a spanning set that is much larger than one might
initiallythink. Moreover,thisspaceisdirectlytiedtotheobservablesusedtoinvesti-
gatethesystem.

| 3.4. Exampledynamicalsystems |           |           |     |        |     |     |     |     |     | 51  |
| ---------------------------- | --------- | --------- | --- | ------ | --- | --- | --- | --- | --- | --- |
| 3.4.2                        | Nonlinear | dynamical |     | system |     |     |     |     |     |     |
Nowconsiderthefollowingnonlinearordinarydifferentialequationintwovariables:
=μx
|     |     |     |     |     | x˙  | ,   |     |     |     | (3.45a) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- |
|     |     |     |     |     | 1   | 1   |     |     |     |         |
=λ(x −x2).
|     |     |     |     |     | x˙  |     |     |     |     | (3.45b) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- |
|     |     |     |     |     | 2   | 2 1 |     |     |     |         |
Ifλ(cid:20)|μ|< 0, thenthedynamicsof x converge rapidlyto x2, sothat x = x2 isa
|     |     |     |     |     |     | 2   |     | 1   |     | 2 1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
slowmanifold. Thisexamplehasbeen used todemonstratetheabilityoftheKoop-
manoperatortocapturenonlineardynamicsintermsofalinearoperatoronnonlinear
measurementsofthestatex[290,45]. Inparticular,ifwerestricttheKoopmanoper-
x2,thenwe
atortoanobservablesubspacespannedbythemeasurements x , x ,and
|     |     |     |     |     |     |     |     | 1   | 2   | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
obtainalineardynamicalsystemonthesethreestatesthatadvancestheoriginalstate
x:
|     |     | ⎡   | ⎤    | ⎡ ⎤ |     | ⎡ ⎤ ⎡      |                  | ⎤⎡       | ⎤   |        |
| --- | --- | --- | ---- | --- | --- | ---------- | ---------------- | -------- | --- | ------ |
|     |     |     | y    | x   |     | y          | μ 0              | 0        | y   |        |
|     |     |     | 1⎦=⎣ | 1⎦  |     | d 1⎦=⎣     |                  |          | 1⎦  |        |
|     |     | ⎣   |      | =⇒  |     | ⎣          | λ                | −λ⎦⎣     |     |        |
|     |     |     | y    | x   |     | y          | 0                |          | y . | (3.46) |
|     |     |     | 2    | 2   | dt  | 2          |                  |          | 2   |        |
|     |     |     | y    | x 2 |     | y          | 0 0              | 2μ       | y   |        |
|     |     |     | 3    | 1   |     | 3 (cid:17) | (cid:18)(cid:19) | (cid:20) | 3   |        |
K
=x2,isclosely
Thisprocedureofincludinghigher-orderpowersofthestate,asiny
relatedtotheCarlemanlinearization[61,267,164],whichhasextensionstononlinear 3 1
control[37,16,270].
Bylookingatlefteigenvectorsϕ˜
|     |     |     |     |     | α   | oftheKoopman | operatorKcorresponding |     |     | to  |
| --- | --- | --- | --- | --- | --- | ------------ | ---------------------- | --- | --- | --- |
eigenvaluesα,
|     |     |     |     |     | ϕ˜ ∗ | K=αϕ˜ ∗ |     |     |     |        |
| --- | --- | --- | --- | --- | ---- | ------- | --- | --- | --- | ------ |
|     |     |     |     |     | α    | α ,     |     |     |     | (3.47) |
itispossibletoobtaineigenfunctionmeasurementsϕ (x)=ϕ˜ ∗ y(x),whichareintrin-
α
α
siccoordinates. Forthisexample,ϕ =x andϕ =x −bx2,whereb =λ/(λ−2μ)
|     |     |     |     |     | μ   | 1 λ | 2   | 1   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
parameterizeshowaggressivelytheslowmanifoldattractstrajectories.
ALGORITHM3.1.Generatedataforanonlineardynamicalsystem.
mu = -.05;
|     | lambda  | = -1; |          |          |     |            |     |         |        |     |
| --- | ------- | ----- | -------- | -------- | --- | ---------- | --- | ------- | ------ | --- |
|     | A = [mu | 0 0;  | 0 lambda | -lambda; |     | 0 0 2*mu]; | %   | Koopman | linear |     |
dynamics
|     | [T,D]          | = eig(A); |     |                |     |         |     |        |          |     |
| --- | -------------- | --------- | --- | -------------- | --- | ------- | --- | ------ | -------- | --- |
|     | slope_stab_man |           | =   | T(3,3)/T(2,3); |     | % slope | of  | stable | subspace | (   |
green)
|     | %% Integrate |                               | Koopman | trajectories |     |     |     |     |     |     |
| --- | ------------ | ----------------------------- | ------- | ------------ | --- | --- | --- | --- | --- | --- |
|     | y0A =        | [1.5;                         | -1;     | 2.25];       |     |     |     |     |     |     |
|     | y0B =        | [1; -1;                       | 1];     |              |     |     |     |     |     |     |
|     | y0C =        | [2; -1;                       | 4];     |              |     |     |     |     |     |     |
|     | tspan        | = 0:.01:1000;                 |         |              |     |     |     |     |     |     |
|     | [t,yA]       | = ode45(@(t,y)A*y,tspan,y0A); |         |              |     |     |     |     |     |     |
|     | [t,yB]       | = ode45(@(t,y)A*y,tspan,y0B); |         |              |     |     |     |     |     |     |
|     | [t,yC]       | = ode45(@(t,y)A*y,tspan,y0C); |         |              |     |     |     |     |     |     |

| 52  |     |     |     |     |     | Chapter3. | KoopmanAnalysis |
| --- | --- | --- | --- | --- | --- | --------- | --------------- |
Figure3.3.Visualizationofthree-dimensionallinearKoopmansystemfrom(3.46)(black
curves).Projectedontothex -x plane,theseblackcurvesrepresentsolutionstothenonlineardynam-
|     |     |     | 1 2 |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
icalsystemin(3.45a).Trajectoriesattractrapidlyontotheslowmanifold(red). Thethree-dimensional
linearsystemhasaslowsubspace(green),andtrajectoriesarealsoconstrainedtostartonthelevelset
y =y2(blue). Inthisexample,μ=−0.05andλ=1. ReprintedwithpermissionfromthePublic
3 1
LibraryofScience[45].
ALGORITHM3.2.PlotKoopmanlinearization ofnonlineardynamicalsystem.
|     | % Attracting                         | manifold | $y_2=y_1^2$ |     | (red | manifold) |     |
| --- | ------------------------------------ | -------- | ----------- | --- | ---- | --------- | --- |
|     | [X,Z] = meshgrid(-2:.01:2,-1:.01:4); |          |             |     |      |           |     |
Y = X.^2;
surf(X,Y,Z,’EdgeColor’,’None’,’FaceColor’,’r’,’FaceAlpha’,.1)
|     | hold on,    | grid on,                     | view(-15,8), |     | lighting        | gouraud |     |
| --- | ----------- | ---------------------------- | ------------ | --- | --------------- | ------- | --- |
|     | % Invariant | set                          | $y_3=y_1^2$  |     | (blue manifold) |         |     |
|     | [X1,Y1] =   | meshgrid(-2:.01:2,-1:.01:4); |              |     |                 |         |     |
Z1 = X1.^2;
surf(X1,Y1,Z1,’EdgeColor’,’None’,’FaceColor’,’b’,’FaceAlpha’,.1)
|     | % Stable | invariant | subspace |     | of Koopman | linear | system (green |
| --- | -------- | --------- | -------- | --- | ---------- | ------ | ------------- |
plane)
[X2,Y2]=meshgrid(-2:0.01:2,0:.01:4);
|     | Z2 = slope_stab_man*Y2;                          |     |     | % for | mu=-.2 |     |          |
| --- | ------------------------------------------------ | --- | --- | ----- | ------ | --- | -------- |
|     | surf(X2,Y2,Z2,’EdgeColor’,’None’,’FaceColor’,[.3 |     |     |       |        |     | .7 .3],’ |
FaceAlpha’,.7)
x = -2:.01:2;
|     | % intersection | of  | green | and | blue surfaces | (below) |     |
| --- | -------------- | --- | ----- | --- | ------------- | ------- | --- |
plot3(x,(1/slope_stab_man)*x.^2,x.^2,’-g’,’LineWidth’,2)
|     | % intersection | of  | red and | blue | surfaces | (below) |     |
| --- | -------------- | --- | ------- | ---- | -------- | ------- | --- |
plot3(x,x.^2,x.^2,’--r’,’LineWidth’,2)

3.4. Exampledynamicalsystems 53
plot3(x,x.^2,-1+0*x,’r--’,’LineWidth’,2);
| %% Plot Koopman | Trajectories | (from lines | 15-17) |
| --------------- | ------------ | ----------- | ------ |
plot3(yA(:,1),yA(:,2),-1+0*yA,’k-’,’LineWidth’,1);
plot3(yB(:,1),yB(:,2),-1+0*yB,’k-’,’LineWidth’,1);
plot3(yC(:,1),yC(:,2),-1+0*yC,’k-’,’LineWidth’,1);
plot3(yA(:,1),yA(:,2),yA(:,3),’k’,’LineWidth’,1.5)
plot3(yB(:,1),yB(:,2),yB(:,3),’k’,’LineWidth’,1.5)
plot3(yC(:,1),yC(:,2),yC(:,3),’k’,’LineWidth’,1.5)
| plot3([0 0],[0     | 0],[0 -1],’ko’,’LineWidth’,4) |                |     |
| ------------------ | ----------------------------- | -------------- | --- |
| set(gca,’ztick’,[0 | 1 2 3 4                       | 5])            |     |
| axis([-4 4 -1      | 4 -1 4])                      |                |     |
| xlabel(’y_1’),     | ylabel(’y_2’),                | zlabel(’y_3’); |     |

Chapter 4
Video Processing
ThischapterintroducesDMDforrobustseparationofvideoframesintobackground
(low-rank)andforeground(sparse)componentsinrealtime.Themethod,asoriginally
conceivedbyGrosekandKutz[121],providesanovelapplicationoftheDMDtech-
nique and its dynamical decomposition for state-of-the-art video processing. DMD
modeswithFourierfrequenciesneartheorigin(zeromodes)areinterpretedasback-
ground (low-rank) portions of the given video frames, and modes with Fourier fre-
quenciesboundedawayfromtheoriginconstitutetheirsparsecounterparts. Anap-
proximate low-rank/sparse separation is achieved at the computational cost of just
oneSVDandonelinearequationsolve,producingresultsordersofmagnitudefaster
thanacompetingseparation method, robust principalcomponent analysis(RPCA).
TheDMDmethoddevelopedhereisdemonstratedtoworkrobustlyinrealtimewith
personal laptop-class computingpowerand withoutanyparameter tuning, which is
atransformativeimprovementinperformancethatisidealforvideosurveillanceand
recognitionapplications[168,91].
4.1 Background/foreground video separation
Thereisagrowingdemandforaccurate andreal-timevideosurveillance techniques.
Specifically,manycomputervisionapplicationsfocusonalgorithmsthatcanremove
backgroundvariationsinavideostream,whicharehighlycorrelatedbetweenframes,
tohighlightforegroundobjectsofpotentialinterest. Background/foreground separa-
tion is typically an integral step in detecting, identifying, tracking, and recognizing
objectsinvideosequences. Mostmoderncomputervisionapplicationsdemandalgo-
rithmsthatcanbeimplementedinrealtimeandthatarerobustenoughtohandledi-
verse,complicated,andclutteredbackgrounds. Competitivemethodsoftenneedtobe
flexibleenoughtoaccommodatevariationsinascene,includingchangesinillumina-
tionthroughouttheday. Giventheimportanceofthistask,avarietyofiterativetech-
niquesandmethodshavealreadybeendevelopedtoperformbackground/foreground
separation [175, 279, 187, 128, 56]. (See also, for instance, the recent review [25],
whichcompareserrorandtimingofvariousmethods.)
One potential viewpoint for this computational task is to separate a matrix (or
video)intolow-rank(background)andsparse(foreground)components. Recently,this
viewpointhasbeenadvocated byCandèsetal.intheframeworkofRPCA[56]. By
55

56 Chapter4. VideoProcessing
Figure 4.1. Illustration of the DMD method where snapshots (pixels of video frames)
x arevectorizedandalineartransformation Aisconstructed. TheDMDmethodconstructsthe
k
bestmatrixAthatminimizestheleast-squareerrorforalltransformationsx
k+1
=Ax
k
withk =
1,2,...,m−1.
weightinga combination of the nuclear and the (cid:2) -norms, a convenient convex op-
1
timization problem (principal component pursuit) was demonstrated, under suitable
assumptions, toexactly recover thelow-rank and sparse componentsofagiven data
matrix. TheRPCA technique, which has itscomputational costsdominated by the
convex optimization procedure, was shown to be competitive in comparison to the
state-of-the-artcomputervisionproceduredevelopedbyDelaTorreandBlack[169].
Here, weuseDMDinsteadofRPCAforvideoprocessing. Intheapplicationof
videosurveillance,thevideoframescanbethoughtofassnapshotsofsomeunderlying
complex/nonlineardynamics,asinFigure4.1. DMDyieldsoscillatorytimecompo-
nents of the video frames that have contextual implications. Namely, those modes
thatareneartheoriginrepresentdynamicsthatareunchanging,orchangingslowly,
and can be interpreted as stationary background pixels, or low-rank components of
thedatamatrix. Incontrast, thosemodesbounded away from theoriginarechang-
ingon(cid:23)(1)timescalesorfasterandrepresenttheforegroundmotioninthevideo,or
thesparsecomponentsofthedatamatrix. Thus,byapplyingthedynamicalsystems
DMDinterpretationtovideoframes,anapproximateRPCAtechniquecanbeenacted
atafixedcostofanSVDandalinearequationsolve.
UnliketheconvexoptimizationprocedureofCandèsetal.[56],whichcanbeguar-
anteedtoexactlyproducealow-rankandsparseseparationundercertainassumptions,
nosuchguaranteesarecurrentlygivenfortheDMDprocedure. However,incompar-
isonwiththeRPCAandothercomputervision[169]methods,theDMDprocedure
isordersofmagnitudefasterincomputationalperformance,resultinginreal-timesep-
arationonlaptop-classcomputingpower.
4.2 RPCA and DMD
Givenacollectionofdatafromapotentiallycomplex, nonlinearsystem,theRPCA
methodseeksout thesparse structureswithinthedata, whilesimultaneouslyfitting
the remaining entries to a low-rank basis. As long as the given data is truly of this
nature,inthatitliesonalow-dimensionalsubspaceandhassparsecomponents,then
theRPCAalgorithmhasbeen provenbyCandèsetal.[56]toperfectlyseparate the

| 4.2. | RPCAandDMD |     |     |     |     | 57  |
| ---- | ---------- | --- | --- | --- | --- | --- |
givendataXaccordingto
|     |     |     |     | X=L+S, |     | (4.1) |
| --- | --- | --- | --- | ------ | --- | ----- |
where
|     |     |     | L   | → low-rank, |     |     |
| --- | --- | --- | --- | ----------- | --- | --- |
|     |     |     | S   | → sparse.   |     |     |
ThekeytotheRPCAalgorithmisformulatingthisproblemintoatractable,non-
smoothconvexoptimizationproblemknownasprincipalcomponentpursuit(PCP):
|     |     |     | argmin | (cid:7)L(cid:7) | +λ(cid:7)S(cid:7) |     |
| --- | --- | --- | ------ | --------------- | ----------------- | --- |
|     |     |     |        | ∗               | 1                 |     |
(4.2)
|     |     |     | subjectto | X=L+S. |     |     |
| --- | --- | --- | --------- | ------ | --- | --- |
(cid:7)M(cid:7) :=
Here(cid:4)(cid:9)PCP m(cid:5)inimizes the weighed combin ation of the nuclear norm, ∗
(cid:2)
|     | M∗M   |           | (cid:2) | (cid:7)M(cid:7) := | |m |.                     |     |
| --- | ----- | --------- | ------- | ------------------ | ------------------------- | --- |
|     | trace | , and the | -norm,  |                    | The scalar regularization | pa- |
|     |       |           | 1       | 1                  | ij ij                     |     |
rameterisnonnegative: λ≥0. From theoptimization problem (4.2), itcanbeseen
|     | thatasλ → |     |     |     |     | L→  |
| --- | --------- | --- | --- | --- | --- | --- |
0, thelow-rank structurewill incorporate all ofthegiven data, X,
leaving the sparse structure as a zero matrix. It is also true that as λ increases, the
sparsestructurewillembodymoreandmoreoftheoriginaldatamatrix,S→X,asL
commensuratelyapproachesthezeromatrix[56,166].
In effect, λ controls the dimensionality of the low-rank subspace; however, one
Candèsetal.[56]haveshownthatthe
doesnotneedtoknowtherankofLapriori.
choice
1
|     |     |     | λ=  | (cid:31) | ,   | (4.3) |
| --- | --- | --- | --- | -------- | --- | ----- |
max(n,m)
whereXisn×m,hasahighprobabilityofsuccessatproducingthecorrectlow-rank
andsparseseparationprovidedthatthematricesLandSareincoherent,whichisthe
caseformanypracticalapplications.
AlthoughtherearemultiplealgorithmsthatcansolvetheconvexPCPproblem,
the augmented Lagrange multiplier (ALM) method stands out as a simple and stable
algorithm with robust, efficient performance characteristics. The ALM method is
effectivebecauseitachieveshighaccuraciesinfeweriterationswhencomparedagainst
othercompeting methods[56]. Moreover, thereisan inexactALMvariant [177]to
theexactALMmethod[176],whichisabletoconvergeinevenfeweriterationsatthe
costofweakerguaranteedconvergencecriteria.MATLABcodethatimplementsthese
methods,alongwithafewotheralgorithms,canbedownloadedfromtheUniversity
[2].
of Illinois Perception and Decision Lab website This is the code implemented
throughoutthischapter.
| 4.2.1 | Video interpretation |     | of RPCA |     |     |     |
| ----- | -------------------- | --- | ------- | --- | --- | --- |
Inavideosequence, stationarybackground objectsappear ashighlycorrelated pixel
regions from one frame tothenext, which suggests alow-rank structure within the
videodata. Thesnapshotineachframeistwo-dimensionalbynature;pixelsneedto
bereshapedintoone-dimensionalcolumnvectorsandunitedintoasingledatamatrix
TheRPCAalgorithmcanthenimplementthebackground/fore-
X(seeFigure4.1).
groundseparationfoundinX=L+S,wherethelow-rankmatrixListhebackground
andthesparsematrixSisacomplementaryvideoofthemovingforegroundobjects.
Becausetheforegroundobjectsexhibitaspatialcoherencythroughoutthevideo,the

| 58  |     |     |     | Chapter4. | VideoProcessing |     |
| --- | --- | --- | --- | --------- | --------------- | --- |
RPCAmethodisnolongerguaranteedahighprobabilityofsuccess;however,inprac-
tice,RPCAachievesanacceptableseparationalmosteverytime[56].
Asλisdecreased,thesparsereconstructionofthevideoSstartstobringinmore
oftheoriginalvideo,includingerroneousstationarypixelsthatshouldbepartofthe
low-rank background. When λ is increased, the sparse reconstruction of the video
beginstoseeadecreaseinthepixelintensitiesthatcorrespondtothemovingobjects,
andsomeforegroundpixelsdisappearaltogether.
| 4.2.2 | RPCA interpretation | of  | DMD |     |     |     |
| ----- | ------------------- | --- | --- | --- | --- | --- |
TheDMDalgorithmcanbeusedtoproduceasimilarlow-rankandsparseseparation
asin (4.1). For theDMDcase, theseparation relieson theinterpretation ofthe ω
k
frequenciesinthesolution reconstructions represented in general by(1.5) andmore
specificallyinDMDby(1.24). Low-rankfeaturesinvideoaresuchthat|ω |≈0;that
j
istosay,theyareslowlychangingintime. Thus,ifonesetsathresholdtogatherall
thelow-rank modes where |ω | ≤ ε (cid:20) 1, then the separation can be accomplished.
j
ThisreproducesarepresentationoftheLandSmatricesoftheform
(cid:7)
|     |     |     | L≈  | φ exp(ω t), |     |     |
| --- | --- | --- | --- | ----------- | --- | --- |
b
|     |     |     |     | k k k |     |     |
| --- | --- | --- | --- | ----- | --- | --- |
|ω |≤ε
(cid:7)k
|     |     |     | S≈ b | φ exp(ω t). |     | (4.4) |
| --- | --- | --- | ---- | ----------- | --- | ----- |
|     |     |     |      | k k k       |     |       |
|ω |>ε
k
Notethatthelow-rankmatrixLpicksoutonlyasmallnumberofthetotalnumberof
DMDmodestorepresent theslowoscillationsordirectcurrent(DC)contentinthe
data(ω ≈0).
ThisDCcontentisexactlythebackgroundmodewheninterpretedin
j
thevideostreamcontext.
TheadvantageoftheDMDmethodanditssparse/low-rankseparationisthecom-
putationalefficiencyofachieving(4.4),especiallywhencomparedtotheoptimization
methodsthusfardeveloped. However,theDMDmethoddoesnotdowellfordelta
function–like behaviors in time, i.e., a very rapid on/off behavior. Such a behavior
would require many Fourier modes in time to resolve, undermining the method of
associatingcorrelatedspatialactivitywithsingleoscillatorybehaviorsintime.
| 4.3 | DMD for background |     | subtraction |     |     |     |
| --- | ------------------ | --- | ----------- | --- | --- | --- |
AvideosequenceoffersanaturalapplicationforDMDbecausetheframesofthevideo
areequallyspacedintime,andthepixeldatacollectedateverysnapshotcanreadilybe
vectorized. Givenavideowithmframes,then ×n =npixelsineachframecanbe
x y
n×1vectorsx
|     | extractedas | ,x  | ,...,x . | DMDcanattempttoreconstructanygiven |     |     |
| --- | ----------- | --- | -------- | ---------------------------------- | --- | --- |
|     |             | 1   | 2 m      |                                    |     |     |
framebycalculatingx (t)attimet. Thevalidityofthereconstructiondependson
DMD
howwellthespecificvideosequencemeetstheassumptionsandcriteriaoftheDMD
method.
Toreconstructtheentirevideo,considerthe1×mtimevectort=[t t ··· t ],
|     |     |     |     |     | 1 2 | m   |
| --- | --- | --- | --- | --- | --- | --- |
whichcontainsthetimesatwhichtheframeswerecollected. ThevideosequenceXis
reconstructedwithDMDasfollows:
(cid:7)r
|     |     | =   | φ   | ω t=Φdiag(exp(ωt))b. |     |       |
| --- | --- | --- | --- | -------------------- | --- | ----- |
|     |     | X   | b e | k                    |     | (4.5) |
|     |     | DMD | k k |                      |     |       |
k=1

4.3. DMDforbackgroundsubtraction 59
Noticethatφ isann×1vector,whichismultipliedbythe1×mvectorttoproduce
n×m k =
theproper video size. By theconstruction of theDMD methodology, x
1
Φb,whichmeansthatΨbrendersthefirstframeofthevideowithadimensionality
| reductionchosenthroughtheparameter |     | r.  |     |     |
| ---------------------------------- | --- | --- | --- | --- |
Thus,thediagonalmatrixoffrequenciesωdictateshowthatfirstframegetsaltered
overtimetoreconstructthesubsequentframes. Itbecomesapparentthatanyportion
ofthefirstvideoframethatdoesnotchangeintime,orchangesveryslowlyintime,
musthaveanassociatedFouriermode(ω )locatedneartheoriginincomplexspace:
k
(cid:7)ω (cid:7)≈
0. Thisobservation makesitpossible toseparate background (approximate
k
low-rank)informationfromforeground(approximatesparse)informationwithDMD.
Assumethatω p∈{1,2,...,r},satisfies(cid:7)ω (cid:7)≈0(typicallythisisonlya
,where
|     | p   |     | p   |     |
| --- | --- | --- | --- | --- |
singlemode)andthat(cid:7)ω (cid:7)∀k(cid:18)= pisboundedawayfromzero. Wemaynowrewrite
k
| (4.5)as |     |                                      | (cid:7)      |       |
| ------- | --- | ------------------------------------ | ------------ | ----- |
|         |     | ω                                    | ω            |       |
|         | X = | b φ e p t                            | + b φ e k t. | (4.6) |
|         | DMD | (cid:17)p (cid:18)p(cid:19) (cid:20) | j j          |       |
(cid:17)k(cid:18)=p
(cid:18)(cid:19) (cid:20)
BackgroundVideo
ForegroundVideo
∈ (cid:2)n×m,
Assumingthat X then aproper DMDreconstruction should also produce
X ∈(cid:2)n×m. However,eachtermoftheDMDreconstructionispotentiallycom-
DMD
| φ exp(ω | t) ∈ (cid:4)n×m | ∀k,           |                      |              |
| ------- | --------------- | ------------- | -------------------- | ------------ |
| plex, b |                 | although they | sum to a real-valued | matrix. This |
| k k k   |                 |               |                      |              |
poses a problem when separating the DMD terms into approximate low-rank and
sparse reconstructions, because real-valued outputs are desired for a video interpre-
tation,andproperhandlingofthecomplexelementscanmakeasignificantdifference
intheaccuracyoftheresults.
ConsidercalculatingDMD’sapproximatelow-rankreconstructionaccordingto
|     |     | XLow-Rank=b | φ ω t. |     |
| --- | --- | ----------- | ------ | --- |
e p
|     |     | DMD p | p   |     |
| --- | --- | ----- | --- | --- |
Sinceitshouldbetruethat
|     | X=XLow-Rank+XSparse, |     |     | (4.7) |
| --- | -------------------- | --- | --- | ----- |
DMD
DMD
thenDMD’sapproximatesparsereconstruction,
(cid:7)
|     |     | XSparse= | φ ω    |     |
| --- | --- | -------- | ------ | --- |
|     |     | b        | e k t, |     |
|     |     | DMD k    | k      |     |
k(cid:18)=p
canbecalculatedwithreal-valuedelementsonlyasfollows:
|     |     |     |     |     |
| --- | --- | --- | --- | --- |
|     |     |     |     |     |
XSparse=X− XLow-Rank ,
|     |     | DMD | DMD |     |
| --- | --- | --- | --- | --- |
where|·|yieldsthemodulusofeachelementwithinthematrix.
However,thismay
resultinXSparsehavingnegativevaluesinsomeofitselements,whichwouldnotmake
DMD
senseintermsofhavingnegativepixelintensities. Theseresidualnegativevaluescan
beputintoann×mmatrixRandthenaddedbackintoXLow-Rankasfollows:
DMD
|     |     |     |     |     |
| --- | --- | --- | --- | --- |
|     |     |     |     |     |
XLow-Rank←R+ XLow-Rank ,
|     | DMD |                    | DMD |     |
| --- | --- | ------------------ | --- | --- |
|     |     | Sparse←X Sparse−R. |     |     |
X
|     |     | DMD DMD |     |     |
| --- | --- | ------- | --- | --- |
Inthisway,themagnitudesofthecomplexvaluesfromtheDMDreconstructionare
accounted for, while maintaining the important constraints in (4.7) so that none of

| 60  |     |     |     |     |     | Chapter4. | VideoProcessing |
| --- | --- | --- | --- | --- | --- | --------- | --------------- |
thepixel intensitiesare belowzero andensuringthat theapproximate low-rank and
sparseDMDreconstructionsarerealvalued. Asdemonstratedinthenextsection,this
methodworkswellempirically.
| 4.4 | Simple | example | and | algorithm |     |     |     |
| --- | ------ | ------- | --- | --------- | --- | --- | --- |
Let usfirst considerasimpleexample ofone-dimensional dynamicsintime. Specif-
ically, wecan consider afunction comprisingatime-independent background mode
mixedwithadynamicaltime-varyingmode. OurobjectiveistouseDMDtoextract
thetwomodesduetotheirtime-independentandtime-dependentnature. Thespecific
modesconsideredare
|     |     | f(x,t)= |     | (x)+f (x,t) |     |     |     |
| --- | --- | ------- | --- | ----------- | --- | --- | --- |
f
|     |     |     | 1   | 2   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
=0.5cos(x)+2sech(x)tanh(x)exp(i2.8t),
(4.8)
|     |        | (x)istimeindependentand |     |     | (x,t)istimedependent. |     |                    |
| --- | ------ | ----------------------- | --- | --- | --------------------- | --- | ------------------ |
|     | wheref |                         |     |     | f                     |     | ThecodeinAlgorithm |
|     |        | 1                       |     |     | 2                     |     |                    |
4.1constructstheexampledata.
ALGORITHM4.1.Mixingoftwosignals.
|     | %% Define | time | and space | discretizations |     |     |     |
| --- | --------- | ---- | --------- | --------------- | --- | --- | --- |
n = 200;
m = 80;
x = linspace(-15,15,n);
t = linspace(0,8*pi,m);
|     | dt =       | t(2) - t(1);               |                |             |                       |     |     |
| --- | ---------- | -------------------------- | -------------- | ----------- | --------------------- | --- | --- |
|     | [Xgrid,T]  | = meshgrid(x,t);           |                |             |                       |     |     |
|     | %% Create  | two                        | spatiotemporal |             | patterns              |     |     |
|     | f1 =       | 0.5*cos(Xgrid)             |                | .* (1+0*T); | % time-independent!   |     |     |
|     | f2 =       | (sech(Xgrid).*tanh(Xgrid)) |                |             | .* (2*exp(1j*2.8*T)); |     |     |
|     | %% Combine | signals                    | and            | make        | data matrix           |     |     |
|     | X =        | (f1 + f2)’;                | % Data         | Matrix      |                       |     |     |
figure;
surfl(real(X’));
|     | shading | interp; | colormap(gray); |     | view(-20,60); |     |     |
| --- | ------- | ------- | --------------- | --- | ------------- | --- | --- |
TheDMDalgorithm followsthestandardstepsoutlinedintheintroduction. In
thisparticularcase(Algorithm4.2),wealsoperformarankr =50decompositionand
siftoutthezeroeigenvaluegeneratedbythebackgroundmode.
ALGORITHM4.2.DMDofsignals.
|     | %% Create | data | matrices | for | DMD |     |     |
| --- | --------- | ---- | -------- | --- | --- | --- | --- |
X1 = X(:,1:end-1);
X2 = X(:,2:end);
|     | %% SVD | and rank-50     | truncation |          |     |     |     |
| --- | ------ | --------------- | ---------- | -------- | --- | --- | --- |
|     | r =    | 50; % rank      | truncation |          |     |     |     |
|     | [U,    | S, V] = svd(X1, |            | ’econ’); |     |     |     |
|     | Ur =   | U(:, 1:r);      |            |          |     |     |     |

4.4. Simpleexampleandalgorithm 61
| Sr = S(1:r,       | 1:r);         |     |             |     |     |
| ----------------- | ------------- | --- | ----------- | --- | --- |
| Vr = V(:,         | 1:r);         |     |             |     |     |
| %% Build          | Atilde        | and | DMD Modes   |     |     |
| Atilde =          | Ur’*X2*Vr/Sr; |     |             |     |     |
| [W, D] =          | eig(Atilde);  |     |             |     |     |
| Phi = X2*Vr/Sr*W; |               |     | % DMD Modes |     |     |
%% DMD Spectra
| lambda = | diag(D);        |     |     |     |     |
| -------- | --------------- | --- | --- | --- | --- |
| omega =  | log(lambda)/dt; |     |     |     |     |
figure;
| plot(omega, | ’.’); |     |     |     |     |
| ----------- | ----- | --- | --- | --- | --- |
Theomegaeigenvaluesthatarenearlyzeroareconsideredbackgroundmodessince
theyhavenotimeevolution,i.e.,theyaretimeindependent. Thebackgroundmode
associatedwiththezerovalueomegaisthenusedtoconstructtheDMDbackground
mode(Algorithm4.3).
ALGORITHM4.3.Separateforegroundandbackground.
bg = find(abs(omega)<1e-2);
| fg = setdiff(1:r, |              | bg); |                  |     |       |
| ----------------- | ------------ | ---- | ---------------- | --- | ----- |
| omega_fg          | = omega(fg); |      | % foreground     |     |       |
| Phi_fg =          | Phi(:,fg);   |      | % DMD foreground |     | modes |
| omega_bg          | = omega(bg); |      | % background     |     |       |
| Phi_bg =          | Phi(:,bg);   |      | % DMD background |     | mode  |
TheforegroundandbackgroundDMDmodescanthenbeusedtoreconstructthe
DMDsolution. Inparticular,twosolutionsareachieved: aDMDreconstructionof
theforegroundvideoandaDMDreconstructionofthebackgroundvideo(ormode).
Thefollowingcodeconstructsthesetwoobjects.
ALGORITHM4.4.Foreground/background
reconstruction.
| %% Compute                    | DMD          | Foreground | Solution        |             |            |
| ----------------------------- | ------------ | ---------- | --------------- | ----------- | ---------- |
| b = Phi_bg                    | \            | X(:, 1);   |                 |             |            |
| X_bg = zeros(numel(omega_bg), |              |            |                 | length(t)); |            |
| for tt =                      | 1:length(t), |            |                 |             |            |
| X_bg(:,                       | tt)          | = b        | .* exp(omega_bg |             | .* t(tt)); |
end;
| X_bg = Phi_bg    |     | * X_bg; |     |     |     |
| ---------------- | --- | ------- | --- | --- | --- |
| X_bg = X_bg(1:n, |     | :);     |     |     |     |
figure;
surfl(real(X_bg’));
| shading    | interp; | colormap(gray); |          | view(-20,60); |     |
| ---------- | ------- | --------------- | -------- | ------------- | --- |
| %% Compute | DMD     | Background      | Solution |               |     |
| b = Phi_fg | \       | X(:, 1);        |          |               |     |

| 62  |        |     |       | Chapter4. | VideoProcessing |
| --- | ------ | --- | ----- | --------- | --------------- |
|     | f(x,t) |     | (x,t) |           | (x,t)           |
|     |        |     | f     |           | f               |
|     |        |     | 2     |           | 1               |
|     | x      | (t) | x (t) |           | x (t)           |
|     | DMD    |     | fg    |           | bg              |
t
x
ℑ{ω}
−−→
backgroundω
p
ℜ{ω}
Figure4.2.Foreground/backgroundseparationusingasimpleexample f(x,t)(topleft)
constructedfromtime-dependentdynamics f (x,t)andtime-independentmode f (x)(topmiddle
|     |     |     | 2   |     | 1   |
| --- | --- | --- | --- | --- | --- |
andtopright,respectively). TheDMDreconstructionforfulldynamicsismirroredinthemiddle
panels,withthefullreconstruction,foreground(time-dependent)behavior,andbackground(time-
independent)modegivenbyx (t),x (t),andx (t),respectively.TheDMDspectraldistribution
|     |     | DMD fg | bg  |     |     |
| --- | --- | ------ | --- | --- | --- |
ofeigenvaluesω isshowninthebottompanel,withthezeromodeω ≈10−15highlightedinred.
|      | j                        |     |             | p   |     |
| ---- | ------------------------ | --- | ----------- | --- | --- |
| X_fg | = zeros(numel(omega_fg), |     | length(t)); |     |     |
for tt = 1:length(t),
|     | X_fg(:, tt) | = b .* exp(omega_fg | .*  | t(tt)); |     |
| --- | ----------- | ------------------- | --- | ------- | --- |
end;
| X_fg | = Phi_fg    | * X_fg; |     |     |     |
| ---- | ----------- | ------- | --- | --- | --- |
| X_fg | = X_fg(1:n, | :);     |     |     |     |
figure;
surfl(real(X_fg’));
| shading | interp; | colormap(gray); | view(-20,60); |     |     |
| ------- | ------- | --------------- | ------------- | --- | --- |
The above codes rely on the same algorithm as in § 1.4. The only difference is
theseparationstepintheDMDeigenvalues. Onceseparated,reconstructionisdone
inthestandardwaywithtwodistinctreconstructionsbasedontheeigenvalues. Fig-
ure 4.2 shows the original example along with the DMD reconstruction and DMD
spectra. Specifically, the top panel of the figure shows the two initial signals, one
time-stationary (f (x)) and the other not (f (x,t)), along with the combined signal
|     |     | 1   | 2   |     |     |
| --- | --- | --- | --- | --- | --- |
f(x,t)= (x)+ (x,t). ThemiddlepanelshowsthefullDMDreconstructionx˜(t)
|     | f   | f   |     |     |     |
| --- | --- | --- | --- | --- | --- |
|     | 1   | 2   |     |     |     |
alongwiththeDMDreconstructionoftheforeground(time-dependent)objectx˜ (t)
2

4.5. DMDforvideosurveillance 63
andthebackground (time-independent)behavior x˜ (t). TheDMDspectraisshown
1
inthebottompanel,andthebackgroundeigenvalueω ≈10 −15isshowninred.
p
4.5 DMD for video surveillance
This framework easily generalizes to more complex video streams. Here we use
the open-source Advanced Video and Signal based Surveillance (AVSS) Datasets,
(www.eecs.qmul.ac.uk/∼andrea/avss2007_d.html),specificallythe“ParkedVehicle—
Hard”and“AbandonedBag—Hard”videos. TheDMDseparation procedurecanbe
comparedandcontrastedagainsttheRPCAprocedure. Theoriginalvideoswerecon-
vertedtograyscaleanddown-sampledinpixelresolutionton=120×96=11520to
makethecomputationalmemoryrequirementsmanageableforpersonal computers.
Also,theintroductorypreamblestothesurveillancevideos,whichconstitutethefirst
351framesofeachvideo,wereremovedbecausetheyareirrelevantforthefollowing
illustrations.
Thevideostreamsarebroken intosegmentsof m =30frameseach, whichwere
analyzedindividuallyusingboththeRPCAandtheDMDmethods. Framenumbers
500, 1000, and 2000 of the entire video stream are depicted in Figures 4.3 and 4.4,
alongwiththeirseparationresultsforeasycomparison. Althoughonehastheoption
ofmanuallytuningtheregularizationparametero(cid:9)ftheRPCAmethodtobestsuitthe
givenapplication,forconsistencyλissetatλ=( n)−1≈9.32·10 −3,asissuggested
byCandèsetal.[56]forcreatingareliableautomaticalgorithm. Likewise,thedimen-
sionalityreductionparameteroftheDMDmethodisheldconstantatr =m−1=29.
Forenhancedcontrastandbettervisibility,thesparseresultsfrombothmethodsare
artificiallybrightenedbyafactorof10.
ConsiderFigure4.3oftheAVSS“ParkedVehicle”surveillancevideo,whichshows
variousvehiclestravelingalongaroad,withatrafficlight(notvisible)andacrosswalk
(visible)nearthebottomoftheframe. Thereareafewvehiclesparkedalongsidethe
road. Sometimes,inthedistance,movingvehiclesbecomedifficulttoperceivebyeye
due to limitations of the pixel resolution. Note that some extraneous pixels in the
sparsestructurecanbeeliminatedbyapplyingasimplethresholdingcriterionbased
onpixelintensity.
Next, let’sconsiderFigure4.4oftheAVSS“AbandonedBag”surveillance video,
which consists of people walking, standing, and sitting as trains come and go in a
subwaystation. Shadowsarerelevantinthisvideobecause theymovewiththeirre-
spectiveforegroundobjects,andtheysometimeschangethebackgroundsignificantly
enough tobeviewedasextensions ofthemovingobjects themselves. Notethat,for
frames500and1000,bothmethodsstrugglewiththefactthatbetweenthenumerous
movingobjectsandtheirshadows,manyofthepixelsinthevideochangeintensityat
somepoint. Observe thatobjectsinmotioncreatemovementtrailsthatextrapolate
theobject’smotionbothforwardandbackwardintime. Whentheobjectisdark,its
correspondingmovementtrailisbright,andviceversa.
4.5.1 Timing Performance
TheRPCAandDMDmethodshavecomparablygoodbackground/foregroundsepa-
rationresults. Thedifferenceintheseparationqualityseemstodependonthespecific
situation,likelybecausetheassumptionsthatdeterminewhentheRPCAandDMD
methodswillperform wellarealsodifferent. Giventherelativelyconsistentquality
oftheseparationresults,otherfactors,suchascomputationaleffort,becomethedis-

64 Chapter4. VideoProcessing
Figure4.3.TheDMDbackground/foregroundseparationresultsareillustratedforthree
specificframesinthe“ParkedVehicle”video. The30-framevideosegmentthatcontainsframe500
hasthreevehiclesdrivinginthesamelane toward thecamera. The30-framevideosegmentthat
containsframe1000hasamansteppinguptoacrosswalkasavehiclepassesby,andasecondcarin
thedistance,barelyperceptible,startstocomeintoview. The30-framevideosegmentthatcontains
frame2000hasthreevehiclesstoppedatatrafficlightatthebottomoftheframe,withanothertwo
vehiclesparkedontherightsideoftheroad,andfivemovingvehicles,twogoingintothedistance
andthreecomingtowardthevehicleswaitingatthelight,thelastvehiclebeingimperceptibletothe
eyeatthispixelresolution: n=11520.
tinguishingcharacteristicsthatdeterminewhichmethodismoresuitableforthegiven
application.
The key difference in effectiveness between the RPCA and DMD algorithms is
foundincomputationaltimeneededtocompletethebackground/foregroundsepara-
tion.Again,considertheAVSSDatasets,withthetwovideosusedpreviously: “Parked
Vehicle”and“AbandonedBag.” Foratimingperformanceexperiment,considerhav-
ingthesevideosdown-sampledtovariouspixel resolutions n andseparated intovar-
ious video segment sizes m. Figure 4.5 shows the computational time required for
RPCAandDMDaveragedoverbothvideos,fixingeithernumberofpixelsorvideo
segmentsizes. BoththeexactALMandthefasterinexactALMconvexoptimization
routineswereusedtosolvethePCPproblem(4.2)oftheRPCAmethod.
InFigure4.5,theempiricalcomputationaltimesareplottedonalogarithmicscale,

4.5. DMDforvideosurveillance 65
Figure4.4.TheDMDbackground/foregroundseparationresultsareillustratedforthree
specificframesinthe“AbandonedBag”video. The30-framevideosegmentthatcontainsframe500
hasthreepeoplesteppingslightlyclosertoanarrivingtrain,andanotherpersonwalkingbehinda
supportpillartowardthetrainintheupperrightareaoftheframe. Thetwopeopleclosesttothe
camerawalktowardthebottomoftheframe.The30-framevideosegmentthatcontainsframe1000
hasfourpeoplewalkingindifferentdirectionsinthemiddleoftheframe,oneofwhomcomesout
frombehindasupportpillar,while,fartherdowntheplatform,twopeopleenterthetrain. The30-
framevideosegmentthatcontainsframe2000hasawomanwalkoutfrombehindasupportpillar,
movetotheleft,andthenturnsomewhattowardthecamera. Thetrainismovingandtheman
sittingclosesttothesupportpillaradjustshisbackpack.
along with best-fit curves found by the linear least-squares method. It is clear that
the DMD method is about two to three orders of magnitude faster than its RPCA
methodcounterpartusingtheexactALMoptimizationprocedureandaboutoneor-
derofmagnitudefasterwhentheinexactALMoptimizationprocedureisemployed.
Infact,manycamerasoperateatarateofabout20to30framespersecond,andDMD
canbecomputedforthosevideosegmentsinabout0.1–0.01secondsforhigh-andlow-
resolutionimages,respectively. Thisefficiencymakesreal-time,onlinedataprocessing
possible,evenwithoutdown-sampling.

66 Chapter4. VideoProcessing
Figure4.5.DMDisfasterthanRPCAatforeground/backgroundseparationbyordersof
magnitude. Forthe“AbandonedBag”and“ParkedVehicle”videos,thecomputationaltimesofthe
DMD(greenandyellow,respectively),inexactALMRPCA(redandmagenta,respectively),andexact
ALMRPCA(blueandcyan,respectively)background/foregroundseparationmethodsaregraphed
onalogarithmicscale. Thenumberofpixelsperframeisfixedat{2880,6480},respectively. This
timingdatafitsreasonablywellwithaquadraticfit: t =cs2,where t isthecomputationaltime,
c∈(cid:2),andsisthevideosegmentsize(numberofframespervideosegment).Timingwasassessedon
a1.86GHzIntelCore2DuoprocessorusingMATLAB.
Original (cid:2)=1 (cid:2)=10
Figure4.6. Theeffectsoftheparameter r thatcontrolsthedimensionalityreductionof
theDMDprocessaredepicted.Theoriginalframe,andtheDMDsparsereconstructionsofthatframe
forr=1andr =10,artificiallybrightenedby10timesthetrueintensity,areillustratedforframe
2000ofthe“ParkedVehicle”video[1]usinga30-framevideosegment(seeFigure4.3).Noticethatthe
sparsityincreaseswiththeparameter r becausedimensionalityreductionhastheeffectofblurring
themotionbetweenframes,thussmearingthemotionoutoveragreaternumberofpixelsinany
givenframe.Evenundersignificantdimensionalityreduction(r=1),thebackground/foreground
separationisstillaccomplishedreasonablywell. By r =10,themethodapproximatesthefull-rank
reconstruction(r=29).
4.5.2 DMD and rank truncation
AsdiscussedindetailinChapter8,oneparameterintheDMDalgorithmisr,therank
truncationthatdecreasesthedimensionalityofthedecomposition. Toshowtheeffect
thatthedimensionalityreduction parameter r hason theDMD separation process,
considertheforegroundDMDresultsrepresentedinFigure4.6.
Thesurprisingresulthereisthequalityofthelow-rankandsparseseparationeven
whenr issetaslowas1.Ranktruncationseemstohavetheeffectofblurringthevideo
framestogether. Itispossiblethattheresultsof r =1areinpartbecausethevehicles

4.5. DMDforvideosurveillance 67
(cid:1)(cid:27)(cid:28)(cid:1)(cid:13)(cid:18)(cid:9)(cid:21)(cid:4)
(cid:1)(cid:30)(cid:29)(cid:1)(cid:13)(cid:18)(cid:9)(cid:21)(cid:4)
(cid:1)(cid:29)(cid:27)(cid:26)(cid:1)(cid:13)(cid:18)(cid:9)(cid:21)(cid:4)
(cid:6)(cid:21)(cid:15)(cid:14)(cid:15)(cid:19)(cid:9)(cid:17)(cid:1)(cid:8)(cid:15)(cid:12)(cid:13)(cid:20)(cid:1) (cid:8)(cid:15)(cid:12)(cid:13)(cid:20)(cid:1)(cid:7)(cid:13)(cid:14)(cid:18)(cid:13)(cid:19)(cid:22)(cid:1) (cid:8)(cid:15)(cid:12)(cid:13)(cid:20)(cid:1)(cid:7)(cid:13)(cid:14)(cid:18)(cid:13)(cid:19)(cid:22)(cid:1) (cid:8)(cid:15)(cid:12)(cid:13)(cid:20)(cid:1)(cid:7)(cid:13)(cid:14)(cid:18)(cid:13)(cid:19)(cid:22)(cid:1) (cid:2)(cid:9)(cid:11)(cid:16)(cid:14)(cid:21)(cid:20)(cid:23)(cid:19)(cid:12)(cid:1)
(cid:7)(cid:15)(cid:24)(cid:13)(cid:1)(cid:32)(cid:1)(cid:26)(cid:25)(cid:1) (cid:7)(cid:15)(cid:24)(cid:13)(cid:1)(cid:32)(cid:1)(cid:27)(cid:25)(cid:1) (cid:7)(cid:15)(cid:24)(cid:13)(cid:1)(cid:32)(cid:1)(cid:26)(cid:25)(cid:25)(cid:1)
(cid:6)(cid:21)(cid:15)(cid:14)(cid:15)(cid:19)(cid:9)(cid:17)(cid:1)(cid:4)(cid:21)(cid:9)(cid:18)(cid:13)(cid:1)(cid:32)(cid:1)(cid:3)(cid:5)(cid:3)(cid:1)(cid:7)(cid:23)(cid:10)(cid:22)(cid:21)(cid:9)(cid:11)(cid:22)(cid:13)(cid:12)(cid:1)(cid:31)(cid:1)(cid:2)(cid:9)(cid:11)(cid:16)(cid:14)(cid:21)(cid:20)(cid:23)(cid:19)(cid:12)(cid:1)
(cid:4)(cid:21)(cid:9)(cid:18)(cid:13)(cid:1)(cid:28)(cid:27)(cid:1)
(cid:4)(cid:21)(cid:9)(cid:18)(cid:13)(cid:1)(cid:29)(cid:30)(cid:1)
(cid:4)(cid:21)(cid:9)(cid:18)(cid:13)(cid:1)(cid:26)(cid:27)(cid:29)(cid:1)
Figure4.7.AnalysisoftheDMDbackground/foregroundseparationwithrandomback-
groundnoise. Theleftcolumnshowstheoriginalframeswiththerandombackgroundnoise. The
middlethreecolumnsshowthesparseDMDresultsusing10,30,and100framespervideosegment,
whichareartificiallybrightenedbyafactorof10toincreasethecontrastandvisibilityoftheresults
againstablackbackground,andtherightcolumnshowsthetruebackgroundnoisethatwasadded
toeachframe.Theerroneouspixelscontributetothemeanpixelintensityerrorofthebackground.
inthevideoofFigure4.6didnotmoveveryfarwithintheframe,sothesmearingof
pixelsovertheplacesofmovementisvery localized. Thisdimensionalityreduction
constitutes a time-saving procedure that can potentially reduce the video separation
costsevenfurther.
4.5.3 Error analysis
ToaccuratelymeasurehowwelltheDMDmethodcapturesactualforegroundmove-
ment, and not the stationary background, it is helpful to have an artificially con-
structedvideowherethetruebackgroundandforegroundareknown.Theerrorcould
thenbemeasuredpreciselybetweentheactualandDMD-reconstructedbackgrounds.
Moreover, thequalityofreconstruction can alsobecompared withtheRPCA tech-
nique.
OnesuchvideowasconstructedtocalculatetheerrorintheDMDlow-rank/sparse
separation method with 300frames in total, each being 100×100 pixels. Theback-
groundtothevideoisproducedbyauniformrandomgrayscale-intensityfield,rang-
ingfrompureblacktopurewhite. Thebackgroundremainsconstantthroughoutthe
entirevideo.
Thisvideocontainsthreemovingobjects: (1)ablacksquare, 7×7pixelsinsize,
withfourwhitepixelsineachcornerandawhite“plus”signcenteredinthemiddle;
(2)alightgraycirclewithadiameterof9pixels;and(3)atransparentsquare,13×13
pixelsinsize,linedbyblackpixelsandwithablack“X”centeredwithin. Object(1)
revolves,ataconstantrateof4pixelsperframe,counterclockwisearoundtheinside

68 Chapter4. VideoProcessing
x 10−3
5
4.5
4
3.5
3
2.5
2
1.5
1
0.5
0
10 20 30 40 50 60 70 80 90 100
Number of Frames Per Video Segment
ssenthgirB
lexiP
dnuorgkcaB
dezilamroN
naeM
Mean Background Errors
DMD Method Error
RPCA Method Error
16
14
12
10
8
6
4
2
0
10 20 30 40 50 60 70 80 90 100
Number of Frames Per Video Segment
]ces[
emiT
Mean DMD Computational Times
DMD Computation Times
RPCA Computation Times
Best−Fit to DMD Computation Times
Figure4.8. AnalysisoftheDMDbackground/foregroundseparationerror. Themean
pixelintensityerrorfortheentirevideoateachvideosegmentsizeisplottedinthetopfigureona
normalizedintensityscalewhere1ispurewhiteand0ispureblack,thetargetbackgroundcolor.
Themeancomputational times t,usingMATLAB ona1.86GHzIntelCore2Duoprocessor, as
afunctionofthevideosegmentsizess isplottedinthebottomfigure,yieldingaquadraticbest-fit:
t=1.52·10−4s2,R2=0.983.
edgesoftheframestartingatthetopleftcorneroftheframefortheentireduration
of the video. Object (2) enters the video on frame 25 on the left side of the frame,
movingupandtotheleftataconstantrateof2pixelsperframeinbothdirections.
Thisobject reflectsdownwardand eventuallyleaves theframe afterbouncingoff an
imaginarywalllocatedafifthofthewaydownfromthetopoftheframe. Object(3)
entersthevideoonframe50ontherightsideoftheframe,movingdownandtothe
left.Oncethisobjectenterstheframe,itstaysinsidetheframefortherestofthevideo,
reflectingofftheedgesoftheframe. Object(3)maintainsaconstantverticalvelocity
of1pixelperframeandahorizontalvelocityof6pixelsperframe. Atvarioustimes

4.5. DMDforvideosurveillance 69
theseobjectsoverlaponeanother,andtheprecedenceisthatobject(1)isdrawnfirst,
thenobject(2),thenobject(3),buryingthepreviouslydrawnobjectsunderthenewly
drawnobject.
TheforegroundresultsoftheDMDmethodappliedtothisvideoareillustratedin
Figure4.7forframenumbers53,79,and137. Notethatobject(3)cannotbeseenin
theresultsbecauseitispureblack. ThisexemplifiesalimitationtotheDMDmethod,
inthatwhenthereisanobjectoflowpixelintensity,itmaybedifficulttodistinguish
itfromthezeroentriesthatnaturallyoccurinasparsematrix. Notethatthespurious
pixelsarebothresidualsofpreviousframesandprojectionsofwheretheobjectswill
bemovinginfutureframes,andhaveinvertedpixelintensitiescomparedtotheircor-
respondingobjects’intensities.ThisismuchlikewhatisseenintheforegroundDMD
resultsofframes1000and2000ofthe“AbandonedBag”videoinFigure4.4,wherethe
walkingman(frame1000)andwalkingwoman(frame2000)haveobvious,erroneous
movementtrails.
Themean,normalizedpixelintensityerrorforthisconstructedvideoisshownin
Figure4.8. Thiserroriscalculatedonthefirstm−1framesofthevideosegmentsof
length m because thelastframeiswheretheDMDprocedureaccumulates itserror.
Note that the background to the sparse DMD-reconstructed videos should be pure
black,andonanintensityscaleof0to1,theaveragesparsebackgroundpixelintensity
isontheorderof10
−3,comparedtothetrueaveragebackgroundintensityofnearly
identically0.5. Recallthat,insomecases,thresholdingtechniquescaneliminatespu-
riousbackgroundpixelsfromtheforegroundresultsandimprovethemeasurederror.
OnemighthaveexpectedthattheDMDalgorithmerrorswouldhavedecreasedas
thevideosegmentsizesincreased,becausehavingmoreframesmeansthattheDMD
methodhasmoreinformationtoworkwith. However,becauseofthisanomalywith
blackobjectsleavingwhitemovementtrails,thereareextraneouspixelsforeveryvideo
segmentsize. Asthevideosgetlonger,theseerroneousmovementtrailsalsogetlonger,
projecting intoboth the past and the future, increasing the amount of error in pro-
portiontotheincreaseinnumberofframespervideosegment. However,thelonger
videosdoproduceless-brightpixelintensitytrails,whichhelpsreducetheerror,which
isconsistentwiththeideathattheyshouldbeabletomakemoreuseoftheextrain-
formationthattheyhave.
TheRPCA-reconstructedf(cid:9)oregrounderrorresultsarealsopresentedforcompari-
son,wherethesuggestedλ=( n)−1=0.01isused. Inthiscase,theRPCAperfectly
reconstructseveryvideoforsegmentsizesgreaterthan10frames.
Figure4.8 confirmsthequadraticgrowth incomputational timesthattheDMD
andRPCAschemesexperienceasthevideosegmentsizesareincreased. Thisquadratic
growthtrailsoffslightlyforverysmallsegmentsizes,likelyduetoinherentprocessing
times that do not scale with data size. For segment size 10, there is, of course, the
optionofretuningtheregularizationparameterλinRPCA.However,inmostcases
wherethetruesolutionisunknown,thismustbedonemanuallybytime-consuming
rerunsoftheRPCAalgorithm.
Finally,itshouldbenotedthatasobjectsizeincreasesrelativetotheframesize,the
DMDreconstructionerroralsoincreases. Likewise,andnotsurprisingly, theDMD
reconstructionerrorincreasesiffewerframesareusedtoshowthesameobjectmove-
ment. NotalltypesofobjectmovementareaccuratelyreconstructedwiththeDMD
method;however,itseemsthathighspeedsandaccelerationcanstillbehandledfairly
wellgivenenoughsnapshotstocapturethemovement.Objectsthatwereoncemoving
andthenstopareeventsthatarenotwellreconstructedbytheDMDmethod.

70 Chapter4. VideoProcessing
4.5.4 Iterativeapplication of DMD
OneoftheadvantagesoftheRPCAmethodthatisillustratedintheprecedingsubsec-
tionisthatitcanperformexactlow-rankandsparsedecompositions;thustheerrorcan
bereducedtozero. NosuchguaranteesareavailablefortheDMDalgorithm. How-
ever, we highlight an interesting observation concerning the iterative use of DMD.
GrosekandKutz[121]demonstratedhowtheDMDmethodcanbeappliediteratively
toempiricallyconvergetowardthetruelow-rankandsparsecomponentsofthegiven
data. ThesuccessiveDMDiterationsareappliedtotheapproximatesparsestructure,
creatingabetterapproximatesparsestructureandaddingmoredatabackintothelow-
rankstructure. Inthefuture,findingtheexactrateofconvergenceandunderstanding
thetheoreticalbasisforthisconvergencewillbeimportantstepstowardestablishingan
analyticalconnectionbetweentheRPCAandDMDseparationalgorithms. Theper-
formanceofDMDforvideobackgroundsubtractionmayalsobenefitfromstreaming
DMDalgorithms[130].

Chapter 5
Multiresolution Dynamic
Mode Decomposition
Modeling of multiscale systems, in both space and time, pervades modern develop-
mentsintheoryandcomputationacrosstheengineering,biological,andphysicalsci-
ences.Asignificantchallengeismakingeffectiveandefficientconnectionsbetweenmi-
croscaleandmacroscaleeffects,especiallyastheyarepotentiallyseparated byorders
of magnitude in space and time. Wavelet-based methods and/or windowed Fourier
transforms areideally structured toperform such multiresolution analyses(MRAs),
as they systematically remove temporal or spatial features by a process of recursive
refinementofsamplingfromthedata[166,76,78]. Typically,MRAisperformedin
either space or time, but not both simultaneously. In this chapter, we integrate the
conceptofMRAintimewithDMD[167]. ThismultiresolutionDMD(mrDMD)is
showntonaturallyseparatemultiscalespatiotemporalfeatures,providinganeffective
meanstouncovermultiscalestructuresinthedata.
5.1 Time-frequency analysis and the Gábor transform
The Fourier transform is one of the most important and foundational methods for
theanalysisoftime-seriessignals. However,itwasrealizedquiteearlyonthatFourier
transform–based methodshaveseverelimitations. Specifically, whentransforminga
giventimesignal,theentirefrequencycontentofthesignalcanbecapturedwiththe
transform,butthetransformfailstocapturethemomentintimewhenvariousfrequen-
ciesareactuallyexhibited. Indeed,bydefinition,theFouriertransformeliminatesall
time-domaininformationbyintegratingoveralltime.
ThelimitationsofthedirectapplicationoftheFouriertransform,anditsinability
tolocalizeasignalinboththetimeandthefrequencydomains,werearticulatedinthe
earlydevelopmentofradarandsonardetection. TheHungarianphysicist/mathemati-
cian/electricalengineerGáborDénes(PhysicsNobelPrizein1971forthediscoveryof
holographyin1947)wasthefirsttoproposeaformalmethodforlocalizingbothtime
andfrequency. HismethodinvolvedasimplemodificationoftheFouriertransform
kernel. Gáborintroducedthekernel
g (τ)=eiωτ g(τ−t), (5.1)
t,ω
wherethenew term tothe Fourierkernel g(τ−t)was introduced with theaim of
localizing both time and frequency. The Gábor transform, also known as the short-
71

72 Chapter5. MultiresolutionDMD
|)t(S|
a
(cid:111)
Time (t)
Figure5.1.GraphicaldepictionoftheGábortransformforextractingthetime-frequency
contentofasignalS(t).Thetime-filteringwindow g(τ−t)iscenteredatτwithwidtha.
timeFouriertransform(STFT)isthendefinedas
(cid:30)
∞ ! "
(cid:30)[f](t,ω)= f ˜(t,ω)= f(τ)g¯(τ−t)e −iωτ dτ= f,g¯ , (5.2)
g t,ω
−∞
where the bar denotes the complex conjugate of the function. Thus, the function
g(τ−t)actsasatimefilterforlocalizingthesignal overaspecificwindowoftime.
Theintegration over theparameter τ slides thetime-filteringwindowdown theen-
tiresignal,pickingoutthefrequencyinformationateachinstantoftime. Figure5.1
illustratestheGábortime-filteringscheme. Inthisfigure,thetime-filteringwindowis
centeredatτ withwidtha. Thus,thefrequencycontentofawindowoftimeisex-
tractedandτismodifiedtoextractthefrequenciesofanotherwindow.Thedefinition
oftheGábortransformcapturestheentiretime-frequencycontentofthesignal; the
Gábortransformisafunctionofthetwovariables t andω.
Although theGábor transformgivesamethod wherebytimeandfrequencycan
besimultaneouslycharacterized,thereareobviouslimitationstothemethod. Specif-
ically, themethod islimited by thetimefilteringitself. Consider the illustration of
themethodinFigure5.1. Thetimewindowfiltersoutthetimebehaviorofthesignal
inawindowcenteredatτ withwidtha. Itfollowsthat,whenconsideringthespec-
tralcontentofthiswindow,anyportionofthesignalwithawavelengthlongerthan
thewindowiscompletelylost. Indeed,sincetheHeisenberguncertaintyrelationship
must hold, the shorter the time-filtering window, the less information there is con-
cerning the frequency content. In contrast, longer windows retain more frequency
components,butthiscomesattheexpenseoflosingthetimeresolutionofthesignal.
Asaconsequence ofafixed time-filteringwindow,therearetrade-offsbetweentime
andfrequencyresolution;increasedaccuracyinoneoftheseparameterscomesatthe
expenseofresolutionintheotherparameter.
5.2 Wavelets and MRA
TheGábortransformestablishedtwokeyprinciplesfortime-frequencyanalysis: trans-
lationofashort-timewindowandscalingoftheshort-timewindowtocapturefiner

5.2. WaveletsandMRA 73
| (cid:8) |     | (cid:9) |     |     |
| ------- | --- | ------- | --- | --- |
(cid:3)(cid:1)(cid:115)(cid:1)(cid:2)(cid:16)(cid:15)(cid:15)
(cid:7)(cid:5)(cid:12) (cid:2)(cid:17)(cid:3)
(cid:2)(cid:18)(cid:3)
| (cid:115) |     | (cid:8) |     |     |
| --------- | --- | ------- | --- | --- |
(cid:7)
| (cid:239)(cid:7)(cid:5)(cid:12) |     | (cid:7) |     |     |
| ------------------------------- | --- | ------- | --- | --- |
(cid:239)(cid:13) (cid:239)(cid:10) (cid:7) (cid:10) (cid:13) (cid:239)(cid:8)(cid:7) (cid:239)(cid:12) (cid:7) (cid:12) (cid:8)(cid:7)
|     | T(cid:22)(cid:23)(cid:20)(cid:1)(cid:2)(cid:27)(cid:3) |     | F(cid:26)(cid:20)(cid:25)(cid:28)(cid:20)(cid:24)(cid:19)(cid:29)(cid:1)(cid:2)(cid:116)(cid:3) |     |
| --- | ------------------------------------------------------ | --- | ----------------------------------------------------------------------------------------------- | --- |
(cid:9)
|                                | (cid:115)                                      | (cid:115)             |     | (cid:115)                             |
| ------------------------------ | ---------------------------------------------- | --------------------- | --- | ------------------------------------- |
| (cid:8) (cid:2)(cid:19)(cid:3) | (cid:10)(cid:6)(cid:9)(cid:4)(cid:239)(cid:10) | (cid:8)(cid:4)(cid:7) |     | (cid:8)(cid:6)(cid:11)(cid:4)(cid:13) |
(cid:7)
(cid:239)(cid:8)
| (cid:239)(cid:14) | (cid:239)(cid:11) | (cid:7) | (cid:11) | (cid:14) |
| ----------------- | ----------------- | ------- | -------- | -------- |
T(cid:22)(cid:23)(cid:20)(cid:1)(cid:2)(cid:27)(cid:3)
Figure5.2.IllustrationoftheMexicanhatwaveletψ (topleftpanel),itsFouriertrans-
1,0
formψˆ
(toprightpanel),andtwoadditionaldilationsandtranslationsofthebasicψ wavelet,
| 1,0             |                |     |     | 1,0 |
| --------------- | -------------- | --- | --- | --- |
| namelytheψ andψ | (bottompanel). |     |     |     |
| 3/2,−3          | 1/4,6          |     |     |     |
timeresolution. AsimplemodificationtotheGábormethod istoallowthescaling
window(a)tovaryandsuccessivelyextractimprovementsinthetimeresolution.
In
otherwords,firstthelow-frequency(poortimeresolution)componentsareextracted
usingabroad scalingwindow. Thescalingwindowissubsequentlyshortened toex-
tracthigherfrequenciesatbettertimeresolution.Bykeepingacatalogoftheextracting
process, excellent resolution inbothtimeandfrequencyofagiven signalcanbeob-
tained. Thisprincipleisfundamentaltowavelettheory. Thetermwaveletmeanslittle
waveandoriginatesfromtheprocesseswherebythescalingwindowextractssmaller
andsmallerpiecesofwavesfromthelargersignal.
Waveletanalysisbeginswiththeconsiderationofafunctionknownasthemother
wavelet: # $
1 t−b
|     | ψ (t)= (cid:9) | ψ   |     |     |
| --- | -------------- | --- | --- | --- |
, (5.3)
|     | a,b | a a |     |     |
| --- | --- | --- | --- | --- |
wherea(cid:18)=0andb arerealconstants. Theeffectofthesetwoparametersontheshape
ofthewavelet isillustrated inFigure5.2; thea parameter controlsscalingand b de-
τ
notes translation (previously denoted by in Figure 5.1). Unlike Fourier analysis,
andverymuch likeGábortransforms,avastvarietyofmotherwaveletscanbecon-
structed. Inprinciple,themotherwaveletisdesignedtohavecertainpropertiesthat
aresomehowbeneficialforagivenproblem. Dependingontheapplication,different
motherwaveletsmaybeselected. Ultimately,thewaveletissimplyanotherexpansion
basis for representing a given signal or function. Historically, the first wavelet was
constructed by Haar in 1910[124], so the concepts and ideas of wavelets are over a

| 74  |     |     |     |     |     | Chapter5. | MultiresolutionDMD |     |
| --- | --- | --- | --- | --- | --- | --------- | ------------------ | --- |
centuryold. However,theirusewasnotwidespreaduntilthemid-1980s.
Thewaveletbasiscanbeaccessedviaanintegraltransformoftheform
(cid:30)
|     |     |     | (Tf)(ω)= | K(t,ω)f(t)dt, |     |     |     |     |
| --- | --- | --- | -------- | ------------- | --- | --- | --- | --- |
(5.4)
t
where K(t,ω) is the kernel of the transform. This is equivalent in principle to
K(t,ω) =
theFourier transform, whose kernel consists of theoscillations given by
exp(−iωt). Thekeyideanowistodefineatransformthatincorporates themother
waveletasthekernel. Wemaydefinethecontinuouswavelettransform(CWT):
(cid:30)
∞
|     |     | (cid:31) [f](a,b)=(f,ψ |     | )=  |     | f(t)ψ¯ | (t)dt. | (5.5) |
| --- | --- | ---------------------- | --- | --- | --- | ------ | ------ | ----- |
|     |     | ψ                      |     | a,b |     | a,b    |        |       |
−∞
Much like the windowed Fourier transform, the CWT is a function of the dilation
parameteraandtranslationparameterb. Parenthetically,awaveletisadmissibleifthe
followingpropertyholds:
(cid:30)
|     |     |     |     | ∞ |ψˆ(ω)|2 |       |     |     |       |
| --- | --- | --- | --- | ---------- | ----- | --- | --- | ----- |
|     |     |     | C = |            | dω<∞, |     |     | (5.6) |
|     |     |     | ψ   | |ω|        |       |     |     |       |
−∞
wheretheFouriertransformofthewaveletisdefinedby
|     |     |            | (cid:30) | #   | $   |              |             |       |
| --- | --- | ---------- | -------- | --- | --- | ------------ | ----------- | ----- |
|     |     |            | ∞        | t−b |     |              |             |       |
|     | ψˆ  | 1          | −iωtψ    |     |     | 1            | −ibωψˆ(aω). |       |
|     |     | = (cid:31) | e        |     | dt  | = (cid:31) e |             | (5.7) |
|     |     | a,b |a|    |          |     |     | |a|          |             |       |
|     |     |            | −∞       | a   |     |              |             |       |
Thus,providedtheadmissibilitycondition(5.6)issatisfied,thewavelettransformcan
bewelldefined.
In the wavelet transform, the signal is first split up into a collection of smaller
signalsbytranslatingthewavelet withtheparameter b overtheentiretimedomain
of the signal. Second, the same signal is processed at different frequency bands, or
resolutions, by scalingthewavelet windowwiththeparameter a. Thecombination
of translation and scaling allows for processing of the signals at different times and
frequencies. Figure5.3isaschematicthatillustratestheGáborandwavelettransform
conceptsinthetime-frequencydomain.Inthisfigure,thestandardtimeseries,Fourier
transform,andwindowedFouriertransformarerepresentedalongwiththemultireso-
lutionconceptofthewavelettransform. Inparticular,theboxillustratingthewavelet
transformshowsthemultiresolutionconceptinaction. StartingwithalargeFourier
domainwindow,theentirefrequencycontentisextracted. Thetimewindowisthen
scaledinhalf,leadingtofinertimeresolutionattheexpenseofworsefrequencyreso-
lution.Thisprocessiscontinueduntiladesiredtime-frequencyresolutionisobtained.
Thissimplefigureiscriticalforunderstandingwaveletapplicationtotime-frequency
analysis.
As an example, consider one of the more common wavelets: the Mexican hat
wavelet (Figure 5.2). This wavelet is essentially a second moment of a Gaussian in
thefrequencydomain. Thedefinitionsofthiswaveletanditstransformareasfollows:
|     |     |     |     |     |     | (cid:4) (cid:5) |     |     |
| --- | --- | --- | --- | --- | --- | --------------- | --- | --- |
d2
|     |     | ψ(t)=(1−t2)e |     | −t2/2=− |     | −t2/2 | =ψ  |        |
| --- | --- | ------------ | --- | ------- | --- | ----- | --- | ------ |
|     |     |              |     |         |     | e     | ,   | (5.8a) |
|     |     |              |     |         | dt2 |       | 1,0 |        |
(cid:9)
|     |     | ψˆ(ω)=ψˆ |     |      |       | −ω2/2. |     |        |
| --- | --- | -------- | --- | ---- | ----- | ------ | --- | ------ |
|     |     |          |     | (ω)= | 2πω2e |        |     | (5.8b) |
1,0

5.3. FormulatingmrDMD 75
time (t)
)(cid:116)(
ycneuqerf
time (t)
)(cid:116)(
ycneuqerf
time (t)
)(cid:116)(
ycneuqerf
time (t)
)(cid:116)(
ycneuqerf
TimeSeries Fourier
Gábor Wavelet
Figure5.3.Graphicaldepictionofthedifferencebetweenthetime-seriesanalysis,Fourier
analysis,Gáboranalysis,andwaveletanalysisofasignal.Thewavelettransformstartswithalarge
Fourierdomainwindowsothattheentirefrequencycontentisextracted. Thetimewindowisthen
scaledinhalf, leadingto finer timeresolution atthe expense of worsefrequencyresolution. This
processiscontinueduntiladesiredtime-frequencyresolutionisobtained.
The Mexican hat wavelet has excellent localization properties in both time and fre-
quency due to the minimal time-bandwidth product of the Gaussian function. Fig-
ure 5.2 (top panels) shows the basic Mexican wavelet function ψ and its Fourier
1,0
transform,bothofwhichdecayint (ω)likeexp(−t2)(exp(−ω2)). TheMexicanhat
waveletcanbedilatedandtranslatedeasily,asisdepictedinFigure5.2(bottompanel).
Herethreewaveletsaredepicted: ψ , ψ , andψ ,showingbothscalingand
1,0 3/2,−3 1/4,6
translationofthewavelet.
5.3 Formulating mrDMD
ThemrDMDmodelisinspiredbytheobservationthattheslowandfastmodescanbe
separatedforsuchapplicationsasforeground/backgroundsubtractioninvideostreams,
asdiscussedinChapter4. ThemrDMDapproachisarecursivecomputationofDMD
toremovelow-frequency,orslowlyvarying,featuresfromagivencollectionofsnap-
shots.ThisprocessisillustratedinFigure5.4. InDMD,thenumberofsnapshotsmis
chosensothatDMDmodesprovideanapproximatelyfull-rankapproximationofthe
dynamicsobserved. Thus, m ischosensothatallhigh-andlow-frequencycontentis
present. InmrDMD,mischoseninitiallytoallowextractionofthelowest-frequency
modes. Ateachresolutionlevel,theslowestmodesareremoved,thetimedomainisdi-
videdintotwosegmentswithm/2snapshotseach,andDMDisonceagainperformed

| 76  |     |     | Chapter5. | MultiresolutionDMD |     |
| --- | --- | --- | --------- | ------------------ | --- |
Imagω
|     | →    | →    |     | →    | Realω |
| --- | ---- | ---- | --- | ---- | ----- |
|     | −−   | −−   |     | −−   |       |
|     | φ(1) | φ(2) |     | φ(3) |       |
|     | k    | k    |     | k    |       |
Figure5.4. ThemrDMDapproachtakessuccessivesamplesofthedata,initiallywithm
snapshotsanddecreasingbyafactoroftwoateachresolutionlevel.TheDMDspectrumisshownin
themiddlepanel,wherethereare m (bluedots)slow-dynamicmodesattheslowestlevel,m (red)
|     |     | 1   |     |     | 2   |
| --- | --- | --- | --- | --- | --- |
modesatthenextlevel,and m 3 (green)modesatthefastesttimescaleshown. Theshadedregion
representsthemodesthatareremovedatthatlevel. Thebottompanelshowsthewavelet-liketime-
frequencydecompositionofthedatacolor-codedwiththesnapshotsandDMDspectralrepresentations
[167].
m/2snapshotsequence.
oneach Thisrecursiveprocesscontinuesuntiladesiredter-
mination. Becauseweareonlyinterestedinthelowest-frequencymodesateachlevel,
itispossibletosubsamplethesnapshots,reducingmandincreasingthecomputational
efficiency.
Mathematically, mrDMD separates theDMDapproximate solution (1.24)at the

5.3. FormulatingmrDMD 77
firstlevelasfollows:
(cid:7)m
(0)φ(1)
| x     | (t)= | b   | exp(ω | t)  |     |     | (5.9) |
| ----- | ---- | --- | ----- | --- | --- | --- | ----- |
| mrDMD |      | k   | k     | k   |     |     |       |
k=1
|     |     | (cid:7)m |     |     | (cid:7)m |     |     |
| --- | --- | -------- | --- | --- | -------- | --- | --- |
1
|     | =   | b (0)φ(1) | exp(ω | t)+ | b (0)φ(1) exp(ω | t), |     |
| --- | --- | --------- | ----- | --- | --------------- | --- | --- |
|     |     | k         |       | k   | k               | k   |     |
|     |     |           | k     |     | k               |     |     |
|     |     | k=1       |       | k=m | +1              |     |     |
1
|     |     | (slowmodes) |     |     | (fastmodes) |     |     |
| --- | --- | ----------- | --- | --- | ----------- | --- | --- |
wheretheφ(1)
representtheDMDmodescomputedfromthefullmsnapshots.
k
Thefirstsuminexpression(5.9)representstheslow-modedynamics,whereasthe
second sum is everything else. Thus, the second sum can be computed toyield the
matrix
(cid:7)m
|     |     | =     |     | (0)φ(1) exp(ω | t). |     |        |
| --- | --- | ----- | --- | ------------- | --- | --- | ------ |
|     |     | X m/2 | b   |               |     |     | (5.10) |
|     |     |       |     | k k           | k   |     |        |
k=m+1
1
TheDMDanalysisoutlinedintheprevioussectioncannowbeperformedonceagain
onthedatamatrixX . However,thematrixX isnowseparatedintotwomatri-
|     | m/2 |     |     | m/2 |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
ces,
|     |     |     |     | (1) (2) |     |     |        |
| --- | --- | --- | --- | ------- | --- | --- | ------ |
|     |     | X   | =X  | +X      | ,   |     | (5.11) |
|     |     | m/2 |     | m/2 m/2 |     |     |        |
wherethefirstmatrixcontainsthefirstm/2snapshotsandthesecondmatrixcontains
theremainingm/2snapshots.Them slow-DMDmodesatthislevelaregivenbyφ(2)
,
|     |     |     | 2   |     |     |     | k   |
| --- | --- | --- | --- | --- | --- | --- | --- |
wheretheyarecomputedseparatelyinthefirstorsecondintervalofsnapshots.
ThemrDMDprocessworksbyrecursivelyremovingslow-frequencycomponents
,...untiladesired/prescribedmulti-
| andbuildingthenewmatricesX |     |     | ,X  | ,X  |     |     |     |
| -------------------------- | --- | --- | --- | --- | --- | --- | --- |
|                            |     | m/2 | m/4 | m/8 |     |     |     |
resolution decomposition has been achieved. The approximate DMD solution can
thenbeconstructedasfollows:
|     |       | (cid:7)m |          |     | (cid:7)m         |     |     |
| --- | ----- | -------- | -------- | --- | ---------------- | --- | --- |
|     |       | 1        |          |     | 2                |     |     |
|     | (t)=  | (1)φ(1)  | exp(ω(1) | t)+ | (2)φ(2) exp(ω(2) | t)  |     |
| x   |       | b        |          |     | b                |     |     |
|     | mrDMD | k        | k        | k   | k k              | k   |     |
|     |       | k=1      |          |     | k=1              |     |     |
(cid:7)m
|     |     | 3   | (3)φ(3) | exp(ω(3) |     |     |        |
| --- | --- | --- | ------- | -------- | --- | --- | ------ |
|     |     | + b |         | t)+···,  |     |     | (5.12) |
|     |     |     | k k     | k        |     |     |        |
k=1
whereattheevaluationtime t,thecorrectmodesfromthesamplingwindowarese-
|     |     |     |     |     | φ((cid:2)) | ω((cid:2)) |     |
| --- | --- | --- | --- | --- | ---------- | ---------- | --- |
lected at each level of the decomposition. Specifically, and are the DMD
|     |     |     |     |     | k   | k   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
modesandDMDeigenvaluesatthe(cid:2)thlevelofdecomposition,theb ((cid:2))
aretheinitial
k
projectionsofthedataontothetimeintervalofinterest,andthem arethenumberof
k
slowmodesretainedateachlevel. Theadvantageofthismethodisapparent: different
spatiotemporalDMDmodesareusedtorepresentkeymultiresolutionfeatures. There
isnotasinglesetofmodesthatdominatestheSVDandpotentiallyobscuresfeatures
atothertimescales.
Figure5.4illustratesthemrDMDprocessschematically. Inthefigure,athree-level
decomposition is performed, with the slowest scale represented in blue (eigenvalues
and snapshots), the midscale in red, and the fast scale in green. The connection to
multiresolution wavelet analysis is also evident from the bottom panels, as one can
seethatthemrDMDmethodsuccessivelypullsouttime-frequencyinformationina
principledway.

| 78  |     |     |     |     | Chapter5. |     | MultiresolutionDMD |     |
| --- | --- | --- | --- | --- | --------- | --- | ------------------ | --- |
Thesamplingstrategyandalgorithmcanbefurtheroptimizedsinceonlytheslow
modes at each decomposition level need to be accurately computed. Thus, one can
modify the algorithm so the sampling rate increases as the decomposition proceeds
fromoneleveltothenext. ThisassuresthatthelowestlevelsofthemrDMDarenot
highlysampled, sincethecost oftheSVDwould be greatlyincreased by such afine
samplingrate.
| 5.3.1 | Formal | mrDMD | expansion |     |     |     |     |     |
| ----- | ------ | ----- | --------- | --- | --- | --- | --- | --- |
Thesolution(5.12)canbemademoreprecise. Specifically,onemustaccountforthe
numberoflevels(L)ofthedecomposition,thenumberoftimebins(J)foreachlevel,
andthenumberofmodesretainedateachlevel(m ). ThiscanbeeasilyseeninFigure
L
5.4. Thus,thesolutionisparameterizedbythefollowingthreeindices:
|     |     | (cid:2)=1,2,...,L | :                        | numberofdecompositionlevels, |     |     |               | (5.13a) |
| --- | --- | ----------------- | ------------------------ | ---------------------------- | --- | --- | ------------- | ------- |
|     |     | =1,2,...,J        | numbertimebinsperlevel(J |                              |     | =2  | ((cid:2)−1)), |         |
|     |     | j                 | :                        |                              |     |     |               | (5.13b) |
k=1,2,...,m
|     |     |     | (cid:2) | : numberofmodesextractedatlevelL. |     |     |     | (5.13c) |
| --- | --- | --- | ------- | --------------------------------- | --- | --- | --- | ------- |
Toformallydefinetheseriessolutionforx (t),wedefinetheindicatorfunction
|     |     | %   |       |      | mrDMD |     |     |     |
| --- | --- | --- | ----- | ---- | ----- | --- | --- | --- |
|     |     | 1,  | t ∈[t | ,t ] |       |     |     |     |
f (cid:2),j(t)= j j+1 , with j =1,2,...,J and J =2 ((cid:2)−1) , (5.14)
0, elsewhere
whichisonlynonzerointheinterval,ortimebin,associatedwiththevalueof j.
Thethreeindicesandindicatorfunction(5.14)givethemrDMDsolutionexpan-
sion
|     |     |       | (cid:7)L  | (cid:7)J (cid:7)m |                         |                  |     |        |
| --- | --- | ----- | --------- | ----------------- | ----------------------- | ---------------- | --- | ------ |
|     |     |       |           | L (cid:2),j(t)b   | ((cid:2),j)φ((cid:2),j) | exp(ω((cid:2),j) |     |        |
|     |     | x     | (t)=      | f                 |                         |                  | t). | (5.15) |
|     |     | mrDMD |           |                   | k k                     |                  | k   |        |
|     |     |       | (cid:2)=1 | j=1 k=1           |                         |                  |     |        |
ThisconcisedefinitionofthemrDMDsolutionincludestheinformationonthelevel,
timebinlocation,andnumberofmodesextracted. Figure5.5demonstratesmrDMD
intermsof thesolution (5.15). In particular, each modeisrepresented in itsrespec-
tivetimebinandlevel. Analternativeinterpretationofthissolutionisthatityields
(cid:2)
the least-square fit, at each level of the decomposition, to the discrete-time linear
dynamicalsystem
|     |                 |     |                                    | ((cid:2),j)=A | ((cid:2),j) ((cid:2),j) |     |                 |        |
| --- | --------------- | --- | ---------------------------------- | ------------- | ----------------------- | --- | --------------- | ------ |
|     |                 |     |                                    | x             | x ,                     |     |                 | (5.16) |
|     |                 |     |                                    | t+1           | t                       |     |                 |        |
|     |                 |     | ((cid:2),j)                        |               |                         |     | atlevel(cid:2). |        |
|     | wherethematrixA |     | capturesthedynamicsinagiventimebin |               |                         |     | j               |        |
(cid:2),j(t)actsasasiftingfunctionforeachtimebin.
|     | Theindicatorfunction |     | f   |     |     |     |     | Interest- |
| --- | -------------------- | --- | --- | --- | --- | --- | --- | --------- |
ingly,thisfunctionactsastheGáborwindowofawindowedFouriertransform[166].
Sinceoursamplingbinhasahardcutoffofthetimeseries,itmayintroducesome
artificialhigh-frequencyoscillations. Time-seriesanalysis,andwaveletsinparticular,
introducevariousfunctionalformsthatcanbeusedinanadvantageousway. Think-
ingmorebroadly,onecanimagineusingwaveletfunctionsforthesiftingoperation,
thusallowingthetimefunction f (cid:2),j(t)totaketheformofoneofthemanypotential
waveletbases,e.g.,Haar,Daubechies,Mexicanhat,etc.[76,78].
Forthepresent,we
simplyusethesiftingfunctionintroducedin(5.14).
| 5.4 | The mrDMD | algorithm |     |     |     |     |     |     |
| --- | --------- | --------- | --- | --- | --- | --- | --- | --- |
ThemrDMDisarecursive, hierarchicalapplicationofthebasicDMDalgorithmin-
troducedinChapter1. However,thesamplingwindows(snapshotcollection)arenow

5.4. ThemrDMDalgorithm 79
| φ(4,1) ··· | φ(4,8) |     |     |     |
| ---------- | ------ | --- | --- | --- |
| k          | k      |     |     |     |
| −−−→       | −−−→   |     |     |     |
(cid:2)=decompositionlevel
−
|     |     |     | − j | =timebin |
| --- | --- | --- | --- | -------- |
→ →−−−−
((cid:2),j)
φ
k
| φ(3,1) φ(3,2) | φ(3,3) φ(3,4) |        |                            |     |
| ------------- | ------------- | ------ | -------------------------- | --- |
| k k           | k k           |        | →−−                        |     |
| φ(2,1)        | φ(2,2)        |        |                            |     |
| k             | k             | φ(1,1) | k=modenumberatlevel(cid:2) |     |
|               | →−−−−         | k      |                            |     |
Representedarethemodesφ(cid:2),j
| Figure5.5. IllustrationofthemrDMDhierarchy. |     |     |     | and |
| ------------------------------------------- | --- | --- | --- | --- |
k
their position in the decomposition structure. The triplet of integer values (cid:2),j, and k un iquely
expressesthetimelevel,bin,andmodeofthedecomposition.
adjustedandonlytheslowestmodesareextractedateachlevelofthedecomposition.
WehighlightagaintheDMDalgorithmbutnowinthecontextofthemrDMDinno-
vation.Asbefore,whenthestatedimensionnislarge,thematrixAmaybeintractable
toanalyzedirectly. Instead,DMDcircumventstheeigendecompositionofAbycon-
A˜.
sidering a rank-reduced representation in terms of a POD-projected matrix The
mrDMDalgorithmproceedsasfollows:
1. Considerasamplingwindowintimeatlevel(cid:2)andtimebin j ofthedecompo-
sition. Inthissamplingwindow,constructthedatamatricesXandX. (cid:5)
2. TaketheSVDofX:
X=UΣV ∗
|     |     |     | ,   | (5.17) |
| --- | --- | --- | --- | ------ |
where∗denotestheconjugatetranspose,U∈(cid:4)n×r,Σ∈(cid:4)r×r,andV∈(cid:4)m×r.
Here r istherankofthereducedSVDapproximation toX. Theleftsingular
vectorsUarePODmodes.
3. Next, computeA˜((cid:2),j) ,the r ×r projection ofthefullmatrixA ((cid:2),j) ontoPOD
modes:
|     | A ((cid:2),j)=X    | (cid:5) VΣ−1U       | ∗                 |        |
| --- | ------------------ | ------------------- | ----------------- | ------ |
|     | =⇒ A˜((cid:2),j)=U | ∗ A ((cid:2),j) U=U | ∗ X (cid:5) VΣ−1. | (5.18) |
ComputetheeigendecompositionofA˜((cid:2),j)
| 4.  |     | :   |     |     |
| --- | --- | --- | --- | --- |
A˜((cid:2),j)
|     |     | W=WΛ, |     | (5.19) |
| --- | --- | ----- | --- | ------ |

80 Chapter5. MultiresolutionDMD
wherethecolumnsofWareeigenvectorsandΛisadiagonalmatrixcontaining
thecorrespondingeigenvaluesλ .
k
5. Identifyandcollectthesloweigenvalues,ifany,where(cid:7)λ (cid:7)<ρ,andusethem
j
toconstructtheslowmodesatthislevelofdecomposition.
6. Finally,reconstructtheeigendecompositionofA ((cid:2),j) fromWandΛ. Inparticu-
lar,theeigenvaluesofA ((cid:2),j) aregivenbyΛandtheeigenvectorsofA ((cid:2),j) (DMD
modes)aregivenbythecolumnsofΦ((cid:2),j)
:
Φ((cid:2),j)=X (cid:5) VΣ−1W.
(5.20)
Thepoweratlevel(cid:2)andtimebin j maynowbecomputed, followingtheap-
proachdescribedinChapter8.
7. Dividetheoriginal samplingwindowinhalf, andrepeat alloftheabovesteps
foreachofthefirstandsecondhalvesofthesamplingwindowatlevel(cid:2)+1.
5.4.1 Parameters of the mrDMD algorithm
Thisalgorithmhasafewparameters. Instep1,ateachlevel(cid:2),thenumberofsnapshots
ineachsamplingwindowmaybeasubsampleofthefull-resolutiondatabasedonthe
desired slow eigenvalue threshold in step 5. This subsampling enables a substantial
increaseinefficiencyofexecution, especially atlowerlevelsofrecursion withlarger
windows,withoutsacrificingtheabilitytoextractthelowest-amplitude(i.e.,slowest)
modes. In step 2, the rank r of the reduced SVD approximation may be chosen to
exploitlow-ranktruncationofthedata. AsnotedinChapters1and8,this r maybe
choseninaprincipledway.
Instep5, theparameter ρisselected toextract onlyslow modes. Thereissome
freedominthechoiceofρ,andthisvaluemaybeselectedbasedonthedurationofthe
samplingwindow. Tobe specific, theimplementation intheexample codein Algo-
rithm5.3belowchoosesρtoselectmodeswithfewerthantwocyclesofoscillations
withinthesamplingwindow.
Notethattheabovealgorithmalsoallowsconstruction ofthebest-fitdynamical
system at each level (5.16). After decomposing at a specified number of levels, the
solutionmaybereconstructedusing(5.15).
5.5 Example code and decomposition
ThefirstexampleweconsiderforapplicationofmrDMDisillustratedinFigure5.6.
Thisexampleconsistsofasyntheticmovieofm=1000frameswhereeachframehas
n=80×80=6400pixels,sampledatdt =0.01sec. Thethreeunderlyingmodesof
thedatahavedifferent,overlappingspatialdistributions. Mode1oscillatesat5.55Hz
forthefirsthalfofthemovie. Mode2oscillatesat0.9Hzfromseconds3to7ofthe
movie. Mode3hasaslow,stationaryoscillationof0.15Hzfortheentiredurationof
themovie. Forthisdemonstration, Gaussianwhitesensornoisewasaddedtoevery
pixelsothatthesignal-to-noiseratioisapproximately3.Thefollowingsectionofcode
constructsaninstanceofthisexampledata.

5.5. Examplecodeanddecomposition 81
ALGORITHM5.1.Constructexamplemovie(mrDMD_demo.m).
% parameters
| nx = 80; | % horizontal |     | pixels |     |     |     |
| -------- | ------------ | --- | ------ | --- | --- | --- |
| ny = 80; | % vertical   |     | pixels |     |     |     |
| n = nx   | * ny;        |     |        |     |     |     |
| T = 10;  | % sec        |     |        |     |     |     |
dt = 0.01;
t = dt:dt:T;
| sig = 0.1;           | %                                              | magnitude       | of                  | gaussian | noise added |     |
| -------------------- | ---------------------------------------------- | --------------- | ------------------- | -------- | ----------- | --- |
| % 3 underlying       |                                                | modes           |                     |          |             |     |
| [Xgrid,              | Ygrid]                                         | =               | meshgrid(1:nx,      |          | 1:ny);      |     |
| mode1.u              | = exp(-((Xgrid-40).^2/250+(Ygrid-40).^2/250)); |                 |                     |          |             |     |
| mode1.f              | = 5.55;                                        | %               | cycles/sec          |          |             |     |
| mode1.A              | = 1;                                           |                 |                     |          |             |     |
| mode1.lambda         |                                                | = exp(1i        | * mode1.f*2*pi*dt); |          |             |     |
| mode1.range          |                                                | = [0,           | 5];                 |          |             |     |
| mode2.u              | = zeros(nx,                                    |                 | ny);                |          |             |     |
| mode2.u(nx-40:nx-10, |                                                |                 | ny-40:ny-10)        |          | = 1;        |     |
| mode2.f              | = 0.9;                                         | %               | cycles/sec          |          |             |     |
| mode2.A              | = 1;                                           |                 |                     |          |             |     |
| mode2.lambda         |                                                | = exp(1i        | * mode2.f*2*pi*dt); |          |             |     |
| mode2.range          |                                                | = [3,           | 7];                 |          |             |     |
| mode3.u              | = zeros(nx,                                    |                 | ny);                |          |             |     |
| mode3.u(1:nx-20,     |                                                |                 | 1:ny-20)            | = 1;     |             |     |
| mode3.f              | = 0.15;                                        | %               | cycles/sec          |          |             |     |
| mode3.A              | = 0.5;                                         |                 |                     |          |             |     |
| mode3.lambda         |                                                | = exp(1i        | * mode3.f*2*pi*dt); |          |             |     |
| mode3.range          |                                                | = [0,           | T];                 |          |             |     |
| modes(1)             | = mode1;                                       |                 |                     |          |             |     |
| modes(2)             | = mode2;                                       |                 |                     |          |             |     |
| modes(3)             | = mode3;                                       |                 |                     |          |             |     |
| % make               | the movie                                      |                 |                     |          |             |     |
| Xclean               | = zeros(n,                                     |                 | numel(T));          |          |             |     |
| for ti               | = 1:numel(t),                                  |                 |                     |          |             |     |
| Snap                 | = zeros(nx,                                    |                 | ny);                |          |             |     |
| for                  | mi =                                           | 1:numel(modes), |                     |          |             |     |
mymode = modes(mi);
|     | if ti | > round(mymode.range(1)/dt) |     |     | &&  | ... |
| --- | ----- | --------------------------- | --- | --- | --- | --- |
ti < round(mymode.range(2)/dt),
|     |     | Snap | = Snap + | mymode.A | * mymode.u | * ... |
| --- | --- | ---- | -------- | -------- | ---------- | ----- |
real(mymode.lambda^ti);
end;
end;
| Xclean(:, |     | ti) | = Snap(:); |     |     |     |
| --------- | --- | --- | ---------- | --- | --- | --- |
end;
% add noise
| Noise = | sig | * randn(size(Xclean)); |     |     |     |     |
| ------- | --- | ---------------------- | --- | --- | --- | --- |

| 82  |     |         | Chapter5. | MultiresolutionDMD |
| --- | --- | ------- | --------- | ------------------ |
|     |     | spatial | temporal  |                    |
1
0.5
|     | Mode 1 |     | 0   |     |
| --- | ------ | --- | --- | --- |
-0.5
-1
|     |     |     | 0 2 4 | 6 8 10 |
| --- | --- | --- | ----- | ------ |
1
0.5
|     | Mode 2 |     | 0   |     |
| --- | ------ | --- | --- | --- |
-0.5
-1
|     |     |     | 0 2 4 | 6 8 10 |
| --- | --- | --- | ----- | ------ |
0.5
|     | Mode 3 |     | 0   |     |
| --- | ------ | --- | --- | --- |
-0.5
|     |     |     | 0 2 4 | 6 8 10 |
| --- | --- | --- | ----- | ------ |
Time (sec)
Figure5.6.ModesofexampledatatodemonstratemrDMD.Thedataisn=6400pixels
bym=1000snapshots,sampledatdt =0.01sec. Thethreemodeshaveoverlappingspatialdistri-
butionsandoscillateat5.55,0.9,and0.15Hz,respectively. Thefirsttwomodesareonlyactivefor
apartofthemovie.
| X   | = Xclean + Noise; |     |     |     |
| --- | ----------------- | --- | --- | --- |
Tovisualizethedataconstructedaboveasamovie,weusethefollowingcode.
| ALGORITHM5.2.Visualize |     | exampleasamovie(mrDMD_demo.m). |     |     |
| ---------------------- | --- | ------------------------------ | --- | --- |
figure;
for ti = 1:numel(t),
|     | Pic = reshape(X(:, | ti), nx,          | ny); |     |
| --- | ------------------ | ----------------- | ---- | --- |
|     | imagesc(Pic,       | range(X(:))/2*[-1 | 1]); |     |
|     | axis square;       | axis off;         |      |     |
pause(dt);
end;
Weseek amethodtodecomposethisdataandcharacterize itsdynamicsinspace
and time within the sampling window. The code in Algorithm 5.3 calls the func-
tionmrDMD.m,whichimplementsthealgorithmdescribedinthischapter. Figure5.7

5.5. Examplecodeanddecomposition 83
DMD Mode Amplitude
|     |     | 0   |     | 1   |
| --- | --- | --- | --- | --- |
6.4
3.2
1.6
)zH( .qerF
0.8
0.4
0.2
0
|     | 0   | 1  2  3  | 4  5  6  | 7  8  9  10 |
| --- | --- | -------- | -------- | ----------- |
Time (sec)
Figure5.7. ResultsofmrDMDforthespatiotemporaldynamicsexampleinFigure5.6.
Themultiresolutionviewofpowerasitvariesintimeandinfrequencyisshownasanimage. The
absolutevaluesofspatialDMDmodesatafewlevelsφ((cid:2),j)
areshownontheright,andtheseclosely
resembletheunderlyingspatialmodes.
showstheresultingoutputasawavelet-inspiredviewofthemultiresolutionstructures
presentinthedata,followingtheaxesillustratedinFigure5.4,aswellastheassociated
spatialmodesateachlevelofdescription.
Comparing these modes extracted at levels 1, 4, and 6 to the generative modes
inFigure5.6, itisclearthatmrDMDisanatural description ofthedata. Notethat
where the time course of the mode does not match well with the halving windows
ofthealgorithm, such asforthemiddlemodeinFigure5.7initsfirstnonzerotime
window,ourabilitytoestimatethemodeamplitudeispoor.
ALGORITHM5.3.ComputemrDMDofexamplemovie(mrDMD_demo.m).
| L = 6;       | % number       | of levels         |             |                 |
| ------------ | -------------- | ----------------- | ----------- | --------------- |
| r = 10;      | % rank         | of truncation     |             |                 |
| mrdmd =      | mrDMD(X,       | dt,               | r, 2, L);   |                 |
| % compile    | visualization  |                   | of multires | mode amplitudes |
| [map, low_f] | =              | mrDMD_map(mrdmd); |             |                 |
| [L, J]       | = size(mrdmd); |                   |             |                 |
%%
figure;
imagesc(-map);

| 84  |     |     |     |     |     |     | Chapter5. | MultiresolutionDMD |
| --- | --- | --- | --- | --- | --- | --- | --------- | ------------------ |
set(gca, ’YTick’, 0.5:(L+0.5), ’YTickLabel’, floor(low_f*10)/10)
;
|     | set(gca, | ’XTick’,      | J/T*(0:T) |           | +   | 0.5);               |     |     |
| --- | -------- | ------------- | --------- | --------- | --- | ------------------- | --- | --- |
|     | set(gca, | ’XTickLabel’, |           | (get(gca, |     | ’XTick’)-0.5)/J*T); |     |     |
axis xy;
|     | xlabel(’Time  |       | (sec)’); |     |     |     |     |     |
| --- | ------------- | ----- | -------- | --- | --- | --- | --- | --- |
|     | ylabel(’Freq. |       | (Hz)’);  |     |     |     |     |     |
|     | colormap      | pink; |          |     |     |     |     |     |
grid on;
ThefunctionmrDMD.musedinAlgorithm5.3isshownbelow. Notethatthisfunc-
tionrecurses,terminatingonlywhentheparameterLis1.
ALGORITHM5.4.RecursivefunctiontocomputemrDMD(mrDMD.m).
|     | function   | tree | = mrDMD(Xraw, |     | dt, | r, max_cyc, |          | L)  |
| --- | ---------- | ---- | ------------- | --- | --- | ----------- | -------- | --- |
|     | % function | tree | = mrDMD(Xraw, |     |     | dt, r,      | max_cyc, | L)  |
% Inputs:
|     | % Xraw                     | n            | by m             | matrix       | of raw      | data,       |         |               |
| --- | -------------------------- | ------------ | ---------------- | ------------ | ----------- | ----------- | ------- | ------------- |
|     | %                          | n            | measurements,    |              | m           | snapshots   |         |               |
|     | % dt                       | time         | step             | of           | sampling    |             |         |               |
|     | % r                        | rank         | of               | truncation   |             |             |         |               |
|     | % max_cyc                  | to           | determine        |              | rho,        | the freq    | cutoff, | compute       |
|     | %                          | oscillations |                  |              | of max_cyc  |             | in the  | time window   |
|     | % L                        | number       |                  | of levels    | remaining   |             | in      | the recursion |
|     | T = size(Xraw,             |              | 2) *             | dt;          |             |             |         |               |
|     | rho = max_cyc/T;           |              | %                | high         | freq cutoff |             | at this | level         |
|     | sub = ceil(1/rho/8/pi/dt); |              |                  |              | % 4x        | Nyquist     | for     | rho           |
|     | %% DMD at                  | this         | level            |              |             |             |         |               |
|     | Xaug = Xraw(:,             |              | 1:sub:end);      |              | % subsample |             |         |               |
|     | Xaug = [Xaug(:,            |              | 1:end-1);        |              | Xaug(:,     | 2:end)];    |         |               |
|     | X = Xaug(:,                | 1:end-1);    |                  |              |             |             |         |               |
|     | Xp = Xaug(:,               |              | 2:end);          |              |             |             |         |               |
|     | [U, S, V]                  | = svd(X,     |                  | ’econ’);     |             |             |         |               |
|     | r = min(size(U,2),         |              |                  | r);          |             |             |         |               |
|     | U_r = U(:,                 | 1:r);        | %                | rank         | truncation  |             |         |               |
|     | S_r = S(1:r,               |              | 1:r);            |              |             |             |         |               |
|     | V_r = V(:,                 | 1:r);        |                  |              |             |             |         |               |
|     | Atilde =                   | U_r’         | * Xp             | * V_r        | / S_r;      |             |         |               |
|     | [W, D] =                   | eig(Atilde); |                  |              |             |             |         |               |
|     | lambda =                   | diag(D);     |                  |              |             |             |         |               |
|     | Phi = Xp                   | * V(:,1:r)   |                  | / S(1:r,1:r) |             | * W;        |         |               |
|     | %% compute                 | power        | of               | modes        |             |             |         |               |
|     | Vand = zeros(r,            |              | size(X,          |              | 2)); %      | Vandermonde |         | matrix        |
|     | for k =                    | 1:size(X,    | 2),              |              |             |             |         |               |
|     | Vand(:,                    | k)           | = lambda.^(k-1); |              |             |             |         |               |
end;

5.5. Examplecodeanddecomposition 85
% the next 5 lines follow Jovanovic et al, 2014 code:
G = S_r * V_r’;
P = (W’*W).*conj(Vand*Vand’);
q = conj(diag(Vand*G’*W));
Pl = chol(P,’lower’);
b = (Pl’)\(Pl\q); % Optimal vector of amplitudes b
%% consolidate slow modes, where abs(omega) < rho
omega = log(lambda)/sub/dt/2/pi;
mymodes = find(abs(omega) <= rho);
thislevel.T = T;
thislevel.rho = rho;
thislevel.hit = numel(mymodes) > 0;
thislevel.omega = omega(mymodes);
thislevel.P = abs(b(mymodes));
thislevel.Phi = Phi(:, mymodes);
%% recurse on halves
if L > 1,
sep = floor(size(Xraw,2)/2);
nextlevel1 = mrDMD(Xraw(:, 1:sep),dt, r, max_cyc, L-1);
nextlevel2 = mrDMD(Xraw(:, sep+1:end),dt, r, max_cyc, L-1);
else
nextlleve1 = cell(0);
nextlevel2 = cell(0);
end;
%% reconcile indexing on output
% (because MATLAB does not support recursive data structures)
tree = cell(L, 2^(L-1));
tree{1,1} = thislevel;
for l = 2:L,
col = 1;
for j = 1:2^(l-2),
tree{l, col} = nextlevel1{l-1, j};
col = col + 1;
end;
for j = 1:2^(l-2)
tree{l, col} = nextlevel2{l-1, j};
col = col + 1;
end;
end;
5.5.1 Global temperature data and El Niño
Inthisexample, weusemrDMDondatameasuringglobal surfacetemperatureover
the ocean. The data is open source from the NOAA/OAR/ESRL PSD, Boulder,
Colorado,USA.TheNOAA_OI_SST_V2datasetconsideredcanbedownloadedat
http://www.esrl.noaa.gov/psd/. Thedataspansa20-yearperiodfrom1990to2010.

86 Chapter5. MultiresolutionDMD
(cid:16)(cid:20)(cid:20)(cid:19)(cid:1) (cid:16)(cid:20)(cid:20)(cid:20)(cid:1)
(cid:2)(cid:7)(cid:9)(cid:7)(cid:8)(cid:18)(cid:1)
(cid:12) (cid:13)(cid:5)(cid:14)(cid:1) (cid:13)(cid:6)(cid:14)(cid:1) (cid:12)(cid:1)
(cid:11)(cid:1)
(cid:11)(cid:1)
(cid:11)(cid:1)
(cid:11)(cid:1)
(cid:11)(cid:1)
(cid:11)(cid:1)
→
(cid:16)(cid:20)(cid:20)(cid:15)(cid:1)
(cid:13)(cid:3)
Y
(cid:14)(cid:10)(cid:13)
e
(cid:4)
a
(cid:14)(cid:1)
r
−−−
(cid:2)(cid:7)
−
(cid:9)(cid:7)
−
(cid:8)(cid:16)
−
(cid:17)
(cid:1) (cid:15)−(cid:16)−(cid:15)(cid:1)−−−−−−−−−−
ElNiñoModeof1997
(warmspotoffPeru)
leveL
φ(1,1)
1
φ(1,1)
2
φ(4,7)
1
t≈1997
φ(4,9)
1 t≈1999
Figure 5.8. Application of mrDMD on SST data from 1990 to 2010. The leftpanel
illustratestheprocessforafour-leveldecomposition. Ateachlevel,modesslowerthanaspecificcutoff
areextracted. Atagivenlevel,thezero-modecomponenthasperiodT =∞. Illustratedarethe
(a)level-1mrDMDmodewithperiodT =∞and(b)Level-1mrDMDmodewithperiodT =52
weeks.Furtheroninthedecompositionwecanextractthe(c)level-4mrDMDmodeof1997and(d)
level-4mrDMDmodeof1999.Mode(c)clearlyshowstheElNiñomodeofinterestthatdevelopsin
thecentralandeast-centralequatorialPacific.TheElNiñomodewasnotpresentin1999,asisclear
frommode(d)[167].
Figure5.8showstheresultsofthemrDMDalgorithm. Specifically,afour-levelde-
compositionwasperformedwiththeslowspatiotemporalmodespulledateachlevel,
assuggestedinFigure5.4. Atthefirstlevelofthedecomposition,twomodesareex-
tracted: thezeromode(T =∞)depictedinFigure5.8(a)andayearlycycle(T =52
weeks)showninFigure5.8(b). Theyearlycycleistheslowestmodeextractedatlevel
1.
Notethattheω=0modecomponentoflevel1,φ(1,1)
,correspondstotheaverage
1
oceantemperatureovertheentire20-yeardataset.
We continue the mrDMD analysis through to L = 4. At the fourth level, the
data-drivenmethodofmrDMDdiscoversthe1997ElNiñomodegeneratedfromthe
well-knownElNiño,SouthernOscillation(ENSO).ElNiñoisthewarmphaseofthe
ENSOcycleandisassociated withabandofwarmoceanwaterthatdevelopsinthe
central and east-central equatorial Pacific (between approximately the International
DateLineand120°W),includingoffthePacificcoastofSouthAmerica. ENSOrefers
tothecycleofwarmandcoldtemperatures,asmeasuredbyseasurfacetemperature,
SST,ofthetropicalcentralandeasternPacificOcean. ElNiñoisaccompaniedbyhigh
airpressureinthewesternPacificandlowairpressureintheeasternPacific. Thecool
phaseofENSOiscalledLaNiña,withSSTintheeasternPacificbelowaverageandair

5.6. Overcomingtranslationalandrotationalinvariances 87
pressureshighintheeasternandlowinthewesternPacific. TheENSOcycle,bothEl
NiñoandLaNiña,causesglobalchangesofbothtemperatureandrainfall.
Indeed,1997isknowntohavebeenastrongElNiñoyear,asverifiedbyitsstrong
modalsignatureinthe(cid:2)=4leveldecomposition ofmrDMD.Incontrast, thesame
samplingwindowshifteddownto1999producesnoElNiñomode,whichisinkeep-
ingwithknownoceanpatternsthatyear. ThemrDMDmodeclearlyshowsthisband
ofwarmoceanwaterasaspatiotemporalmodein1997inFigure5.8(c).
TheseresultscouldnothavebeenproducedwithDMDunlessthecorrectsampling
windowswerechosenaheadoftime,requiringasupervisedlearningstepnotrequired
bymrDMD.ThusmrDMDprovidesaprincipled,algorithmicapproachthatiscapa-
bleofdata-drivendiscoveryindatafromcomplexsystems,suchasocean/atmospheric
data.
5.6 Overcoming translational and rotational invariances
The final application of mrDMD is to an example that is notoriously difficult for
SVD-based methods to characterize, namely, when translational and/or rotational
structures are present. Indeed, such invariances completely undermine our ability
to compute low-rank embeddings of the data as driven by correlated structures, or
POD/PCAmodes.ThishasbeentheAchillesheelofmanySVD-basedmethodsinap-
plicationssuchasPCA-basedfacerecognition,wherewell-croppedandcenteredfaces
arerequiredforreasonableperformance,sothattranslationandrotationareremoved
inanexpensivepreprocessingprocedure.
In adynamical systemssetting, asimple traveling wavewill appear tobeahigh-
dimensionalobjectinPODspacedespitethefactthatitisonlyconstructedfromtwo
modes, oneassociated withtranslational invariance. For dynamical cases exhibiting
translation and/or rotation, Rowley and Marsden [234]formulated one of theonly
mathematical strategies to date to extract the low-dimensional embeddings. In par-
ticular,theydeveloped atemplate-matchingtechniquetofirst removetheinvariance
beforeapplyingSVD.Althougheffective,itisnotsuitedforcaseswheremultipleob-
jectsandtimescalesarepresentinthedata.
ThemrDMDapproachisabletohandleinvariancessuchastranslationandrota-
tion. Consideronceagainthecaseofasimpletravelingwave. StandardDMDapplied
tothetravelingwavewouldresultinasolutionapproximationrequiringmanyDMD
modesdue tothe slow fall-off of thesingular values (1.18) in step 1 of theDMD al-
gorithm. Further,theeigenvaluesω in(1.24)wouldalsobeboundedawayfromthe
k
originasthereisnobackgroundmodeforsuchtranslatingdata.
InthemrDMDarchitecture,thefactthattheeigenvaluesareboundedawayfrom
theorigin(andtypicallyO(1))intheinitialsnapshotwindowXwouldsimplyallow
themrDMDmethodtoignorethetravelingwaveatthefirstlevelofmrDMD.Once
thedomainisdividedintotwoforthenextlevelofanalysis,thetravelingwaveisnow
effectivelymovingathalfthespeedinthisnewdomain,i.e.,theeigenvalueshavemi-
grated toward the origin and the traveling wave is now reevaluated. The recursive
procedureeventuallyadvancestoasamplingwindowwherethetravelingwavelooks
sufficiently stationary and low rank to be extracted in the multiresolution analysis.
The level at which it is extracted also characterizes the speed of the traveling wave.
Specifically,thehigherthelevelinthedecompositionwherethetravelingwaveisex-
tracted,thefasteritsspeed.

| 88  |     |     |     |                                                                            |     | Chapter5. | MultiresolutionDMD                                                          |     |
| --- | --- | --- | --- | -------------------------------------------------------------------------- | --- | --------- | --------------------------------------------------------------------------- | --- |
|     |     |     |     | (cid:2)(cid:6)(cid:13)(cid:14)(cid:1)(cid:4)(cid:12)(cid:9)(cid:10)(cid:1) |     |           | (cid:5)(cid:11)(cid:12)(cid:16)(cid:1)(cid:4)(cid:12)(cid:9)(cid:10)(cid:1) |     |
|     |     |     |     |                                                                            |     |           | ψ¯ (x,y−vt)                                                                 |     |
2
|     |     | 10v       |     | =             | 10v | +   |     |     |
| --- | --- | --------- | --- | ------------- | --- | --- | --- | --- |
|     | v   |           |     |               |     |     | v   |     |
|     |     | x¯(x,y,t) |     | ψ¯ (x−10vt,y) |     |     |     |     |
1
(cid:19)(cid:10)(cid:20)(cid:1)
|     | (cid:3)(cid:10)(cid:15)(cid:10)(cid:11)(cid:1)(cid:21)(cid:23)(cid:1) | (cid:8)(cid:1) (cid:18)(cid:1) | (cid:9)(cid:1) (cid:10)(cid:1) | (cid:18)(cid:1) |     |     |     |     |
| --- | --------------------------------------------------------------------- | ------------------------------ | ------------------------------ | --------------- | --- | --- | --- | --- |
φ(13,7)
|     |     |     | (cid:17)(cid:1) |     |     | 1   |     | sedomtsaf |
| --- | --- | --- | --------------- | --- | --- | --- | --- | --------- |
(cid:17)(cid:1)
|     |     |     | (cid:17)(cid:1) |     | (cid:19)(cid:8)(cid:20)(cid:1) |     | (cid:19)(cid:9)(cid:20)(cid:1) |     |
| --- | --- | --- | --------------- | --- | ------------------------------ | --- | ------------------------------ | --- |
(cid:17)(cid:1)
(cid:17)(cid:1)
|     |     |     |                 |     |     | φ(13,3) |     | φ(13,5) |
| --- | --- | --- | --------------- | --- | --- | ------- | --- | ------- |
|     |     |     | (cid:17)(cid:1) |     |     | 1       |     | 1       |
(cid:3)(cid:10)(cid:15)(cid:10)(cid:11)(cid:1)(cid:22)(cid:1) sedomwols
|     |     | (cid:6)(cid:1) |     | (cid:7)(cid:1) | (cid:19)(cid:6)(cid:20)(cid:1) |     | (cid:19)(cid:7)(cid:20)(cid:1) |     |
| --- | --- | -------------- | --- | -------------- | ------------------------------ | --- | ------------------------------ | --- |
(cid:3)(cid:10)(cid:15)(cid:10)(cid:11)(cid:1)(cid:21)(cid:1) φ(2,1) φ(2,2)
|     |     |     |     |     |     | 1   |     | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Figure5.9. ThemrDMDapproachseparatesmovingobjects. Twomodes(toppanella-
beled“FastMode"and“SlowMode")arecombinedinthedatasnapshots(toprightpanel).The“Fast
Mode"movesrightwardatspeed10v whilethe“SlowMode"movesupwardatspeedv. Wetake
v =1/40withoutlossofgenerality. Thusthefastandslowmodespeedsdifferbyapproximately
anorderofmagnitude. InmrDMD(bottomleftpanel),the“SlowMode"isextractedatlevel2,as
representedbypanels(a)and(b).The“FastMode"isextractedatlevel13,asrepresentedinthethree
representativepanels(c)–(e). Althoughthereissomeshadow(residual)oftheslowmodeonthefast
modeandviceversa,mrDMDisremarkablyeffectiveatextractingthecorrectmodes.Moreover,the
levelatwhichtheyareextractedcanallowforareconstructionofthevelocityanddirection.Toour
knowledge,thisisthebestperformanceachievedtodatewithanSVD-basedmethodwithmultiple
time-scaleobjects.
Figure5.9demonstratestheapplicationofthemrDMDmethodtoasimpleexam-
pleinwhichtherearetwomovingobjects,onemovingslowlyandtheothermoving
faster. Specifically,theexampleconstructedresultsfromthedynamicalsequence
|     |     |     | x¯=ψ¯ | (x−10vt,y)+ψ¯ | (x,y−vt), |     |     |     |
| --- | --- | --- | ----- | ------------- | --------- | --- | --- | --- |
(5.21)
|     |     |     |     | 1   | 2   |     |          |     |
| --- | --- | --- | --- | --- | --- | --- | -------- | --- |
|     |     |     |     |     |     |     | ψ¯ (x,y) | =   |
where the two modes used to construct the true solution are for j 1,2.
j
ThetwomodesareGaussiansoftheformψ¯ =exp(−σ(x−x )2−σ(y−y )2)with
|     |     |     |     |     | j   |     | 0   | 0   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
σ =0.1,and(x ,y )=(−18,20)and(x ,y )=(−20,−9)forthefastandslowmodes,
|     |     | 0 0 |     | 0   | 0   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
respectively. Note that the first mode is translating rightward at speed 10v and the
secondmodeistranslatingupwardatspeedv. Withoutlossofgenerality,v canbeset
Itischosentobev=1/40forthedomainandGaussiansconsidered.
toanyvalue.
Inthiscase,thestraightforwardtemplate-matchingprocedurewouldfailduetothe
twodistincttimescalesoftheobjects. Asshowninthefigure,mrDMDiscapableof
pullingoutthetwomodesatlevels2(slow)and13(fast)oftheanalysis. Althoughthere
isaresidualinbothextractedmodes,slowandfast,mrDMDdoesareasonablejobof

5.6. Overcomingtranslationalandrotationalinvariances 89
extracting the fast and slow modes. To our knowledge, this is the only SVD-based
methodcapableofsuchunsupervisedperformance.
Themotivationforthisexampleisquiteclearwhenconsideringvideoprocessing
andsurveillance. Inparticular,formanyapplicationsinthisarea,backgroundsubtrac-
tionisonlyonestepintheoverallvideoassessment. Identificationoftheforeground
objectsisthenext, andultimatelymoreimportant, task. Considertheexampleofa
videoofastreetsceneinwhichthereisapedestrianwalking(slowtranslation)along
withavehicledrivingdowntheroad(fasttranslation). Not onlywouldwewantto
separatetheforegroundfromthebackground,butalsowewouldwanttoseparatethe
pedestrianfromthevehicle. Moreprecisely,wewouldwanttomakeaseparatevideo
andidentifydifferentobjectsinthevideo. TheresultsofFigure5.9showthatmrDMD
maybeeffectiveatthiskindoftask.

Chapter 6
DMD with Control
The modeling of complex, high-dimensional systems that exhibit dynamics and re-
quirecontrolispermeatingnotonlythetraditionalengineeringandphysicalsciences,
butalsomodernapplicationssuchaseradicationeffortsofinfectiousdiseases,distribu-
tionsystems,andtheelectricalgrid. DMDwithcontrol(DMDc)utilizesboththemea-
surementsofthesystemandtheappliedexternalcontroltoextracttheunderlyingdy-
namicsandtheinput-outputcharacteristicsinanequation-freemanner[222]. DMDc
inheritstheadvantageouscharacteristicsofDMD:itoperatessolelyonsnapshotdata,
efficiently handles high-dimensional measurement data, and connects measurement
data to the analysis of nonlinear dynamical systems via Koopman operator theory.
DMDccanalsoextractinput-outputcharacteristics,allowingfortheconstructionof
asetofROMsthatcanbeusedtopredictanddesigncontrollersforhigh-dimensional,
complexsystems.
6.1 Formulating DMDc
TheDMDcmethodwasoriginallydevelopedtoanalyzemeasurementdatacollected
fromcomplexsystemswhereexogenousforcinghasbeenappliedduringtheobserva-
tionperiod. Thegoal oferadicatinginfectious diseases, such aspoliomyelitis, offers
amotivatingexampleforthedevelopmentofDMDc;thisisdiscussedinChapter11.
Ascasesofparalyzedchildrenareobserved,largenumbersofchildrenarealsoconcur-
rentlybeingvaccinatedtofightthespreadofthisterribledisease. DMDcutilizesboth
themeasurementsofthestateandtheexogenous inputtodisambiguatetheunderly-
ingdynamicsandtheimpactoftheforcing. Characterizingtheunderlyingdynamics
andtheinput-outputpropertiesiscriticaltothedevelopmentofpredictivemodelsand
controlstrategiestodrivethesystemtoaparticularstate. Inthissection,wedescribe
thebasicformulationofDMDc.
6.1.1 Data and a dynamical system with inputs
Thegoal of DMDcis to characterize the relationship between three measurements:
thecurrent measurement x , thefuturestatex ,andthecurrent control u . The
k k+1 k
relationshipcanbedescribedbythecanonicaldiscretelineardynamicalsystem
x k+1 ≈Ax k +Bu k , (6.1)
91

| 92  |     | Chapter6. | DMDwithControl |     |
| --- | --- | --------- | -------------- | --- |
Figure 6.1. Thetop leftpanelshowsapitchingairfoil. Thetoprightpanel showsthe
InternationalSpaceStation.Thebottomleftimageshowsachildbeingvaccinatedagainstpolio.The
bottomrightimageshowsbednetsencompassingaseriesofbedsinahospital. Eachofthesecomplex
systemshasbothstatedynamicsandthepossibilityofactuation. Forthepitchingairfoil,DMDcis
abletohandlethehighdimensionalityofthesystemanddiscovertheinput-outputcharacteristics.
Inthespreadofinfectiousdisease,vaccinationsandbednetsareakeyactuationtool forarresting
transmission of disease. Top left panel from [222], top right panel reprinted courtesy of NASA,
bottompanelsreprintedwithpermissionfromtheInstituteforDiseaseModeling.
where x ∈ (cid:2)n, u ∈ (cid:2)q, A ∈ (cid:2)n×n, and B ∈ (cid:2)n×q. Theoperator A describes the
k k
dynamics of the unforced system. The operator B characterizes the impact of the
input u on the state x . The relationship in (6.1) does not need to hold exactly,
k k+1
similartoDMD.ThegoalistofindapproximationsofAandBfrommeasurements.
(cid:5)
ThestatesnapshotmeasurementmatricesXandX arecollectedinthesamemanner
asforDMD.Anewmeasurementsnapshotmatrixisconstructedfortheinputs:
|     | ⎡       | ⎤   |     |       |
| --- | ------- | --- | --- | ----- |
|     | | |     | |   |     |       |
| Υ=⎣ |         | ⎦   |     |       |
|     | u u ... | u . |     | (6.2) |
|     | 1 2     | m−1 |     |       |
|     | | |     | |   |     |       |
(6.1)canberewritteninmatrixformtoincludethenewdatamatrices:
(cid:5)≈AX+BΥ.
|     | X   |     |     | (6.3) |
| --- | --- | --- | --- | ----- |
Astandardperspectivefromthecontrolcommunityistoincludeameasurementequa-
tion. Alinearobservationequationoftheformy=Cxistypicallyconstructed,indi-
catingahiddendynamicstatexandanoutputmeasurementy. Foralargenumberof
DMDapplicationsinvolvingnumericalsimulations,themeasurementmatrixCisthe

| 6.1. FormulatingDMDc |             |     |                |     |               |     | 93  |
| -------------------- | ----------- | --- | -------------- | --- | ------------- | --- | --- |
|                      | Experiments |     | Data Snapshots |     | Data Matrices |     |     |
in Time
Numerical
|     |     |     |     |     | ⎡   |     | ⎤   |
| --- | --- | --- | --- | --- | --- | --- | --- |
State Measurements
|     |     |     |           | X=  | ⎣x  | x ··· | x ⎦ |
| --- | --- | --- | --------- | --- | --- | ----- | --- |
|     |     |     |           |     | 1   | 2     | m−1 |
|     |     |     | x x x     |     |     |       |     |
|     |     |     | 1 2 ··· m |     | ⎡   |       | ⎤   |
Laboratory
|     |     |     |     | X   | ⎣x  | x ··· | x ⎦ |
| --- | --- | --- | --- | --- | --- | ----- | --- |
|     |     |     |     |     | = 2 | 3     | m   |
Control Measurements
x
|     |     |     |     |     | ⎡   |     | ⎤   |
| --- | --- | --- | --- | --- | --- | --- | --- |
Historical
|     |     |     | u u u     | Υ=  | ⎣u  | u ··· | u ⎦ |
| --- | --- | --- | --------- | --- | --- | ----- | --- |
|     |     |     | 1 2 ··· m |     | 1   | 2     | m−1 |
Figure6.2. ShapingdatamatricesforDMDc. Datacanbecollectedfromanumberof
differentsources,suchasnumericalsimulations,laboratoryexperiments,andhistoricaldata. For
systemswithexogenousforcing,measurementsoftheinputsarealsoimportant. TheDMDcmethod
utilizesmeasurementsofboththestateandtheexternalforcing[modifiedfigurefrom[222]].
identity. Theobservationequationisimportantwithinthesystemidentificationper-
spective. Foranumberofaerospace applicationsconsidered inthe1980sand1990s,
thenumberofmeasurementswastypicallysmallerthanthenumberofstatesrequired
[151,152].
todescribetheinput-output models Thisisdiscussed ingreater detailin
Chapter7. DMDcwasdevelopedfortheoppositeregime,wherethenumberofstate
measurementsismuchlargerthantherankoftheunderlyingsystem.
Figure6.2illustratesthecollectionofstateandinputmeasurementdatafromnu-
merical simulations, laboratory experiments, and historicalrecords. DMDcutilizes
|     |     |     | (cid:5) ,andΥtodiscoverabest-fitapproximationoftheoper- |     |     |     |     |
| --- | --- | --- | ------------------------------------------------------- | --- | --- | --- | --- |
thethreedatamatricesX,X
atorsAandB. Thenexttwosubsectionsdetailhowtosolvefortheseoperators. The
firstsubsection outlinestheanalysisandalgorithmifthematrixBisknownorwell
estimated. ThesecondsubsectiondescribeshowtofitAandB.
| 6.1.2 The | operator | B is known |     |     |     |     |     |
| --------- | -------- | ---------- | --- | --- | --- | --- | --- |
Let us first consider a case where the operator B is known or well estimated. This
idealistic assumption is not true for most complex systems without well-defined or
physics-basedgoverningequations,butitdoesillustratethemajormotivationofthis
method. Withoutincludingtheeffectsoftheinputs,standardDMDdoesnotproduce
thecorrectdynamiccharacteristics.
ThecontrolsnapshotmatrixΥandoperatorBcanbesubtracted
fromthetime-
|     | shiftedsnapshotmatrixX |     | (cid:5) in(6.3),giving |     |     |     |       |
| --- | ---------------------- | --- | ---------------------- | --- | --- | --- | ----- |
|     |                        |     | X (cid:5)−BΥ≈AX.       |     |     |     | (6.4) |
ThegoalistosolvefortheoperatorA. TheprocedureissimilartothestandardDMD
algorithmwherewefirstcomputethetruncatedSVDwithranktruncation r ofthe
statesnapshotmatrixX=UΣV ∗ . Thebest-fitoperatorAcanthenbecomputedas
|     |     |     | A=(X (cid:5)−BΥ)VΣ−1U | ∗ . |     |     | (6.5) |
| --- | --- | --- | --------------------- | --- | --- | --- | ----- |

| 94  |     |                                |     |     |                     | Chapter6. |     | DMDwithControl |
| --- | --- | ------------------------------ | --- | --- | ------------------- | --------- | --- | -------------- |
|     |     | System Identification          |     |     | Predictive Modeling |           |     |                |
|     |     | Specify input control sequence |     |     | Data                |           |     | Prediction     |
snoitacilppA
|     |     | Υ=  |     |     | x   | x   | x   | x   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     |     | −2  |     | −1  | 0 1 |
A˜Uˆ∗
|     |     |                       | Υ    |     |      |     |     | Uˆ    |
| --- | --- | --------------------- | ---- | --- | ---- | --- | --- | ----- |
|     |     | Run experiment using  |      |     |      |     |     |       |
|     |     |                       | X, X |     |      |     | u   |       |
|     |     |                       |      |     | u −2 | u   | −1  | 0 x˜1 |
B˜
|     |     | x   | k+1=Ax k+Bu |     | Reduc e d |  O r de r M o d | e l       |     |
| --- | --- | --- | ----------- | --- | --------- | --------------- | --------- | --- |
|     |     |     |             | k   | x         | A ˜             | x k+B˜u˜k |     |
|     |     |     |             |     | ˜ k       | + 1 =           | ˜         |     |
Figure 6.3. Twopossible applications of DMDc: System Identification and predictive
modeling[222].
ThisderivationisequivalenttoDMDiftheinputsnapshotsareeitheru =0∀ j ∈
j
|     | [1,m−1]or |     | =          |            | (cid:20) |          |         |              |
| --- | --------- | --- | ---------- | ---------- | -------- | -------- | ------- | ------------ |
|     |           |     | B 0. Ifthe | truncation | value r  | n, amore | compact | and computa- |
tionallyefficientmodelcanbefoundusingabasistransformationx˜=U ∗ xsimilarto
DMD.Thereduced-orderapproximationofAis
|     |     |     |     | A˜ =U ∗(X | (cid:5)−BΥ)VΣ−1. |     |     |     |
| --- | --- | --- | --- | --------- | ---------------- | --- | --- | --- |
(6.6)
|     | NotethataROMcanbeconstructedusingA˜ |     |     |     | andB˜ | =U ∗ |     |     |
| --- | ----------------------------------- | --- | --- | --- | ----- | ---- | --- | --- |
B. Theeigendecomposition
ofA ˜ ,definedbyA ˜ W=WΛ,yieldseigenvectorsthatcanbeusedtofindthedynamic
|     | modesofA. |     | Theexactdynamicmodescanbefoundwiththedescription |                        |     |     |     |       |
| --- | --------- | --- | ------------------------------------------------ | ---------------------- | --- | --- | --- | ----- |
|     |           |     |                                                  | Φ=(X (cid:5)−BΥ)VΣ−1W. |     |     |     | (6.7) |
Ifλ(cid:18)=0,thenthisistheDMDmodeforλ.
|     |     |     |     |     | Iftheeigenvalue |     | is0,thenthedynamic |     |
| --- | --- | --- | --- | --- | --------------- | --- | ------------------ | --- |
modeiscomputedusingΦ=UW.
| 6.1.3 | The | operator | B is unknown |     |     |     |     |     |
| ----- | --- | -------- | ------------ | --- | --- | --- | --- | --- |
This section describes how to find approximations of the operators A and B solely
from snapshot data. By relaxing the assumption that B is known, a wider range of
complexsystemscanbeinvestigatedwithDMDc. Experimentalistsandanalystscan
use DMDc to disambiguate the underlying dynamics and the impact of external in-
puts. Further,DMDccouldbeusedtohelpdesigntheinputstoexplorethedynamical
propertiesoftheunderlyingsystem.
Theproblemin(6.3)canbereformulatedas
& ’
|     |     |     |     | (cid:5)≈[A B] | X =GΩ, |     |     |       |
| --- | --- | --- | --- | ------------- | ------ | --- | --- | ----- |
|     |     |     |     | X             |        |     |     | (6.8) |
Υ
sothatG(cid:3)[A B]istheaugmented operatormatrixandΩ(cid:3)[X]istheaugmented
Υ
datamatrix.

| 6.1. FormulatingDMDc |           |     |     |     |     |           |      | 95  |
| -------------------- | --------- | --- | --- | --- | --- | --------- | ---- | --- |
|                      |           | DMD |     |     |     |           | DMDc |     |
|                      | (cid:5) ≈ |     |     |     |     | (cid:5) ≈ |      |     |
| X                    |           | A   | X   |     | X   |           | G    |     |
Ω
Figure6.4. AnillustrationshowingthesizeofthematricesforDMDandDMDc. The
grayboxesaretheoperatorsthatDMDandDMDcdiscover.
DMDc of the measurement trio X, Υ, and X (cid:5) is the eigendecomposition of the
operatorAdefinedby
(cid:5)Ω†,
|     |     |     |     |     | G=X |     |     | (6.9a) |
| --- | --- | --- | --- | --- | --- | --- | --- | ------ |
& ’
†
(cid:5) X
|     |     |     |     | [A  | B]=X |     | ,   | (6.9b) |
| --- | --- | --- | --- | --- | ---- | --- | --- | ------ |
Υ
whereΩcontainsboththemeasurementandthecontrolsnapshotinformation. We
seek a best-fit solution of the operator G. Note that the size of the operator is no
longersquare,asinthecaseofAforDMD;seeFigure6.4foranillustration.
To solve for G, SVD is performed on the augmented data matrix, giving Ω =
U˜Σ˜V˜∗
. SVDisonemethodforfindingasolutionthatminimizestheFrobeniusnorm
of (cid:7)X (cid:5)−GΩ(cid:7) . The truncation value of the SVD for Ω will be defined as ˜r. The
F
truncationvalueofΩshouldbeequaltoorlargerthanX.AnapproximationofGcan
befoundusingthecomputation
(cid:5) V˜Σ˜−1U˜∗
|     |     |     |     | G=X |     |     | ,   | (6.10) |
| --- | --- | --- | --- | --- | --- | --- | --- | ------ |
∈ (cid:2)n×(n+q)
where G . Approximations of the operators A and B can be found by
| splittingtheleftsingularvectorsU˜ |      |              |              |       | intotwoseparatecomponents: |            |                      |         |
| --------------------------------- | ---- | ------------ | ------------ | ----- | -------------------------- | ---------- | -------------------- | ------- |
|                                   |      |              |              |       | (cid:5) −1                 | U˜∗        | (cid:5) −1 U˜∗],     |         |
|                                   |      |              | [A,          | B]≈[X | V˜Σ˜                       | , X        | V˜Σ˜                 | (6.11)  |
|                                   |      |              |              |       |                            | 1          | 2                    |         |
|                                   |      | (cid:2)n×˜r, | (cid:2)q×˜r, |       | U˜∗                        | [U˜∗ U˜∗]. |                      |         |
| where                             | U˜ ∈ |              | U˜ ∈         | and   | =                          |            | For high-dimensional | systems |
|                                   | 1    |              | 2            |       |                            | 1          | 2                    |         |
wheren(cid:13)1,solvingforandstoringtheoperatorscanbecomputationallyinfeasible.
Areduced-orderapproximationcanbesolvedforinstead,leadingtoamoretractable
computationalmodel. Weseekatransformationtoalower-dimensionalsubspaceon
whichthedynamicsevolve.
DMDutilizesthetruncatedsingularvectorsUtodefinethesubspaceforthereduced-
DMDccannotuseU˜
| orderapproximation. |     |     |     |     |     | tofindthelow-rankmodelofthedynamics |     |     |
| ------------------- | --- | --- | --- | --- | --- | ----------------------------------- | --- | --- |
andinputmatrixsinceU˜ isdefinedfortheinputspace,whichnowincludesboththe
InsteadofU˜,weconstructareduced-
statemeasurementsandtheexogenousinputs.
ordersubspacefromtheoutputmeasurementsX. (cid:5) Thisobservationisfundamentalto
understandingDMDcasamethod forfindingabest-fit operator between input and
outputdata.

| 96  |     |     |     |     | Chapter6. | DMDwithControl |     |
| --- | --- | --- | --- | --- | --------- | -------------- | --- |
(cid:5)
ThedatamatrixoftheoutputspaceX canbeusedtofindthereduced-ordersub-
space. AsecondSVDonX (cid:5) givesthefactorizationX (cid:5)=UˆΣˆVˆ∗ ,wherethetruncation
valueisr andUˆ ∈(cid:2)n×r,Σˆ ∈(cid:2)r×r,andVˆ∗∈(cid:2)r×m−1. ThetwoSVDswilllikelyhave
differenttruncationvaluesoftheinputandoutputmatrices ˜r and r,wheretypically
˜r >r. Usingthetransformationx=Uˆx˜,thefollowingreduced-orderapproximations
ofAandBcanbecomputed:
−1
|     |     |     | A˜ =Uˆ∗ A¯Uˆ =Uˆ∗ | X (cid:5) V˜Σ˜ | U˜∗ Uˆ, |     | (6.12) |
| --- | --- | --- | ----------------- | -------------- | ------- | --- | ------ |
1
|     |     |     | B˜=Uˆ∗ =Uˆ∗ | (cid:5) | −1 U˜∗ |     |        |
| --- | --- | --- | ----------- | ------- | ------ | --- | ------ |
|     |     |     | B¯          | X V˜Σ˜  | ,      |     | (6.13) |
2
|     | whereA˜ ∈(cid:2)r×r | andB˜∈(cid:2)r×q. | WecanthenformtheROM |      |     |     |        |
| --- | ------------------- | ----------------- | ------------------- | ---- | --- | --- | ------ |
|     |                     |                   | x˜ =A˜x˜            | +B˜u | .   |     | (6.14) |
|     |                     |                   | kF1                 | k    | k   |     |        |
SimilartoDMD,thedynamicmodesofAcanbefoundbyfirstsolvingtheeigenvalue
decompositionA˜W=WΛ.
Thetransformationfromeigenvectorstodynamicmodes
ofAisslightlymodifiedandisgivenby
−1
|     |     |     | Φ=X (cid:5) V˜Σ˜ | U˜∗ UˆW, |     |     |     |
| --- | --- | --- | ---------------- | -------- | --- | --- | --- |
(6.15)
1
wheretherelationshipbetweenΦandWissimilartothedescriptionofDMDinChap-
ter1.
| 6.2 | The DMDc | algorithm |     |     |     |     |     |
| --- | -------- | --------- | --- | --- | --- | --- | --- |
Thefollowingsectionoutlinesthealgorithmandprovidescodetocomputeeachstep.
1. Collectandconstructthesnapshotmatrices:
Collect thesystem measurementandcontrolsnapshotsandformthematrices
(cid:5) ,andΥ. StackthedatamatricesXandΥtoconstructthematrixΩ:
X,X
|     | X =   | StateData(:,1:end-1); |     |     |     |     |     |
| --- | ----- | --------------------- | --- | --- | --- | --- | --- |
|     | Xp =  | StateData(:,2:end);   |     |     |     |     |     |
|     | Ups = | InputData(:,1:end-1); |     |     |     |     |     |
|     | Omega | = [X;Ups];            |     |     |     |     |     |
ComputetheSVDoftheinputspaceΩ.
2.
ComputetheSVDofΩtoobtainthedecompositionΩ≈U˜Σ˜V˜∗ withtruncation
|     | value ˜r: |                                   |     |     |     |     |     |
| --- | --------- | --------------------------------- | --- | --- | --- | --- | --- |
|     | [U,Sig,V] | = svd(Omega,’econ’);              |     |     |     |     |     |
|     | thresh    | = 1e-10;                          |     |     |     |     |     |
|     | rtil      | = length(find(diag(Sig)>thresh)); |     |     |     |     |     |
|     | Util      | = U(:,1:rtil);                    |     |     |     |     |     |
|     | Sigtil    | = Sig(1:rtil,1:rtil);             |     |     |     |     |     |
|     | Vtil      | = V(:,1:rtil);                    |     |     |     |     |     |
(cid:5)
3. ComputetheSVDoftheoutputspaceX.
|     |                  |     | (cid:5)                   |     |     | (cid:5)≈UˆΣˆVˆ∗ |     |
| --- | ---------------- | --- | ------------------------- | --- | --- | --------------- | --- |
|     | ComputetheSVDofX |     | toobtainthedecompositionX |     |     | withtrunca-     |     |
|     | tionvalue        | r:  |                           |     |     |                 |     |

| 6.3. Examples |                   |     |     | 97  |
| ------------- | ----------------- | --- | --- | --- |
| [U,Sig,V]     | = svd(Xp,’econ’); |     |     |     |
| thresh        | = 1e-10;          |     |     |     |
r = length(find(diag(Sig)>thresh));
| Uhat   | = U(:,1:r);     |     |     |     |
| ------ | --------------- | --- | --- | --- |
| Sighat | = Sig(1:r,1:r); |     |     |     |
| Vbar   | = V(:,1:r);     |     |     |     |
oftheoperatorsG=[A B].
4. Computetheapproximation
Compute
|     |     | A˜ =Uˆ∗ (cid:5) V˜Σ˜ | −1 U˜∗ Uˆ, |         |
| --- | --- | -------------------- | ---------- | ------- |
|     |     | X                    |            | (6.16a) |
1
−1
|     |     | B˜=Uˆ∗ X (cid:5) V˜Σ˜ | U˜∗ : | (6.16b) |
| --- | --- | --------------------- | ----- | ------- |
2
n = size(X,1);
q = size(Ups,1);
| U_1 =   | Util(1:n,:);                             |     |     |     |
| ------- | ---------------------------------------- | --- | --- | --- |
| U_2 =   | Util(n+q:n+q,:);                         |     |     |     |
| approxA | = Uhat’*(Xp)*Vtil*inv(Sigtil)*U_1’*Uhat; |     |     |     |
| approxB | = Uhat’*(Xp)*Vtil*inv(Sigtil)*U_2’;      |     |     |     |
PerformtheeigenvaluedecompositionofA˜.
5.
Performtheeigenvaluedecompositiongivenby
|       |                 | A ˜ W=WΛ: |     | (6.17) |
| ----- | --------------- | --------- | --- | ------ |
| [W,D] | = eig(approxA); |           |     |        |
6. ComputethedynamicmodesoftheoperatorA.
|     |     | Φ=X (cid:5) V˜Σ˜ −1 | U˜∗ UˆW: |     |
| --- | --- | ------------------- | -------- | --- |
(6.18)
1
| Phi = Xp | * Vtil * inv(Sigtil) | *   | U_1’*Uhat * W; |     |
| -------- | -------------------- | --- | -------------- | --- |
6.3 Examples
WeillustrateDMDcappliedtotwoexamples. Thefirstexampleisanunstablesystem
that has a proportional controller stabilizing the system. The second example is a
high-dimensionalstabledynamicalsystemwithexogenousforcing.

| 98                    |         |     |     |     |     | Chapter6. | DMDwithControl |     |
| --------------------- | ------- | --- | --- | --- | --- | --------- | -------------- | --- |
| 6.3.1 Unstable linear | systems |     |     |     |     |           |                |     |
DMDccanbeutilizedtodiscovertheunderlyingdynamicsofanunstablesystemthat
has a stabilizing controller. Without the inclusion of measurements of the inputs,
DMDwouldproduceasetofstableeigenvaluesanddynamicmodes. DMDc,though,
canrecovertheunstabledynamics. Considertheunstablelineardynamicalsystem
|       | &   | ’     | &     |       | ’&  | ’ & | ’   |        |
| ----- | --- | ----- | ----- | ----- | --- | --- | --- | ------ |
|       |     | x     | =     | 1.5 0 | x   | +   | 1   |        |
|       |     | 1     |       |       | 1   |     | u , | (6.19) |
|       |     | x     |       | 0 0.1 | x   |     | 0 k |        |
|       |     | 2 k+1 |       |       | 2   | k   |     |        |
| = K[x | ]   |       | = −1. |       |     |     |     |        |
where u and K The proportional controller shifts the unstable
eigenvalue,λ=1.5,toastablevalueofλ=0.5wellwithintheunitcircle. k 1 k
Recallthat
eigenvaluesoutsidetheunitcircleinthecomplexplaneareunstablefordiscretetime
systems. Wecanproduceartificialdatafromthismodelusinganinitialconditionof
x = [4 7]T. The first five temporal snapshots can be collected in the DMDc data
0
matrices:
|     |     |          | &   |          |       | ’      |     |         |
| --- | --- | -------- | --- | -------- | ----- | ------ | --- | ------- |
|     |     |          | 4   | 2 1      | 0.5   |        |     |         |
|     |     | X=       |     |          |       | ,      |     | (6.20a) |
|     |     |          | 7   | 0.7 0.07 | 0.007 |        |     |         |
|     |     |          | &   |          |       |        | ’   |         |
|     |     | (cid:5)= | 2   | 1        | 0.5   | 0.25   |     |         |
|     |     | X        |     |          |       |        | ,   | (6.20b) |
|     |     |          | 0.7 | 0.07     | 0.007 | 0.0007 |     |         |
|     |     |          | (   |          |       | )      |     |         |
|     |     | Υ=       | −4  | −2 −1    | −0.5  |        |     |         |
|     |     |          |     |          |       | .      |     | (6.20c) |
Using the data matrices and a known input matrix B, the description of DMDc in
§ 6.1.2 can be used to discover the underlying dynamics. The SVD of X gives the
factorization
|     |     |     | &   |         |         | ’   |     |     |
| --- | --- | --- | --- | ------- | ------- | --- | --- | --- |
|     |     |     |     | −0.5239 | −0.8462 |     |     |     |
U=
|     |     |     |     |          |        | ,   |     | (6.21a) |
| --- | --- | --- | --- | -------- | ------ | --- | --- | ------- |
|     |     |     |     | −0.8462  | 0.5329 |     |     |         |
|     |     |     | &   |          |        | ’   |     |         |
|     |     |     |     | 8.2495   | 0      |     |     |         |
|     |     |     | Σ=  |          |        | ,   |     | (6.21b) |
|     |     |     |     | 0 1.6402 |        |     |     |         |
|     |     |     | ⎡   |          |        | ⎤   |     |         |
−0.9764
0.2105
|     |     |     | ⎢   |               |          | ⎥     |     |         |
| --- | --- | --- | --- | ------------- | -------- | ----- | --- | ------- |
|     |     |     | ⎢   | − 0 . 2 0 1 0 | − 0 . 80 | 4 4 ⎥ |     |         |
|     |     | V=  |     |               |          | ⎦.    |     | (6.21c) |
|     |     |     | ⎣   | −             | −        |       |     |         |
|     |     |     |     | 0 . 0 7 1 8   | 0 . 4    | 9 32  |     |         |
|     |     |     |     | −0.0330       | −0.2557  |       |     |         |
Thedatamatrices,theSVDapproximation,andthematrixBallowustocomputean
approximationtoA:
|     |     |     |     | &     |     | ’   |     |        |
| --- | --- | --- | --- | ----- | --- | --- | --- | ------ |
|     |     |     | A¯  | = 1.5 | 0   |     |     |        |
|     |     |     |     |       |     | ,   |     | (6.22) |
|     |     |     |     | 0     | 0.1 |     |     |        |
wherewerecovertheunstablelineardynamicsfromdataofthestateandcontrolsnap-
shots. DMDwouldincorrectlyrecoveranoperatorwithstableeigenvalues,whereas
DMDccancorrectlydisambiguatetheunderlyingdynamicsfromexogenousinputs.
InordertoalsorecovertheinputmatrixB,theproblemhastobeslightlymodified.
With perfect feedback control, DMDc will not be able to accurately reconstruct B,
sincetwooftherowsofΩareequivalentuptoascalingfactor. Addingasmallrandom
disturbancetothecontrollerwillbreaktheequivalence. Theformofthecontroller
can be transformed to u = K[x ] +δ , where each δ is drawn from a Gaussian
|     |     | k   |     | 1 k k |     |     |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- |

6.3. Examples 99
distributionwithzeromean. ThisallowsbothAandBtobereconstructedwhenthe
feedbackisfromaproportionalcontroller.
ALGORITHM6.1.DMDcforunstablesystemswithknownBmatrix.
%Data collection
|     | A = [1.5 0;0 | 0.1]; |     |     |
| --- | ------------ | ----- | --- | --- |
x0 = [4;7];
K = [-1];
m = 20;
DataX = x0;
DataU = [0];
B = [1;0];
|     | for j = 1 :  | m                  |                      |     |
| --- | ------------ | ------------------ | -------------------- | --- |
|     | DataX(:,j+1) | = A * (DataX(:,j)) | + B.*(K*DataX(:,j)); |     |
|     | DataU(:,j)   | = K .* DataX(1,j); |                      |     |
end
%Data matrices
X = DataX(:,1:end-1);
Xp = DataX(:,2:end);
Ups = DataU;
%SVD
|     | [U,Sig,V] = | svd(X,’econ’); |     |     |
| --- | ----------- | -------------- | --- | --- |
thresh = 1e-10;
r = length(find(diag(Sig)>thresh));
U = U(:,1:r);
Sig = Sig(1:r,1:r);
V = V(:,1:r);
%DMD
A_DMD = Xp*V*inv(Sig)*U’
|       | %DMDc - B is    | known                  |             |        |
| ----- | --------------- | ---------------------- | ----------- | ------ |
|       | A_DMDc = (Xp    | - B*Ups)*V*inv(Sig)*U’ |             |        |
| 6.3.2 | Linear dynamics | in the Fourier         | domain with | inputs |
Inthisexample,DMDcisappliedtoadynamicalsystemdefinedonalarge-scalespa-
tialgrid. Thedynamicshavealow-rankrepresentationinthetwo-dimensionalspatial
Fourierdomain,whereonlyfivemodesarechosentobenonzero. Asetofoscillating
frequenciesareassociatedwiththemodestogeneratedistinctspatiotemporalpatterns
inspaceandtime. Anexternalinputcanbeappliedtoaspatialgridlocationataspe-

100 Chapter6. DMDwithControl
(a) (b) (e)
(c) (d)
Figure 6.5. (a)illustratesonerealization oftheexamplein§6.3.2withoutactuation
overtime.(b)illustratesthesamedynamicalsystem,butwithactuation.(c)illustratestheactuation
appliedinthespatialdomain.(d)showsacomparisonbetweentheactualeigenvaluesandtheeigen-
valuesfoundfromDMDandDMDc.(e)showsfourdynamicmodesofDMDandDMDccompared
totheactualunderlyingspatialmodes[222].
cifictime. Themotivationforthisexamplecomesfromepidemiologyandinfectious
diseasespread,wherethenumberofmeasurementscanincludeasubstantialnumber
ofphysicallocations;thedynamicsoftenappeartobelowdimensional;andinterven-
tions,likevaccinationcampaigns,canbedirectedatspecificlocations.
We construct a sparse dynamical system in the two-dimensional spatial Fourier
domain. Onlyfivemodesareallowedtobenonzero. Foreachnonzeromode,alinear
dynamicalsystemisconstructedbychoosinganeigenvaluethathasbothanoscillating
componentandasmallstabledampingrate. Theboundary conditionsareperiodic,
restrictingthedynamicstothetorus. Actuationcanbeappliedtosinglepixelsinspace
andtime. Toinvestigatetheimpactoftheactuationonthefivemodes,theinputsin
spaceandtimeneedtobeinverseFouriertransformed. Thespatialgridis128×128.
Theunderlyingdynamicsofthislarge-scaledynamicalsystemcanbereconstructed
fromstateandcontrolsnapshotsusingDMDc.Figure6.5showsthedynamicbehavior
ofthefiveoscillatingmodesonthetoruswithandwithoutcontrolinthetopleftof
theillustration. Theactuationislocalizedtoasinglepixelonthetorusandisshown
inthelowerleftplot. AcomparisonoftheoutputofDMDandDMDcisshownfor
boththeeigenvaluesandthedynamicmodes. Thedynamicmodesareshownonthe
torus. DMDcisabletoreconstructtheunderlyingdynamicmodeswithhighfidelity
inthislarge-scalesystem.
6.4 Connections to system identification methods
DMDcisamodaldecompositionmethodthatdiscoverscoherentspatiotemporalmodes
from measurements of complex systems with inputs. DMD and DMDc have been
previouslyconnectedtosystemidentificationmethodsfromthecontrolcommunity
[290,222]. Anumberofimportantgeneraldifferencesexist,though,betweenDMDc
and other system identification methods. DMD and DMDc are modal decomposi-
tion methods discovering coherent spatiotemporal patterns from high-dimensional
data[247]. DMD has also been connected to Koopman spectral analysis, providing

6.5. ConnectionstoKoopmanoperatortheory 101
theoretical justification for characterizing nonlinear systems [162, 235, 195]. These
differences can be partially attributed to the originating field of study. DMD and
DMDcweredevelopedinthecontextofscientificfields,suchasfluiddynamics,where
large-scalegoverningequationsofthenonlinearsystem aredifficult toanalyze[250,
247,222]. Systemidentificationmethodsweredevelopedintheengineeringcontextof
producinglinearinput-outputmodelsforthedevelopmentofcontrollers [293,154].
Despitethesedifferences,anumberofalgorithmicsimilaritiesexist.
DMD and DMDc are intimately connected to two system identification meth-
ods: ERA and OKID, discussed in Chapter 7. These methods were originally de-
velopedforapplicationsintheaerospacecommunity,wherethenumberofmeasure-
ments collected was smaller than the rank of the system [151, 150]. ERA was also
previouslyshowntobeconnectedtoamodaldecompositionmethodcalledbalanced
properorthogonaldecomposition(BPOD),wherebothproduceequivalentbalanced
input-outputmodels[201,233,184]. ERA,though,canproducethesebalancedmod-
elsdirectlyfromdatawithout theneed forcomputationallyexpensive adjoint simu-
lations. Under impulse response experiments, DMDc and ERA are algorithmically
connected [290, 222]. OKID is a generalization of ERA when convenient impulse
response dataisunavailable [152,220,218,150]. OKIDisalso apart ofalarger set
ofsystemidentificationmethodscalledsubspaceidentificationmethods[226]. There
areanumberofconnectionsbetweenDMDcandotherpopular subspace identifica-
tionmethods,suchasN4SID,MOESP,andCVA[292,293,154,226]. Thesemethods
involveregression, modelreduction,andparameterestimation,similartoDMDc,as
describedin[226]. Withthesestrongconnectionsinthefieldofsystemidentification,
we believe DMDc is well poised to be impactful in this field for high-dimensional,
complexsystems.
6.5 Connections to Koopman operator theory
DMDhasbeenrigorouslyconnectedtotheanalysisofnonlineardynamicalsystems
through Koopman spectral analysis, as discussed in Chapter 3. In this section, we
brieflydescribehowKoopmanoperatortheorycanbegeneralizedtohandlecomplex
systems with external inputs. The generalized Koopman operator called Koopman
withinputsandcontrol(KIC)canbeconnectedtoDMDcforlinearobservablemea-
surements[223].
Considerthenonlineardynamicalsystemwithinputs
x =f(x ,u ), (6.23)
k+1 k k
wherex∈(cid:22) andu∈ ;both(cid:22) and aresmoothmanifolds. Wedefineasetof
scalar-valuedobservationfunctions g :(cid:22) ⊗ →(cid:2). Eachobservablefunctionisan
elementofaninfinite-dimensionalHilbertspace(cid:2). TheKIC(cid:3) :(cid:2) →(cid:2) actson
theHilbertspaceofobservablefunctionsgivenby
(cid:3) g(x,u)(cid:3) g(f(x,u),∗), (6.24)
where∗indicatesachoiceofdefinition,basedonthetypeofcomplexsystemunder
analysis. Thefollowingarethetwomainchoices:
1. ∗=u: Theinputsareevolvingdynamically. Theinputscouldbegeneratedby
state-dependent controllers or by externally evolving systems found in multi-
scalemodeling.

| 102 |     |     |     |     |     |     |     | Chapter6. | DMDwithControl |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --------- | -------------- | --- |
∗=0:
2. Theinputsarenotevolvingdynamically. Theinputsaffectthestatebut
couldberandomexogenousdisturbancesorimpulse-responseexperiments.
(cid:3)
Thelinear characteristics of KICallow us to perform an eigendecomposition of
giveninthestandardform:
|     |     |     | (cid:3)ϕ | (x,u)=λ | ϕ   | (x,u), | =1,2,.... |     |     |        |
| --- | --- | --- | -------- | ------- | --- | ------ | --------- | --- | --- | ------ |
|     |     |     |          |         |     |        | j         |     |     | (6.25) |
|     |     |     |          | j       | j   | j      |           |     |     |        |
The operator is now spanned by eigenfunctions that are defined on the inputs and
state. Usingtheinfiniteexpansionshownin(6.25),theobservablefunctions g canbe
j
|     | rewrittenintermsoftherighteigenfunctionsϕ |     |     |     |     |     | ,   |     |     |     |
| --- | ----------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
j
|     |     |     |     | ⎡   |     | ⎤   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
(x,u)
g
|     |     |     |         | ⎢   | 1        | ⎥   |          |        |     |        |
| --- | --- | --- | ------- | --- | -------- | --- | -------- | ------ | --- | ------ |
|     |     |     |         |     | g (x ,u) |     | (cid:7)∞ |        |     |        |
|     |     |     |         | ⎢   | 2        | ⎥   |          |        |     |        |
|     |     |     | g(x,u)= | ⎢   | .        | ⎥=  | ϕ        | (x,u)v | ,   | (6.26) |
|     |     |     |         | ⎣   | .        | ⎦   | j        | j      |     |        |
|     |     |     |         |     | .        |     | j=1      |        |     |        |
g (x,u)
p
wheren isthenumberofmeasurements. ThenewKoopmanoperatorcanbeapplied
y
tothisrepresentationofthemeasurement:
(cid:7)∞
|     |     |     | (cid:3)g(x,u)=g(f(x,u),u)= |     |     |     | λ ϕ | (x,u)v |     |        |
| --- | --- | --- | -------------------------- | --- | --- | --- | --- | ------ | --- | ------ |
|     |     |     |                            |     |     |     | j   | j      | j . | (6.27) |
j=1
NotethattheexpansionisintermsofKoopmaneigenfunctionsϕwithvector-valued
coefficientsv calledKoopmanmodes. TheterminologyofKoopmanoperatortheory
j
nowallowsformeasurementfunctionsthatacceptinputs.
| 6.5.1 KIC | for linear | systems |     |     |     |     |     |     |     |     |
| --------- | ---------- | ------- | --- | --- | --- | --- | --- | --- | --- | --- |
KICisdirectlyconnectedtoDMDcforlineardynamicalsystems. Considerthelinear
system
|     |     |     |     |     | =Ax | +Bu |     |     |     |        |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ |
|     |     |     |     | x   |     |     | .   |     |     | (6.28) |
|     |     |     |     |     | k+1 | k   | k   |     |     |        |
(x,u)=x
Wechooseasetoflinearmeasurementsonthestateandinputs,e.g., g and
|     |     |     |     |     |     |     |     |     | 1   | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
g (x,u)=u . Thelineardynamicalsystemcanberewrittenintermsofanewsetof
2 1
|     | measurementsz | :   |     |     |     |     |     |     |     |     |
| --- | ------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
k
|     |     |     |     | &     | ’   | &    |     | ’&  | ’   |         |
| --- | --- | --- | --- | ----- | --- | ---- | --- | --- | --- | ------- |
|     |     |     |     | x k+1 | =   | G    | G   | x   |     |         |
|     |     |     |     |       |     | 11   | 12  | k   | ,   | (6.29a) |
|     |     |     |     | u     |     | G    | G   | u   |     |         |
|     |     |     |     | k+1   |     | 21   | 22  | k   |     |         |
|     |     |     |     |       | z = | Gz . |     |     |     | (6.29b) |
|     |     |     |     |       | k+1 | k    |     |     |     |         |
TheeigenvaluesandeigenvectorsofGarefundamentallyconnectedtotheeigenfunc-
tionsandKoopmanmodesof(cid:3).
Thelineardynamicalsystemin(6.29)withinputs
isnotthecanonical version ofan input-output system. Thefuture statez rarely
k+1
includesthefutureinputu . Iftherearedynamicsontheinputs,theKoopmanop-
k+1
Ifnot,thedefinition∗=0shouldbeemployed.
|     | eratorwilldiscoverthem. |     |     |     |     |     |     |     |     | Thisallows |
| --- | ----------------------- | --- | --- | --- | --- | --- | --- | --- | --- | ---------- |
forareductionof(6.29)to
|     |     |     | &   | ’   | &   |     | ’&  | ’   |     |        |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ |
|     |     |     |     | x   | G   | G   |     | x   |     |        |
|     |     |     |     | k+1 | =   | 11  | 12  | k , |     | (6.30) |
|     |     |     |     | u   |     | 0 0 |     | u   |     |        |
|     |     |     |     | k+1 |     |     |     | k   |     |        |

6.5. ConnectionstoKoopmanoperatortheory 103
whichcanbefurtherreducedto
|         | &   | ’   |         |
| ------- | --- | --- | ------- |
| ( ) (   | )   |     |         |
| =       | x   |     |         |
| x k+1 G | G   | k , | (6.31a) |
11 12 u
k
| x = G | z . |     | (6.31b) |
| ----- | --- | --- | ------- |
| k+1   | k   |     |         |
Theformulationin(6.31)isequivalenttoDMDc. TheKICformulationgeneralizes
DMDcinanumberofimportantways. Systemswhereinputsaredynamicallyevolv-
ing can be considered. A larger set of observable functions, including nonlinear li-
braries,cannowalsobeconsideredsince(cid:3) isdefinedonanentiresetofobservable
functionsin(cid:2).

|     | Chapter | 7            |     |        |      |
| --- | ------- | ------------ | --- | ------ | ---- |
|     | Delay   | Coordinates, |     |        | ERA, |
|     | and     | Hidden       |     | Markov |      |
Models
ManyimportantalgorithmicconnectionsbetweenDMDandclassicalmethodsinsys-
temidentificationwillbeexploredinthischapter. Theseconnectionsprovideadeeper
understandingofDMD,enablingustoleveragepowerfultoolsfromneighboringfields
ofengineeringmathematicstodevelopextensionstoDMD.Theseextensionsaddress
known problems with DMD, such as the inabilitytocapture standingwaves or the
systematicbiasoftheDMDeigenvaluespectrawithadditivemeasurementnoise.
First,wewillexploretheuseofdelaycoordinatestoaddressthestandingwaveissue
bystackingmultipletime-shiftedcopiesofthedataintoalargeraugmentedmatrix.In
this case, the DMD algorithm is closely related to ERA, an observation first made
[290].
by Tu et al. Finally, we will explore connections between DMD and hidden
Markovmodels(HMMs).
| 7.1 | Delay coordinates |     | and | shift-stacking | data |
| --- | ----------------- | --- | --- | -------------- | ---- |
ThissectionaddressesacentralissuewithDMDthatwasfirstobservedinTuetal.[290],
wherebythestandardDMDalgorithmisincapableofaccuratelyrepresentingastand-
ingwaveinthedata. Thiswasbothsurprisingandtroublingatthetime,becauseun-
tilthen,thecommunitybelieved thatDMDwasuseful specifically toextract spatial
modesthatoscillateatasinglefixedfrequency. However,ifonlymeasurementsofa
singlesineorcosinewavearecollected,DMDfailstoreturntheconjugatepairofcom-
plexeigenvalues and insteadreturnsasinglereal eigenvalue, whichdoes notcapture
periodicoscillations. Fortunately,thereisasimpleremedythatinvolvesstackingmul-
tipletime-shiftedcopiesofthedataintoanaugmenteddatamatrix;thisisreminiscent
ofERA,aswillbediscussedinthenextsection.
| 7.1.1 | Example: | DMD fails | to capture | a standing | wave |
| ----- | -------- | --------- | ---------- | ---------- | ---- |
TodemonstratetheinabilityofDMDtocaptureastandingwaveonasimpleexample,
|     | DMDisperformedonasinglemeasurement, |     |     | x(t)=sin(t). |     |
| --- | ----------------------------------- | --- | --- | ------------ | --- |
ALGORITHM7.1.Code to demonstrate the limitation of DMD for standing
waves(DMD_standingwave.m).
|     | clear | all, close | all, clc |     |     |
| --- | ----- | ---------- | -------- | --- | --- |
105

| 106 | Chapter7. | DelayCoordinates,ERA,andHiddenMarkovModels |     |     |
| --- | --------- | ------------------------------------------ | --- | --- |
t = 0:.01:10;
x = sin(t);
plot(t,x)
X = x(1:end-1);
X2 = x(2:end);
[U,S,V] = svd(X,’econ’);
Atilde = U’*X2*V*inv(S);
[W,Lambda] = eig(Atilde);
Omega = log(Lambda)/dt
phi = X2*V*inv(S)*W;
b = (phi*exp(Omega*t))’\x’;
xdmd = b*phi*exp(Omega*t);
plot(t,xdmd,’r--’)
BecausetheXmatrixonlycontainsasinglerow,theDMDalgorithmonlyreturns
asingleeigenvalue,givenby
Omega = 0.0255
whichisunstableandclearlydoesnotcapturethesinusoidaloscillationinthedata,as
showninFigure7.1.
Tuetal.[290]reasonedthatforDMDtocaptureastandingwave,itisnecessary
tohavetwocomplexconjugateeigenvaluescorrespondingtothesineandcosinepair.
Thecorrectphaseofthesinewavesolutionisthenrecoveredbythephaseofthelinear
combination of DMD modes. To achieve this, Tu et al. [290] introduced the shift-
stackeddatamatrix,whereatime-shiftedcopyofthedataisstackedasanotherrowin
(cid:5)
thedatamatricesXandX:
|     |     | &   | ’   |     |
| --- | --- | --- | --- | --- |
···
|     |     | X= x x x m−2       |     |        |
| --- | --- | ------------------ | --- | ------ |
|     |     | 1 2 ···            | ,   | (7.1a) |
|     |     | x x x              |     |        |
|     |     | 2 3 m−1            |     |        |
|     |     | &                  | ’   |        |
|     |     | x x ··· x          |     |        |
|     |     | X (cid:5)= 2 3 m−1 | .   | (7.1b) |
···
|     |     | x x x |     |     |
| --- | --- | ----- | --- | --- |
|     |     | 3 4   | m   |     |
SincethisXmatrixcontainstworowsthatarelinearlyindependent,givenbysin(t)
andsin(t+Δt),therearetwoDMDeigenvalues.
AsweseefromtheoutputofAlgo-
rithm7.2,theseeigenvaluescomeinacomplexconjugatepair.
ALGORITHM7.2.Code to demonstrate the resolution of DMD for standing
wavesusingshift-stackeddata(DMD_standingwave.m).
Xaug = [x(1:end-2);
x(2:end-1)];
Xaug2 = [x(2:end-1);
x(3:end)];
[U,S,V] = svd(Xaug,’econ’);
Atilde = U’*Xaug2*V*inv(S);

7.1. Delaycoordinatesandshift-stackingdata 107
1
Data
DMD
| 0.5 |     |     |     | Augmented DMD |     |
| --- | --- | --- | --- | ------------- | --- |
etatS
0
-0.5
-1
| 0 1 | 2 3 | 4 5 | 6 7 | 8 9 | 10  |
| --- | --- | --- | --- | --- | --- |
Time
Figure7.1.ExampleofDMDandaugmentedDMDonastandingwaveexample.
[W,Lambda] = eig(Atilde);
Omega = diag(log(diag(Lambda)))/dt
Phi = Xaug2*V*inv(S)*W;
b = Phi\Xaug(:,1);
for k=1:length(t)
| xaugdmd(:,k) | = Phi*exp(Omega*t(k))*b; |     |     |     |     |
| ------------ | ------------------------ | --- | --- | --- | --- |
end
plot(t,real(xaugdmd(1,:)),’b--’,’LineWidth’,1.5)
| ylim([-1 1]), grid | on  |     |     |     |     |
| ------------------ | --- | --- | --- | --- | --- |
legend(’Data’,’DMD’,’Augmented DMD’)
xlabel(’Time’), ylabel(’State’)
Theeigenvaluesreturnedbythiscodeare
Omega =
1.0000i 0.0000
0.0000 - 1.0000i
NotethatwecomputeΩbytakingthenaturallogarithmofthediscrete-timeeigenval-
uesinΛanddividebythetimestepΔt =0.01.
|     |     |     | Thisaccurately | capturesthepairof |     |
| --- | --- | --- | -------------- | ----------------- | --- |
eigenvaluesassociatedwitha1Hzoscillation: ω=±i.
Thissolutiontothestandingwaveproblembecomesmoreclearifweconsidera
linearordinarydifferentialequationthatgivesrisetosuchoscillations:
x¨+x=0.
(7.2)
If we suspend variables4 by introducing x = x and x = x˙, then we obtain a two-
|     |     | 1   | 2   |     |     |
| --- | --- | --- | --- | --- | --- |
dimensionalsystemofcoupledfirst-orderequationswithtwoconjugateeigenvalues:
|     |     | & ’ & | ’& ’ |     |       |
| --- | --- | ----- | ---- | --- | ----- |
|     | d   | x 0   | 1 x  |     |       |
|     |     | 1 =   | 1    |     |       |
|     |     | −1    | .    |     | (7.3) |
|     | dt  | x     | 0 x  |     |       |
|     |     | 2     | 2    |     |       |
4Notethathereweareusingasubscriptontheunboldedx
todenotethecoordinateofthevectorx,
whereasthesubscriptontheboldedx indicatesthekthtimestep.
k

| 108 |     |     | Chapter7. |     | DelayCoordinates,ERA,andHiddenMarkovModels |     |     |     |     |
| --- | --- | --- | --------- | --- | ------------------------------------------ | --- | --- | --- | --- |
( )
|     |     |     |     |     |     | =   |     | T   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
If we stacked data from the vector x x x and performed DMD, we would
1 2
exactlycapturethepairofcomplexconjugateeigenvaluesλ=±i. However,thisap-
proachreliesonhavingaccessto x ,thederivativeofourstate. Ifatimeseriesof x
|     |     |     |     |     |     | 2   |     |     | 1   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
istheonlyavailable measurement, thenitispossible toapproximate theunderlying
dynamics,includingthederivative,byintroducinganewrowofdataconsistingofthe
shiftedintimebyΔt.
|     | measurementof |     | x   |     |     |     | Inasense,thisapproximationissimilarto |     |     |
| --- | ------------- | --- | --- | --- | --- | --- | ------------------------------------- | --- | --- |
1
afinite-differenceschemethatusesthedifferencebetweenneighboringpointsinatra-
jectorytoapproximatethederivative. Thissuggeststhatshift-stackingthedatamay
besomewhatillconditioned,althoughthishasnotbeenexploredindetail.
| 7.1.2 | Time-delay |     | coordinates |     |     |     |     |     |     |
| ----- | ---------- | --- | ----------- | --- | --- | --- | --- | --- | --- |
Delaycoordinatesrefertoanaugmentedvectorobtainedbystackingthestatexatthe
currenttimealongwithcopiesofxatfuturetimes:
⎡ ⎤
x
⎢ 1⎥
⎢x
2⎥ ⎥
|     |     |     |     |     |     | x =⎢ | .     | .   | (7.4) |
| --- | --- | --- | --- | --- | --- | ---- | ----- | --- | ----- |
|     |     |     |     |     |     | aug  | ⎣ . ⎦ |     |       |
.
x
s
Interestingly,wecanaugmentthestateeitherwithpastmeasurementsorwithfuture
measurements. Moreover,permutingtheorderofthemeasurementswillnotimpact
theDMDalgorithm,aswewillseeinChapter9.
WemaygeneralizetheaboveDMDmethodtoincludes time-shiftedstatevectors:
|     |     |     |     |     | ⎡   |     |     | ⎤   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
···
|     |     |     |     |     | x     | x   |       | x          |        |
| --- | --- | --- | --- | --- | ----- | --- | ----- | ---------- | ------ |
|     |     |     |     |     | 1     | 2   |       | m − s      |        |
|     |     |     |     |     | ⎢ x   | x   | · · · | x ⎥        |        |
|     |     |     |     |     | ⎢ 2   | 3   |       | m − s+ 1 ⎥ |        |
|     |     |     |     | X   | = ⎢   |     |       | ⎥ ,        | (7.5a) |
|     |     |     |     | aug | ⎣ . . | . . | . .   | . . ⎦      |        |
|     |     |     |     |     | .     | .   | .     | .          |        |
···
|     |     |     |     |     | x s | x s+1 |     | x m−1 |     |
| --- | --- | --- | --- | --- | --- | ----- | --- | ----- | --- |
|     |     |     |     |     | ⎡   |       |     | ⎤     |     |
· · ·
|     |     |     |     |         | x   | 2 x | 3   | x m − s + 1 |        |
| --- | --- | --- | --- | ------- | --- | --- | --- | ----------- | ------ |
|     |     |     |     |         | ⎢   |     | · · | · ⎥         |        |
|     |     |     |     |         | ⎢ x | x   |     | x ⎥         |        |
|     |     |     |     | (cid:5) | = ⎢ | 3   | 4   | m − s + 2 ⎥ |        |
|     |     |     |     | X       |     | . . | .   | . .         | (7.5b) |
|     |     |     |     | aug     | ⎣   | . . | .   | . . ⎦       |        |
|     |     |     |     |         |     | . . |     | .           |        |
···
|     |     |     |     |     | x   | x   |     | x   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     |     | s+1 | s+2 |     | m   |     |
ThereareanumberofreasonstocomputeDMDonthesedelaycoordinates. Asmen-
tionedabove,itmaybenecessarytoaugmentthestatetocapturephaseinformation
foraneigenvaluepairassociatedwithastandingwaveinthedata. Inaddition,ifthe
statemeasurementsarelowdimensional,thenitmaybenecessarytoincreasetherank
ofthematrixX throughtheuseofdelaycoordinates. Ingeneral,wemayincrease
aug
thenumbers ofdelaycoordinatesuntilthesystemreachesfullranknumerically(i.e.,
addingmorerowsonlyresultsinnewsingularvaluesthatarebelowacutoffthreshold).
PerformingDMDontheaugmentedmatricesX andX (cid:5) resultsinDMDeigen-
|     |     |     |     |     |     |     |     | aug aug |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ------- | --- |
values Λ and a set of modes Φ . The columns of Φ are much larger than the
|     |     | aug |     |     | aug |     |     | aug |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
originalmeasurements,sincetheywerestacked s times. Therefore,itisnecessaryto
extractthecurrent-stateDMDmodesfromΦ bypullingoutthefirstnrows.
aug

| 7.2. | ConnectiontoERAandHankelmatrices |     |        |     |        |          |     |     | 109 |
| ---- | -------------------------------- | --- | ------ | --- | ------ | -------- | --- | --- | --- |
| 7.2  | Connection                       |     | to ERA | and | Hankel | matrices |     |     |     |
Historically, many techniques in system identification [150, 178] were designed for
high-dimensionalsystemswithfewmeasurements. Forexample,ERAwasdeveloped
tomodelvibrationsinaerospacestructures,suchastheHubbleSpaceTelescopeand
theInternationalSpaceStation[151].ERAisbasedontheminimalrealizationtheory
ofHoandKalman[132].Incontrast,DMDwasdevelopedfornonlinearsystemswith
high-dimensionalfull-statemeasurements. However,theERAandDMDalgorithms
arequitesimilar,andwewillshowthatundersomecircumstancesDMDisaspecial
caseofERA[182,290].
ERAiswidelyusedinmodelingandcontrolbecauseofitsrelativeeaseofimple-
[184]
mentation. It has also been shown recently that ERA yields models that are
equivalenttoBPOD[299,233],whichisusefultoachieveapproximatebalancedtrun-
cation[201]onhigh-dimensionalsystems.
ERAassumesthatmeasurementsareavailablefromtheimpulseresponseofalinear
discrete-timedynamicalsystem5withactuationinputsu,outputmeasurementsy,and
aninternalstatex:
|     |     |     |     |     | =Ax   | +Bu |     |     |        |
| --- | --- | --- | --- | --- | ----- | --- | --- | --- | ------ |
|     |     |     |     |     | x k+1 | ,   |     |     | (7.6a) |
|     |     |     |     |     |       | k k |     |     |        |
=Cx
|     |     |     |     |     | y   | .   |     |     | (7.6b) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ |
|     |     |     |     |     | k   | k   |     |     |        |
Inmanycases,thedimensionofthemeasurementvectorymaybesignificantlysmaller
thanthatofthestatex.
Adiscrete-timeimpulseresponseisgivenby
%
fork=0,
= I
|     |     |     |     | u   |     |               |     |     | (7.7) |
| --- | --- | --- | --- | --- | --- | ------------- | --- | --- | ----- |
|     |     |     |     | k   | 0   | fork∈(cid:5)+ | ,   |     |       |
whichresultsinoutputmeasurements
*
fork=0,
0
|     |     |     |     | y = |        |               |     |     | (7.8) |
| --- | --- | --- | --- | --- | ------ | ------------- | --- | --- | ----- |
|     |     |     |     | k   | CAk−1B | fork∈(cid:5)+ |     |     |       |
.
(cid:5)
ThesemeasurementsareorganizedintotwoHankelmatricesHandH,therowsof
whicharetime-shiftedimpulse-responsemeasurements:
|     |     |     | ⎡   |         |      |              |        | ⎤   |        |
| --- | --- | --- | --- | ------- | ---- | ------------ | ------ | --- | ------ |
|     |     |     |     |         |      | ··· CAm−s−1B |        |     |        |
|     |     |     |     | CB      | CAB  |              |        |     |        |
|     |     |     | ⎢   |         |      | ···          | CAm−sB | ⎥   |        |
|     |     |     | ⎢   | CAB     | CA2B |              |        | ⎥   |        |
|     |     |     | H=⎢ |         |      |              |        | ⎥   |        |
|     |     |     |     | .       | .    | ..           | .      | ,   | (7.9a) |
|     |     |     | ⎣   | .       | .    | .            | .      | ⎦   |        |
|     |     |     |     | .       | .    |              | .      |     |        |
|     |     |     |     | CAs−1B  |      |              | CAm−2B |     |        |
|     |     |     |     |         | CAsB | ···          |        |     |        |
|     |     |     |     | ⎡       |      |              |        | ⎤   |        |
|     |     |     |     |         |      | ···          | CAm−sB |     |        |
|     |     |     |     | CAB     | CA2B |              |        |     |        |
|     |     |     |     | ⎢ ⎢CA2B | CA3B | ··· CAm−s+1B |        | ⎥   |        |
⎥
|     |     |     | H (cid:5)=⎢ |       |        |     |        | ⎥ . | (7.9b) |
| --- | --- | --- | ----------- | ----- | ------ | --- | ------ | --- | ------ |
|     |     |     |             | ⎣ . . | . .    | ... | . .    | ⎦   |        |
|     |     |     |             | .     | .      |     | .      |     |        |
|     |     |     |             | CAsB  | CAs+1B | ··· | CAm−1B |     |        |
5Thisdiscrete-timesystemmayalsobeinducedfromdiscrete-timesamplesofacontinuous-timesystem:
|     |     |     |     |     | d x=A | x+B    |     |     |     |
| --- | --- | --- | --- | --- | ----- | ------ | --- | --- | --- |
|     |     |     |     |     |       | c c u, |     |     |     |
dt
y=C
x,
c
(cid:6)
|     | withA=exp(A | Δt),B= | Δtexp(A | τ)B | dτ,andC=C | .   |     |     |     |
| --- | ----------- | ------ | ------- | --- | --------- | --- | --- | --- | --- |
|     |             | c      | 0       | c   | c         | c   |     |     |     |

| 110 | Chapter7. | DelayCoordinates,ERA,andHiddenMarkovModels |     |     |
| --- | --------- | ------------------------------------------ | --- | --- |
ThetermsCAkBintheHankelmatricesarecalledMarkovparametersafterthegreat
mathematician Andrey Markov. There are strong connections between the Hankel
matrix,modelreduction,andMarkovmodels,asexploredin§7.3.
TheSVDofHresultsinthedominanttemporalpatternsintermsoftheimpulse-
responsetimeseries:
∗≈U ∗
|     |     | H=UΣV | Σ V , | (7.10) |
| --- | --- | ----- | ----- | ------ |
r r r
wherethesubscriptr denotesarank-r truncation. Inasense,thecolumnsofUandV
areeigen-time-seriesthatbestdescribetheimpulseresponseacrossvarioustimescales.
Theseeigen-time-seriesmaybethoughtofasmodes,andwemayusethecoefficients
ofthesemodesasstatesinaROM.Thus,thesemodesareself-similarbuildingblocks
toreconstructthedynamics.
(cid:5)
Finally,weusetheSVDofHandthetime-shiftedH toextractalow-dimensional
approximationtoA,B,andCfrom(7.6):
|     |     | =Σ−1/2U | ∗ (cid:5) Σ−1/2, |         |
| --- | --- | ------- | ---------------- | ------- |
|     |     | A       | H V              | (7.11a) |
|     |     | r r     | +r r,r           |         |
|     |     | =Σ1/2V  | ∗ I 0            |         |
|     |     | B       | p ,              | (7.11b) |
r r
0 0
|     |     | +     | ,        |         |
| --- | --- | ----- | -------- | ------- |
|     |     | I     | 0 UΣ1/2, |         |
|     |     | C = q |          | (7.11c) |
|     |     | r 0   | 0 r      |         |
whereI isthe p×p identitymatrix,whichextractsthefirst p columns,andI isthe
p q
q×q identitymatrix,whichextractsthefirstq rows. TheERAalgorithmisprovided
inAlgorithm7.5,below.
Inpractice, itmaybedifficultorunrealistictoobtainimpulse-responsemeasure-
mentsofasystem. Therearecomplementarymethods,suchasOKID,thatapproxi-
matetheimpulseresponsefrommorerealisticinput-outputdata[152,219]byusinga
Kalmanfilter[153,297]toestimatetheMarkovparameters.
TheaboveformulationofERAisnearlyidenticaltoDMDwithfullstateobserva-
tions(i.e.,C=I,theN×N
identitymatrix),withtheactuationmatrixgivenbythe
initialcondition(i.e.,B=x ). ThisconnectionwasfirstestablishedbyTuetal.[290].
0
In this framework, it is very natural to augment the state of the DMD vector with
delaycoordinatestoincreasetherankofthesystem. Thelow-rankmodelA isalso
r
relatedtothereducedDMDmodelA˜
as
|     |     | ˜ =U   | ∗ (cid:5) Σ−1 |        |
| --- | --- | ------ | ------------- | ------ |
|     |     | A      | H V           | (7.12) |
|     |     |        | r r           |        |
|     |     | =Σ1/2A | Σ−1/2.        |        |
(7.13)
r
DMDcfrom Chapter 6 strengthens the connection between DMD and ERA by in-
cludinginputsintheDMDmodel.
Itisinterestingtonotethatasimilarapproach, calledsingularspectrum analysis
(SSA)[42,41,40,7],relatedtotheTakensembedding[273],originatedintheclimate
communitynearthesametimeasERA.SSAextractspatternsandfiltersdata,butit
is not used to identify reduced-order input-output models, as in ERA. Similar ideas
havebeenusedtoidentifycausalrelationshipsindynamicalsystems[269,307]. Non-
linearLaplacianspectralanalysis(NLSA)[110]isarecentextensionofSSAtohandle
stronglynonlineardynamics.

| 7.2. ConnectiontoERAandHankelmatrices |     |     |          |     |     |     |     |     | 111 |
| ------------------------------------- | --- | --- | -------- | --- | --- | --- | --- | --- | --- |
| 7.2.1 SimpleERA                       |     |     | examples |     |     |     |     |     |     |
Considerthedifferentialequation
|     |     |     |     |     | x˙=λx. |     |     |     | (7.14) |
| --- | --- | --- | --- | --- | ------ | --- | --- | --- | ------ |
DatafromthissystemmaybeformedintoaHankelmatrix:
|     |     |     |     | ⎡   |       |     |       | ⎤   |     |
| --- | --- | --- | --- | --- | ----- | --- | ----- | --- | --- |
|     |     |     |     | λΔt | e2λΔt | ··· | emλΔt |     |     |
e
|     |     |     |     | ⎢      |          |     |            | ⎥   |        |
| --- | --- | --- | --- | ------ | -------- | --- | ---------- | --- | ------ |
|     |     |     |     | ⎢e2λΔt | e3λΔt    | ··· | e (m+1)λΔt | ⎥   |        |
|     |     |     | H=⎢ | .      | .        |     | .          | ⎥ . | (7.15) |
|     |     |     |     | ⎣ .    | .        | ... | .          | ⎦   |        |
|     |     |     |     | .      | .        |     | .          |     |        |
|     |     |     |     | esλΔt  | (s+1)λΔt | ··· | (s+m−1)λΔt |     |        |
|     |     |     |     |        | e        |     | e          |     |        |
=
The rank of this matrix is r 1, since each row is linearly dependent on the first
λΔt
row;forexample,thesecondrowisexactlye timesthefirstrow. Similarly,every
column is linearly dependent on the first column. In this instance, augmenting the
statewithdelaycoordinatesdoesnotincreasetherankoftheHankelmatrix,andour
ROMwillstillhaveexactlyonemode.
However,ifthedynamicsaremorecomplicated,
x¨+(α+β)x˙+αβx=0,
(7.16)
sothattherearetwomodes,
|     |     |     |     | x(t)=c |     | αt+c | βt, |     |        |
| --- | --- | --- | --- | ------ | --- | ---- | --- | --- | ------ |
|     |     |     |     |        |     | e e  |     |     | (7.17) |
1 2
then the rank of the Hankel matrix increases to r = 2, illustrating the necessity of
includingatleasttworowsintheHankelmatrixtoincreasethenumberofnonzero
singularvalues:
|     | ⎡              |       |            |             |          |     |              |            | ⎤         |
| --- | -------------- | ----- | ---------- | ----------- | -------- | --- | ------------ | ---------- | --------- |
|     |                | αΔt+e | βΔt        | e2αΔt+e2βΔt |          |     | (m−s)αΔt+e   | (m−s)βΔt   |           |
|     | e              |       |            |             |          | ··· | e            |            |           |
|     | ⎢ ⎢e2αΔt+e2βΔt |       |            | e3αΔt+e3βΔt |          | ··· | (m−s+1)αΔt+e | (m−s+1)βΔt | ⎥         |
|     |                |       |            |             |          |     | e            |            | ⎥         |
| H=⎢ |                |       |            |             |          |     |              |            | ⎥ .(7.18) |
|     | ⎣              | .     |            | .           |          | ... |              | .          | ⎦         |
|     |                | . .   |            | . .         |          |     |              | . .        |           |
|     | esαΔt+esβΔt    |       | (s+1)αΔt+e |             | (s+1)βΔt | ··· | (m−1)αΔt+e   | (m−1)βΔt   |           |
|     |                |       | e          |             |          |     | e            |            |           |
Notethataddingmorethan tworowsdoesnotincrease therank of H, asshownin
Algorithm7.3.
ALGORITHM7.3.ChecktherankoftheHankelmatrixin(7.18)(ERA_test01.m).
| clear | all, | close | all, | clc |     |     |     |     |     |
| ----- | ---- | ----- | ---- | --- | --- | --- | --- | --- | --- |
t = 0:.01:10;
| x   | = exp(-t) |     | + exp(-3*t); |     |     |     |     |     |     |
| --- | --------- | --- | ------------ | --- | --- | --- | --- | --- | --- |
plot(t,x)
H = [x(1:5);
x(2:6);
x(3:7);
x(4:8);
x(5:9)];
| [U,S,V] |     | = svd(H); |     |     |     |     |     |     |     |
| ------- | --- | --------- | --- | --- | --- | --- | --- | --- | --- |
r = rank(S)

112 Chapter7. DelayCoordinates,ERA,andHiddenMarkovModels
2
1.8
1.6
1.4
1.2
1
0.8
0 0.5 1
Time
etatS
2
Data
ERA Model
1.5
1
0.5
0
0 50 100
Time
Figure7.2. Atwo-modeERAmodelcanaccuratelycapturethedynamicsofthesystem
from(7.18)withslowandfastmodes.
TheimportanceofusingtheHankelmatrixtoextractdominanttemporalsignals
fromdelaycoordinatescannotbeoverstated. Considerthecaseabovewhenα(cid:20)β,so
thattheαmodeismuchslowerthantheβmode. Usingtraditionaltime-domaintech-
niques,suchasdelaycoordinatesandconvolutionintegrals,wewouldneedatremen-
dousnumberofmeasurementstocaptureboththefastandslowtimescales. However,
theERAproceduredemonstratesthatifthereareonlytwoactivemodes,itispossible
tomodelthesystembyadifferentialequationontheamplitudesofthesetwomodes,
regardlessoftheirtimescales. Thisisadramaticreduction inthecomplexityofthe
systemdescription,andthebenefitispronouncedforproblemswithtimescalesepara-
tion. Algorithm7.4demonstratestheERAalgorithmonthisproblemwithα=−.01
andβ=−10;theresultsareshowninFigure7.2.
ALGORITHM7.4.ComputeanERAmodelfromdatain(7.18)(ERA_test01.m).
t = 0:.01:100;
x = exp(-.01*t)+exp(-10*t);
plot(t,x,’k’), hold on
H = [x(1:end-2);
x(2:end-1)];
H2 = [x(2:end-1);
x(3:end)];
[U,S,V] = svd(H,’econ’);
r = rank(S)
YY(1,1,:) = x;
[Ar,Br,Cr,Dr,HSVs] = ERA(YY,100,100,1,1,r);
sys = ss(Ar,Br,Cr,Dr,dt);
u = zeros(size(t));
u(1) = 1;
[y,t] = lsim(sys,u,t); % discrete impulse
plot(t,y,’--r’)
xlabel(’Time’), ylabel(’State’)
legend(’Data’,’ERA Model’)
ALGORITHM7.5.ERA(ERA.m).
function [Ar,Br,Cr,Dr,HSVs] = ERA(YY,m,n,nin,nout,r)
for i=1:nout

7.3. HMMs 113
for j=1:nin
Dr(i,j) = YY(i,j,1);
Y(i,j,:) = YY(i,j,2:end);
end
end
% Yss = Y(1,1,end);
% Y = Y-Yss;
% Y(i,j,k)::
% i refers to ith output
% j refers to jth input
% k refers to kth time step
% nin,nout number of inputs and outputs
% m,n dimensions of Hankel matrix
% r, dimensions of reduced model
assert(length(Y(:,1,1))==nout);
assert(length(Y(1,:,1))==nin);
assert(length(Y(1,1,:))>=m+n);
for i=1:m
for j=1:n
for Q=1:nout
for P=1:nin
H(nout*i-nout+Q,nin*j-nin+P) = Y(Q,P,i+j-1);
H2(nout*i-nout+Q,nin*j-nin+P) = Y(Q,P,i+j);
end
end
end
end
[U,S,V] = svd(H,’econ’);
Sigma = S(1:r,1:r);
Ur = U(:,1:r);
Vr = V(:,1:r);
Ar = Sigma^(-.5)*Ur’*H2*Vr*Sigma^(-.5);
Br = Sigma^(-.5)*Ur’*H(:,1:nin);
Cr = H(1:nout,:)*Vr*Sigma^(-.5);
HSVs = diag(S);
7.3 HMMs
ThereareinterestingandimportantconnectionsbetweentheDMDalgorithm,Han-
kelmatrices,andHMMs. Markovmodelsareprobabilisticallyformulateddynamical
systemsthatdescribetheevolutionofavectorofprobabilitiesthatasystemwillbein
agivendiscretestate. HMMs[230,229,89]areMarkovmodelswheretherearehidden
states,anditisonlypossibletoobservecertainrelatedquantities,referredtoasemis-
sions. Thisisanextremelypowerfulframework,andHMMsareusedtodescribemany
complextime-varyingphenomena,suchasspeechandlanguageprocessing,handwrit-
ingrecognition,andahostofotherapplications.

114 Chapter7. DelayCoordinates,ERA,andHiddenMarkovModels
Mathematically, Markov models are described in a framework that is extremely
similartotraditionaldiscrete-timedynamicalsystems. Aprobabilitystatevectorxis
avectorcontainingprobabilitiesthatthesystemisinoneofmanypossiblestates;as
such, the elements of thisvector must sum toone. The state probability is evolved
forwardintimeviaatransitionmatrixTthatservesasimilarroletotheAmatrixin
dynamicalsystems. However,thereisanimportantaddedpropertythattherowsof
thetransitionmatrixTmustalsosumtoone. Thisconstraint enforcesthefactthat
probabilitiesofsomethinghappeningmustadduptoone:
x =x T. (7.19)
k+1 k
NotethattheMarkovmodelframeworkusesRussianstandardmatrixnotation,which
isthetransposeoftheEnglishstandardfromdynamicalsystems(i.e.,inMarkovmod-
els,statesarerows,andwecomputelefteigenvectorsofTinsteadofrighteigenvectors).
Whenthestatexishidden,thesystemisobservedthroughemissions,
y =x E. (7.20)
k k
IdentifyinganunderlyingHMMfrommeasurementdataoftheemissionsismath-
ematicallysimilartotheERAprocedureabove[6,294]. Theimportantdifferenceis
thatinthecaseofanHMM,wedonotactuallymeasurethevectoryofprobabilities
ofagiven emission, but insteadwemeasure asequenceoftheemissionsthemselves.
However,wewillshowthatfromasequenceofemissionsfromanHMM,itispossible
touseERAtoreconstructtheunderlyingTandEmatrices. WhentheMarkovmodel
statesarenothidden,sothatwehavefull-statemeasurements,thenrecoveringtheun-
derlyingtransitiondynamicsinTispossibleusingDMD.Themethodsdescribedhere
arealsorelatedtotheARMAandautoregressiveexogenous(ARX)systemidentifica-
tionmethods[180,296,145].
7.3.1 Weather system example
Considerasimpleexampleconsistingofathree-stateweathersystem,wheretheweather
can either be sunny, rainy, or cloudy on a given day. Imagine that these states are
somehow hidden (maybe we don’t go out much), but we can observe the behavior
ofourdog,whichisstronglyaffectedbytheweather. Thedogmaybeeitherhappy
or grumpy, depending on the weather. The specific transition matrix and emission
matrixforthissystemareshowninFigure7.3.
A 10-day weather forecast, along with the associated probabilities of the dog’s
mood,issimulatedusingAlgorithm7.6. Figure7.4showstheevolutionoftheseprob-
abilitiesovertime. Noticethatveryquicklytheweatherandmoodprobabilitiescon-
vergetoasteadystate,becauseoftheexistenceofasingleuniteigenvalueλ=1along
withtwootherstableeigenvalues. Anyinitialconditionvariabilitywillquicklydecay
toreveal asteady-statedistributiongiven bythelefteigenvectorofTcorresponding
toλ=1.
ALGORITHM7.6.Simulate hiddenMarkovsystem(HMM_DMD.m).
clear all, close all, clc
% Weather state [S R C]: sun (S), rain (R), clouds (C)
% if sunny today: 0% sun tomorrow, 40% rain, 60% cloud
% rainy today: 25% sun tomorrow, 50% rain, 25% cloud
% cloudy today: 25% sun tomorrow, 25% rain, 50% cloud

7.3. HMMs 115
% Transition Matrix T(i,j) = Prob(i|j),
T = [0.00 0.40 0.60;
0.25 0.50 0.25;
0.25 0.25 0.50];
% x_{k+1} = x_k * T, sum(T’) = [1 1 1]
% Emissions E
% my dog is either happy (H) or grumpy (G)
% if it is sunny, dog is happy
% if it is rainy, dog is grumpy
% if it is cloudy, dog is happy 20%, dog is grumpy 80%
E = [1.0 0.0;
0.0 1.0;
0.2 0.8];
% Look at eigenvalues
[V,D] = eigs(T’); % transpose for left eigenvectors
V = V/sum(V(:,1)); % normalize probabilities = 1
%% Compute a 10-day forecast
xToday = [0 1 0]; % day 0
xHist = xToday; % keep track of all days
for i=1:10 % 10-day forecast
xTomorrow = xToday*T;
xHist = [xHist; xTomorrow];
xToday = xTomorrow;
Emissions
0
S H G
.25 .25
.4 .6
1 0 0 1 .2 .8
.25 R C S R C
.25 .5 .5
Hiddenstates
Markovmodel
⎡ ⎤ ⎡ ⎤
0.00 0.40 0.60 1.00 0.00
T
=⎣
0.25 0.50 0.25
⎦
E
=⎣
0.00 1.00
⎦
0.25 0.25 0.50 0.20 0.80
Figure7.3. HMMforaweathersystem(left)withthreestates: sunny(S),rainy(R),and
cloudy(C).Theemissions(i.e.,observations)ofthesystem(right)aremydog’sbehavior,withtwo
states:happy(H)orgrumpy(G).

| 116 |     | Chapter7. | DelayCoordinates,ERA,andHiddenMarkovModels |     |     |            |     |
| --- | --- | --------- | ------------------------------------------ | --- | --- | ---------- | --- |
|     | 1   |           |                                            |     | 1   |            |     |
|     |     |           | Sunny                                      |     |     | Happy Dog  |     |
|     | 0.8 |           | Rainy                                      |     | 0.8 | Grumpy Dog |     |
Cloudy
|     | ytilibaborP 0.6 |                      |     | ytilibaborP | 0.6                  |     |     |
| --- | --------------- | -------------------- | --- | ----------- | -------------------- | --- | --- |
|     | 0.4             |                      |     |             | 0.4                  |     |     |
|     | 0.2             |                      |     |             | 0.2                  |     |     |
|     | 0               |                      |     |             | 0                    |     |     |
|     | 0               | 5                    |     | 10          | 0                    | 5   | 10  |
|     |                 | # of Days from Today |     |             | # of Days from Today |     |     |
Figure7.4.Probabilitydistributionofthehiddenstate(left)andtheemission(right)using
a10-dayforecast.
C
Data
Correct Prediction
False Prediction
metsyS fo etatS
R
S
|     | 0   | 50  |     | 100 | 150 | 200 | 250 |
| --- | --- | --- | --- | --- | --- | --- | --- |
# of Days from Today
Figure7.5.Predictionofthehiddenstategiventhesequenceofemissionsfor250-daysimulation.
end
In a real-world system, we might not have access to T or E, and we also likely
measureasequenceofactualweatherevents,ratherthanasequenceofprobabilities.
Figure7.5showsMATLAB’spredictionforthehiddenstategivenasequenceofob-
servationsonthedog’smood. Thesuccessrateisnotperfect,butitiscertainlybetter
thanguessing. Toobtain thisestimate, wefirstgenerate asequenceof1000weather
statesalongwiththecorrespondingemissions:
N = 1000;
|     | [seq,states] | = hmmgenerate(N,T,E); |     |     |     |     |     |
| --- | ------------ | --------------------- | --- | --- | --- | --- | --- |
% ’Symbols’,{’Happy’,’Grumpy’},...
% ’Statenames’,{’Sunny’;’Rainy’;’Cloudy’})
indS = (states==1);
indR = (states==2);
indC = (states==3);
indH = (seq==1);
indG = (seq==2);
Next,itispossibletoestimatethemostprobablestatescorrespondingtotheemis-
sions,givenknowledgeofthematricesTandE:

7.3. HMMs 117
| %              | HMMVITERBI: |     | Probable                       | states | from | Emissions, | T, E |
| -------------- | ----------- | --- | ------------------------------ | ------ | ---- | ---------- | ---- |
| likelystates   |             |     | = hmmviterbi(seq,              |        | T,   | E);        |      |
| percentCorrect |             |     | = sum(likelystates==states)/N; |        |      |            |      |
IfthematricesTandEareunknown,itispossibletoestimatethemfromatraining
setofstatesandcorrespondingemissions:
| %       | HMMESTIMATE: |        | Estimate           | T,  | E from | Emissions, | States |
| ------- | ------------ | ------ | ------------------ | --- | ------ | ---------- | ------ |
| [T_est, |              | E_est] | = hmmestimate(seq, |     |        | states);   |        |
OtherusefulHMMcommandsincludethefollowing:
% HMMDECODE: Posterior state probability from Emissions, T, E
| pstates |     | = hmmdecode(seq, |     | T,  | E); |     |     |
| ------- | --- | ---------------- | --- | --- | --- | --- | --- |
% HMMTRAIN: Estimate T, E from Emissions, T_guess, E_guess...
|         | algorithm |     | isn’t great            |     | for our | data |     |
| ------- | --------- | --- | ---------------------- | --- | ------- | ---- | --- |
| T_guess |           | = T | + .001*randn(size(T)); |     |         |      |     |
| E_guess |           | = E | + .001*randn(size(E)); |     |         |      |     |
[T_est2, E_est2] = hmmtrain(seq,T_guess,E_guess,’algorithm’,’
viterbi’);
Asin control theory, it isimportant that thepair T and Eareobservable. Ifthe
emissionsEarechosenpoorly,thenthesystemisnotobservable,anditisimpossible
toinferstatesfromanemissionsequencewithoutambiguity. Thisisexploredinthe
following:
%% Observability...
rank(obsv(T’,E’))
| E_bad | =   | [.75 | .25; |     |     |     |     |
| ----- | --- | ---- | ---- | --- | --- | --- | --- |
.5 .5;
.5 .5];
rank(obsv(T’,E_bad’))
| [seq,states] |     |        | = hmmgenerate(N,T,E_bad);%,... |     |     |          |     |
| ------------ | --- | ------ | ------------------------------ | --- | --- | -------- | --- |
| likelystates |     |        | = hmmviterbi(seq,              |     | T,  | E_bad);  |     |
| [T_est,      |     | E_est] | = hmmestimate(seq,             |     |     | states); |     |
Finally,Algorithm7.7demonstrateshowtousetheDMDalgorithmtosolvefor
thetransitionmatrixTgivenfull-statemeasurements.
ALGORITHM7.7.CompareHMMswithDMD(HMM_DMD.m).
| %% Connection |         | with | DMD...       |     |           |        |     |
| ------------- | ------- | ---- | ------------ | --- | --------- | ------ | --- |
| %             | ... use | ERA  | for original |     | emissions | matrix | E   |
E = eye(3);
N = 10000;
| [seq,states] |     | =   | hmmgenerate(N,T,E); |     |     |     |     |
| ------------ | --- | --- | ------------------- | --- | --- | --- | --- |
indS = (states==1);
indR = (states==2);
indC = (states==3);
| [T_est, | E_est] |     | = hmmestimate(seq, |     | states); |     |     |
| ------- | ------ | --- | ------------------ | --- | -------- | --- | --- |
X = zeros(3,N);
for i=1:N

| 118 |             | Chapter7. | DelayCoordinates,ERA,andHiddenMarkovModels |
| --- | ----------- | --------- | ------------------------------------------ |
|     | X(seq(i),i) | = 1;      |                                            |
end
Y = X(:,2:end);
X = X(:,1:end-1);
[U,S,V] = svd(X,’econ’);
Sinv = S^(-1);
Atilde = U(:,1:3)’*Y*V(:,1:3)*Sinv;
% step 3
[W,D] = eig(Atilde);
% step 4
Phi = Y*V(:,1:3)*Sinv*W;
TheoutputoftheDMDalgorithmis
>>Atilde
|     | 0.4953 | 0.2402 | 0.6263 |
| --- | ------ | ------ | ------ |
|     | 0.2507 | 0.5038 | 0.3737 |
|     | 0.2540 | 0.2560 | 0      |
whichisclosetoT,uptoapermutationonthestatelabels. Theeigenvaluesare
>>eig(Atilde)
1.0000
0.2536
-0.2545

Chapter 8
Noise and Power
DMDsharesmanypropertieswithPODinspaceandthefastFouriertransform(FFT)
in time. It is natural to extend the power spectrum from the Fourier transform to
DMD,sothattheimportanceofaDMDmodemaybeinterpretedbyitspower. Itis
alsopossibletotruncatelow-energymodescorrespondingtosmallsingularvalues,as
inPOD.
AmajorissuewiththestandardDMDalgorithmisthesensitivityofitseigenvalue
spectrumtonoisydata. Ithasbeenshownthatthereisasystematicbiasintheeigen-
valuespectrum withtheadditionofsensor noiseonthedata, andthisbiasdoesnot
disappearasmoredataissampled[129]. TheeffectofsmallsensornoiseonDMDand
theKoopmanexpansionhasalsobeencarefullyexploredandcharacterized[12].
InadditiontotruncatingtheSVDofthedata,therearetwodominantsolutionsto
denoiseordebiastheDMDspectrum. Inthefirstmethod,byDawsonetal.[77],data
isprocessedinforwardandbackwardtimeandthenaveraged,removingthesystematic
bias. Inthesecondmethod,byHematietal.[129],theDMDalgorithmissolvedusing
a total least-squares algorithm [118] instead of the standard least-squares algorithm.
Dawsonetal.[77]provideanexcellentdiscussionofthesourcesofnoisealongwitha
comprehensiveandaccessiblecomparisonoftheproposeddenoisingalgorithms.
Themethodsadvocatedinthischaptershouldgenerallybeconsideredwithevery
application of DMD to a new dataset. In particular, we recommend judicious rank
truncation,denoisingtheDMDeigenvalues,andanalyzingthepowerspectrum.
8.1 Power spectrum
Thepowerspectrumisacentralconceptinfrequencyanalysis,providingavisualrep-
resentationofthefrequencycontentofasignal. Peaksinthepowerspectrumoccur
atfrequenciesthataredominantinthedata. Informationfromthepowerspectrum,
suchastheheightandbroadnessofpeaks,themagnitudeofthenoisefloor, andres-
onancesbetweenintegermultiplesofafrequency,canallprovidevaluablediagnostic
informationaboutasignal.
For periodic data, where the DMD eigenvalues are on the complex unit circle,
there is a direct correspondence between the power spectrum and the DMD mode
amplitude. Moregenerally,however,DMDeigenvaluesmayhaveagrowthordecay
component,makingthecomputationofaDMDpowerspectrummoreinvolved.
119

| 120 |     |     |     |     |     |     | Chapter8. | NoiseandPower |     |
| --- | --- | --- | --- | --- | --- | --- | --------- | ------------- | --- |
50
Noisy signal
Clean Signal
x(t) 0
-50
|     |     | 0   | 1   | 2 3 | 4   | 5 6 | 7   | 8 9 | 10  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
[s]
t
Figure8.1.Sumofsinessignalfrom(8.1).
| 8.1.1 | Fourier | transform |     | and power | spectrum |     |     |     |     |
| ----- | ------- | --------- | --- | --------- | -------- | --- | --- | --- | --- |
TodemonstratetherelationshipbetweentheFFTpowerspectrumandtheDMDspec-
trum,considerasimpleexamplegivenbythesumoftwosinewaves:
|     |     |     | x(t)=14sin(7×2πt)+5sin(13×2πt)+10η(t), |     |     |     |     |     | (8.1) |
| --- | --- | --- | -------------------------------------- | --- | --- | --- | --- | --- | ----- |
whereη(t)isazero-meanGaussianwhitenoiseprocesswithunitstandarddeviation.
This signal, with and without noise, is shown in Figure 8.1 and generated in Algo-
rithm8.1.
ALGORITHM8.1.Generatesumofsinessignalfrom(8.1)(FFTDMD_spectrum.m).
|     | dt = | .01; | %   | time step | of  | signal |     |     |     |
| --- | ---- | ---- | --- | --------- | --- | ------ | --- | --- | --- |
L = 10;
t = 0:dt:L;
|     | % signal:            | sum                                    | of two                    | sines                   | at  | 13 Hz and | 7 Hz |         |     |
| --- | -------------------- | -------------------------------------- | ------------------------- | ----------------------- | --- | --------- | ---- | ------- | --- |
|     | xclean               | = (14*sin(7*2*pi*t)+5*sin(13*2*pi*t)); |                           |                         |     |           |      |         |     |
|     | % add                | noise                                  | to signal                 |                         |     |           |      |         |     |
|     | x =                  | xclean                                 | + 10*randn(size(xclean)); |                         |     |           |      |         |     |
|     | ylim([-40            | 40])                                   |                           |                         |     |           |      |         |     |
|     | plot(t,x,’Color’,[.7 |                                        |                           | .3 .3],’LineWidth’,.9), |     |           |      | hold on |     |
plot(t,xclean,’k’,’LineWidth’,1.5)
|     | legend(’Noisy |     | signal’,’Clean |     | Signal’) |     |     |     |     |
| --- | ------------- | --- | -------------- | --- | -------- | --- | --- | --- | --- |
The traditional FFT power spectrum is readily computed, as in Algorithm 8.2.
Theanalogous DMD spectrum is computed in Algorithm 8.3. As in Chapter 7, to
captureastandingwave, time-shiftedcopiesofthedatamustbestacked toformthe
|     | datamatrix. | TheFFTandDMDpowerspectraarecomparedinFigure8.2. |     |     |     |     |     |     |     |
| --- | ----------- | ----------------------------------------------- | --- | --- | --- | --- | --- | --- | --- |
When computing the DMD mode amplitude, we use b = Φ†x , based on the
1
amountofm(cid:9)odeenergyexpressedinthefirstsnapshotx . Thismodeenergyisthen
1
scaledby2/ s,wheres isthenumber(cid:9)ofrowsintheshift-stackedHankelmatrix,as
Thepowerscaling2/
|     | in(7.5)and(7.9). |     |     |     |     | s appearstoholdregardlessofn,thesizeof |     |     |     |
| --- | ---------------- | --- | --- | --- | --- | -------------------------------------- | --- | --- | --- |
x.
It is interesting to note that without additive noise, the FFT and DMD spectral
|     |     |     |     | =   |     | =4  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
peaks agree perfectly (i.e., s 50 and r in Figure 8.3). However, when we add
noise, we obtain increasingly good agreement of the FFT and DMD spectra for an

8.1. Powerspectrum 121
14
FFT
12 DMD
10
8
|xˆ|
6
4
2
0
0 5 10 15 20 25 30 35 40 45 50
ω[Hz]
Figure8.2. Powerspectrumforsignalgivenbyasumoftwosinewavesat7Hzand13
Hzwithadditivewhitenoise. TheFFTpowerspectrumisshowninblack,andtheDMDspectrum
isshowninredcircles.Inthisexample,r=50singularvaluesarekeptfors=500.
15
FFT
DMD
10
|xˆ|
5
0
0 5 10 15 20 25 30 35 40 45 50
ω[Hz]
Figure8.3. TheDMDpowerspectrumisaccurateintheabsenceofsensornoiseif r =4
singularvaluesarekeptfors=50.
increasinglysquareHankel matrixoftime-delaycoordinates(i.e., s =500). Thisde-
noisingthroughtime-delaycoordinatesalsobecomesmoreimportantwhenwecom-
pute more DMD eigenvalues (e.g., r = 50). These issues of SVD rank truncation
andnumberoftime-delaycoordinatesareexploredinFigures8.2and8.4. Failureto
rank-truncatejudiciouslymayproduceunpredictableandundesiredresults,wherethe
DMDpowerspectrumbecomescorruptedbytoomanysingularvalues. Aprincipled
approachtosingularvaluetruncationwillbepresentedinthenextsection.
ALGORITHM8.2.Code to compute the FFT power spectrum of the signal in
(8.1)(FFTDMD_spectrum.m).
xhat = fft(x);
N = length(t); % number of samples
xpower = abs(xhat(1:N/2+1))*2/N;
Fs = 1/dt; % sampling frequency
freqs = Fs*(0:(N/2))/N;
plot(freqs,xpower,’k’,’LineWidth’,1.2)

| 122 |     |     |     |     |     |     | Chapter8. | NoiseandPower |     |
| --- | --- | --- | --- | --- | --- | --- | --------- | ------------- | --- |
20
FFT
DMD
15
|xˆ|
10
5
0
|     |     | 0 5 | 10  | 15  | 20  | 25 30 | 35  | 40 45 | 50  |
| --- | --- | --- | --- | --- | --- | ----- | --- | ----- | --- |
ω[Hz]
14
FFT
|     |     | 12  |     |     |     |     |     |     | DMD |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
10
8
|xˆ|
6
4
2
0
|     |     | 0 5 | 10  | 15  | 20  | 25 30 | 35  | 40 45 | 50  |
| --- | --- | --- | --- | --- | --- | ----- | --- | ----- | --- |
ω[Hz]
Figure8.4.TheDMDpowerspectrumiscorruptediftoomanysingularvaluesarekept.
|     | r=500modesarekeptwiths=500.(bottom) |     |     |     |     | =50modesarekeptwiths=50. |     |     |     |
| --- | ----------------------------------- | --- | --- | --- | --- | ------------------------ | --- | --- | --- |
|     | (top)                               |     |     |     |     | r                        |     |     |     |
ALGORITHM8.3.CodetocomputetheDMDspectrumofthesignalin(8.1)
(FFTDMD_spectrum.m).
|     | % better | denoising       | with | larger | kshift         |     |        |     |     |
| --- | -------- | --------------- | ---- | ------ | -------------- | --- | ------ | --- | --- |
|     | s = 500; | % number        | of   | times  | to shift-stack |     | signal |     |     |
|     | for k    | = 1:s           |      |        |                |     |        |     |     |
|     | X(k,:)   | = x(k:end-s+k); |      |        |                |     |        |     |     |
end
|     | [U,S,V] | = svd(X(:,1:end-1),’econ’); |     |         |              |     |        |     |     |
| --- | ------- | --------------------------- | --- | ------- | ------------ | --- | ------ | --- | --- |
|     | % keep  | 50 modes                    | and | compute | DMD spectrum |     | Lambda |     |     |
r = 50;
|     | Atilde     | = U(:,1:r)’*X(:,2:end)*V(:,1:r)*inv(S(1:r,1:r)); |     |     |            |      |     |     |     |
| --- | ---------- | ------------------------------------------------ | --- | --- | ---------- | ---- | --- | --- | --- |
|     | [W,Lambda] | = eig(Atilde);                                   |     |     |            |      |     |     |     |
|     | % convert  | eigenvalues                                      |     | to  | continuous | time |     |     |     |
|     | DMDfreqs   | = log(diag(Lambda))/dt/2/pi;                     |     |     |            |      |     |     |     |
Phi = X(:,2:end)*V(:,1:r)*inv(S(1:r,1:r))*W;
|     | % mode | amplitude | (based |     | on first | snapshot) |     |     |     |
| --- | ------ | --------- | ------ | --- | -------- | --------- | --- | --- | --- |
b = Phi\X(:,1);
|     | % need   | to scale           | power | by  | 2/sqrt(s) |     |     |     |     |
| --- | -------- | ------------------ | ----- | --- | --------- | --- | --- | --- | --- |
|     | DMDpower | = abs(b)*2/sqrt(s) |       |     |           |     |     |     |     |

8.1. Powerspectrum 123
30
20
10
x(t) 0
-10
-20
-30
0 1 2 3 4 5 6 7 8 9 10
t [s]
Figure8.5.Sumofsineswithexponentialdecaysignalfrom(8.2).
15
FFT
DMD
10
|xˆ|
5
0
0 5 10 15 20 25 30 35 40 45 50
ω[Hz]
Figure8.6.Powerspectrumforsignalgivenbyasumoftwosinewaveswithdecay.The
FFTpowerspectrumisshowninblack,andtheDMDspectrumisshowninredcircles.
scatter(abs(imag(DMDfreqs)),DMDpower,’r’)
legend(’FFT’,’DMD’)
8.1.2 DMD power spectrum for growth and decay modes
Now,considerasignalthatincludesthesumoftwosinewaves,whereoneofthesine
wavesismultipliedbyanexponentialdecayterm:
x(t)=15sin(3×2πt)+10sin(5×2πt)exp(−t/20). (8.2)
ThissignalisshowninFigure8.5. AsshowninFigure8.6,theDMDspectrum, ob-
tainedbycomputingb=Φ†x ,accuratelycapturestheamplitudeofthetwomodes,
1
whereastheFFTspectrumunderestimatestheamplitudeofthedecayingmode.
Sincethemodeisdecaying,itisnaturaltolookatwhetherornotthereisadiffer-
enceinthemodeamplitudesifcomputedusingothersnapshotsx . Figure8.7shows
k
Φ†x ,whichdecaysovertime;theaveragevalueofthisamplitudematchestheFFTam-
k
plitude. Instead,itisnecessarytoscalethisamplitudebytheeigenvalue,asΦ†x /|λ|k.
k
Thescaledmodeamplitudeaccuratelycapturesthesignalin(8.2).

| 124 |     |     |     |     |     |     |     | Chapter8. | NoiseandPower |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --------- | ------------- | --- |
12
Mode amplitude (unscaled)
11
Mode amplitude (scaled)
10
9
k
8
7
6
5
|     | 0   | 100 | 200 | 300 | 400      | 500     | 600 | 700 | 800 900 1000 |     |
| --- | --- | --- | --- | --- | -------- | ------- | --- | --- | ------------ | --- |
|     |     |     |     |     | (cid:7)b | (cid:7) |     |     |              |     |
k
Figure 8.7. DMDmodeamplitude corresponding todampedmodewithandwithout
scalingby|λ|k.
| 8.1.3 Generalized |     | DMD | power | spectrum |     |     |     |     |     |     |
| ----------------- | --- | --- | ----- | -------- | --- | --- | --- | --- | --- | --- |
Ingeneral,DMDwillbeappliedtohigh-dimensionaldatacontainingmodesthatboth
oscillateandeithergrowordecay,sothateigenvaluesareeitherrealorcomeincom-
λ=α±iβ.
plexconjugatepairs(forrealdata):
IntheearlyDMDpapers[235,64],thematrixXwasdecomposedintotheproduct
ofscaledDMDmodesandaVandermondematrixthatcapturedtheiterativeexponen-
tiationoftheDMDeigenvalues:
|     |     |     |     |     | ⎤⎡  |     |     |     | ⎤   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
⎡
|     |     |     |     |     |     | 1 λ | ··· | λm−2 |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ---- | --- | --- |
1
|     |     |     |          |                  | ⎢        | λ   | · · ·            | λ 1 −2 | ⎥        |       |
| --- | --- | --- | -------- | ---------------- | -------- | --- | ---------------- | ------ | -------- | ----- |
|     |     |     | X≈⎣      |                  | ···⎦ ⎣1  |     |                  | m      | ⎦.       |       |
|     |     |     |          | v v              |          | 2   |                  | 2      |          | (8.3) |
|     |     |     |          | 1 2              |          | . . | .                | .      |          |       |
|     |     |     |          |                  |          | . . | . .              | .      |          |       |
|     |     |     | (cid:17) | (cid:18)(cid:19) | (cid:20) | . . |                  | .      |          |       |
|     |     |     |          |                  | (cid:17) |     | (cid:18)(cid:19) |        | (cid:20) |       |
DMDmodes
Vandermondematrix
=(cid:7)v (cid:7)
Inthisformulation,thenormofamodev yieldsthemodeamplitude: b .
|     |     |     |     |     |     | k   |     |     | k   | k 2 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
InJovanovi´cetal.[149],theamplitudeoftheDMDmodesisexplicitlyseparatedinto
aproductofthenormalizedDMDmodesΦ,adiagonalmatrixofmodeamplitudes,
andtheVandermondeeigenvaluematrix:
|     |     | ⎡    |     | ⎤⎡      |     | ⎤⎡     |     |       | ⎤        |       |
| --- | --- | ---- | --- | ------- | --- | ------ | --- | ----- | -------- | ----- |
|     |     |      |     |         |     | ···    |     | λ ··· | λm−2     |       |
|     |     |      |     |         | b 0 |        | 1   |       |          |       |
|     |     |      |     | ⎢       | 1   | · · ·⎥ | ⎢   | 1     | 1 −2 ⎥   |       |
|     |     | X≈⎣φ | φ   | ···⎦ ⎣0 | b   | ⎦      | ⎣1  | λ · · | · λ m ⎦. |       |
|     |     |      |     |         | 2   |        |     | 2     | 2        | (8.4) |
|     |     |      | 1 2 |         | . . | .      | .   | . .   | .        |       |
|     |     |      |     |         | . . | ..     | .   | . .   | .        |       |
|     |     |      |     |         | . . |        | .   | .     | . .      |       |
InChapter9,wewillusethisformulationinconjunctionwiththesparsity-promoting
(cid:2)
-minimizationtofindasmallsubsetofimportantmodes.
1
From the expression in (8.4), we see that we may use the first column of X to
estimatethemodeamplitudes:
|     |     |     |     | ⎡   |     | ⎤⎡  | ⎤   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
b
⎢ 1⎥
|     |     |     |     | ≈⎣φ | φ   | ···⎦⎣b | ⎦.  |     |     |       |
| --- | --- | --- | --- | --- | --- | ------ | --- | --- | --- | ----- |
|     |     |     |     | x   |     |        | 2   |     |     | (8.5) |
|     |     |     |     | 1   | 1   | 2      | .   |     |     |       |
.
.
InMATLAB,wesolveforbby

| 8.1. Powerspectrum |     |     |     | 125 |
| ------------------ | --- | --- | --- | --- |
>> b = Phi\X(:,1);
ThepseudoinverseisusedbecausethecolumnsofΦarenotorthogonal,soitisimpossi-
bletoprojectthedataontoΦusingtheinnerproduct. NotethatthepseudoinverseofΦ
maybequitecomputationallyexpensive,especiallyifthenumberofDMDmodesr is
large. ThismaybebypassediftheSchmiddefinitionofDMDmodes[247],Φ=UW,
inPODcoefficientsα
| isused,byapplyingtheinverseofthesquarematrixWtox |     |       |     | :      |
| ------------------------------------------------ | --- | ----- | --- | ------ |
|                                                  |     |       | 1   | 1      |
|                                                  |     | x ≈Φb |     | (8.6a) |
1
|     | =⇒  | Uα ≈UWb |     | (8.6b) |
| --- | --- | ------- | --- | ------ |
1
−1α
|     | =⇒  | b≈W | .   | (8.6c) |
| --- | --- | --- | --- | ------ |
1
InMATLAB,thisbecomes
| Phi = U(:,1:r)*W;              | % DMD     | Mode from | Schmid JFM, 2010 |     |
| ------------------------------ | --------- | --------- | ---------------- | --- |
| b = Phi\X(:,1);                | % mode    | amplitude |                  |     |
| % approximation                | using POD | subspace  |                  |     |
| alpha1 = S(1:r,1:r)*V(1,1:r)’; |           |           |                  |     |
bPOD = W\alpha1;
| norm(U(:,1:r)’*X(:,1) | -   | S(1:r,1:r)*V(1,1:r)’) |     |     |
| --------------------- | --- | --------------------- | --- | --- |
norm(b-bPOD,2)
It is also possible to determine b using inexpensive computations on the POD sub-
spacewiththenewformulationofDMDmodesfromTuetal.[290],Φ=X (cid:5) VΣ−1W,
althoughthisismoreinvolved:
|     |     | x ≈Φb |     | (8.7a) |
| --- | --- | ----- | --- | ------ |
1
(cid:5) VΣ−1Wb
|     | =⇒  | Uα ≈X |     | (8.7b) |
| --- | --- | ----- | --- | ------ |
1
∗ (cid:5) VΣ−1Wb
|     | =⇒  | α ≈U X |     | (8.7c) |
| --- | --- | ------ | --- | ------ |
1
|     | =⇒  | α ≈A˜Wb |     |     |
| --- | --- | ------- | --- | --- |
(8.7d)
1
|     | =⇒  | α ≈WΛb |     |     |
| --- | --- | ------ | --- | --- |
(8.7e)
1
|     | =⇒  | b≈(WΛ)−1α |     |        |
| --- | --- | --------- | --- | ------ |
|     |     |           | .   | (8.7f) |
1
Again,inMATLAB,thisisgivenby
Phi = X(:,2:end)*V(:,1:r)*inv(S(1:r,1:r))*W;
| % mode amplitude | (based | on first | snapshot) |     |
| ---------------- | ------ | -------- | --------- | --- |
b = Phi\X(:,1);
| % approximation                | using POD | subspace |     |     |
| ------------------------------ | --------- | -------- | --- | --- |
| alpha1 = S(1:r,1:r)*V(1,1:r)’; |           |          |     |     |
bPOD = (Atilde*W)\alpha1;
| bPOD = (W*Lambda)\alpha1; |     | % equivalent |     |     |
| ------------------------- | --- | ------------ | --- | --- |
norm(b-bPOD,2)
Itisinterestingtonotethatthemodeamplitudebisbasedonthefirstsnapshotx
1
ifx isnotapproximatelyinthecolumnspaceofX (cid:5) . Inthiscase(cid:7)Φb−x (cid:7) willbe
| 1   |     |     | 1   | 2   |
| --- | --- | --- | --- | --- |
large. However,formostdatasets,suchastheflowpastacylinderofvideodata,the
modeamplitudebwillbeagoodapproximation.

126 Chapter8. NoiseandPower
8.2 Truncating data and singular value thresholding
TheDMDalgorithmisbasedontheSVDofthedata. Decidinghowmanysingular
valuestokeepandhowmanytotruncateisoneofthemostimportantchoices. This
choicedependsonmanyfactors,includingtheoriginandqualityofthedataandthe
dynamicimportanceoflow-energymodes. Ithasbeenshownthatinmanyproblems,
suchascontrolofacoustictonesinafluidflowoveranopencavity,low-energyfluid
coherentstructuresareimportantforbalancedinput-outputmodelssuitableforcon-
trol[233,236,238,140]. Typically,numericalsimulationdataisofahighenoughfi-
delitytoextracttheselow-energymodes,whereasexperimentaldatamaybecorrupted
withmeasurementnoise,makingitunclearwheretotruncate.
Inthepast,manydifferenttruncationcriteriahavebeenpresented,includinglook-
ingfor“elbows”inthesingularvalueplotonalogarithmicscaleorchoosingasingular
valuethresholdtoretain99%or99.9%ofthetotalvarianceinthedata.Thesemethods,
knownas hardthreshold techniques, retain the r largest singularvalues and singular
vectors, discarding the remaining data. Anotheralternative is soft thresholding [81],
where low-energy mode amplitudes are smoothly reduced and eventually truncated
entirely.
ArecentbreakthroughbyGavishandDonoho[106]providesatheoreticalfoun-
dation for the optimal truncation of singular values in the case of a data matrix of
measurements,Y,thatcontainssignalXplusadditivewhitenoiseerrorX :
n
Y=X+ηX , (8.8)
n
whereX isamatrixcomposedofidentical,independentlydistributedGaussianvari-
n
ableswithzeromeanandunitstandarddeviation.
In the case that Y is a square matrix of size n×n and the noise magnitude η is
known,[106]showsthattheoptimalsingularvaluethresholdτtodenoiseisgivenby
(cid:9)
4
τ= (cid:9) nη. (8.9)
3
WhenYisarectangularmatrixofsizen×m,thenthethresholdisgivenby
(cid:9)
τ=λ(β) nη, (8.10)
whereβ=m/nistheaspectratioofthematrixYandλ(β)isgivenby
- .
8β
1/2
λ(β)= 2(β+1)+ . (8.11)
(β+1)+(β2+14β+1)1/2
Inmostcases, thenoisemagnitudeηisunknownandmustbeestimateddirectly
fromtheSVDofY. Themediansingularvalueσ isusedtoestimatetheSVDof
median
thewhitenoisematrixηX . ThesingularvaluesofYthatarelargerthanthelargest-
n
noisesingularvaluearekept,whileanysingularvaluesbelowthenoisethresholdare
discarded. Inthiscase,theoptimalthresholdτisgivenby
τ=ω(β)σ , (8.12)
median
where ω(β) = λ(β)/μ and μ is the median of the Marˇcenko–Pastur distribu-
β β
tion[106]. Conveniently,thevalueofω(β)iscomputedbyafunctioninaMATLAB
codesupplementto[106]athttp://purl.stanford.edu/vg705qn9070.

| 8.2. | Truncatingdataandsingularvaluethresholding |     |     |     |     |     |     | 127 |
| ---- | ------------------------------------------ | --- | --- | --- | --- | --- | --- | --- |
|      |                                            | 104 |     |     |     | A 2 |     |     |
|      |                                            | 90% |     | 99% |     |     |     |     |
1
0
103
-1
-2
|     | σ   |     |     |     |     | -1 0 | 1 2 3 4 5 | 6 7 8 |
| --- | --- | --- | --- | --- | --- | ---- | --------- | ----- |
r 102
2
|     |     |     | A   |     |     | B   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
1
101
0
B
-1
100
-2
|     |     | 0   | 50  | 100 | 150 | -1 0 | 1 2 3 4 5 | 6 7 8 |
| --- | --- | --- | --- | --- | --- | ---- | --------- | ----- |
r
Figure 8.8. Singularvaluesforcylinderwakewithadditivenoise (left). Thesingular
valuesthatarekeptbytheoptimalhardthresholdareshowninred. The90%and99%thresholds
areshowningray.AnSVDmodethatiskept(A)iscomparedwithanSVDmodethatisdiscarded
bytruncation(B).
| 8.2.1 | Singular |     | value threshold | for | flow past | a cylinder |     |     |
| ----- | -------- | --- | --------------- | --- | --------- | ---------- | --- | --- |
Wedemonstratetheoptimalsingularvaluehardthresholdonthefluidcylinderwake
example from Chapter 2. In particular, a small amount of white noise is added to
τ
the datamatrix X, and wedemonstrate that the threshold from (8.12) identifies a
reasonablesingularvaluethreshold.
Figure8.8showstheSVDforthenoisyflowdata,andthesingularvaluesretained
afterapplyingthehardthresholdcriterionarecoloredred. Anexampleleftsingular
vector(PODmode)thatiskeptiscomparedwithamodethatisdiscarded. Thereis
acleardifferenceinqualityandsignal-to-noiseratiointhemodesthatarekeptversus
themodesthatarediscarded. Algorithm8.4determinestheoptimalthresholdvalue
andplotsthesingularvalues.
ALGORITHM8.4.Codetocomputeoptimalhardsingularvaluethresholdfrom
GavishandDonoho[106](SVHT_cylinder.m).
|     | Y       | = VORTALL | + .01*randn(size(VORTALL)); |     |           |          |           |     |
| --- | ------- | --------- | --------------------------- | --- | --------- | -------- | --------- | --- |
|     | [U,S,V] |           | = svd(Y,’econ’);            |     | % SVD     | matrix   |           |     |
|     | beta    | =         | size(Y,2)/size(Y,1);        |     | % aspect  | ratio    | of matrix |     |
|     |         | sigma =   | diag(S);                    |     | % extract | singular | values    |     |
|     | %       | optimal   | threshold                   | tau |           |          |           |     |
tau = optimal_SVHT_coef(beta,0)*median(sigma);
semilogy(sigma,’k-o’,’LineWidth’,1.2)
hold on
semilogy(sigma(sigma>tau),’ro’,’LineWidth’,1.2)

| 128              |           |        | Chapter8.    | NoiseandPower |
| ---------------- | --------- | ------ | ------------ | ------------- |
| 8.3 Compensating | for noise | in the | DMD spectrum |               |
As mentioned earlier, the DMD spectrum has been shown to be quite sensitive to
measurementnoise[77,129].
Innumericalsimulations,itisoftenpossibletoobtain
high-fidelitysnapshotdata,butinexperimentsmeasurementnoisemustbeaccounted
for. Thissection highlightstheexcellent work of Dawson etal. [77]and Hemati et
al.[129]toremovethesystematicbiasintroducedintheDMDeigenvaluesduetonoisy
measurements. DMDhasalsobeenusedtoremovenoiseinroboticapplications[26].
Ingeneral,weconsiderasetofdirectmeasurementsyofthestatexwithadditive
noisen :
k
|     |     | y =x | +n . | (8.13) |
| --- | --- | ---- | ---- | ------ |
|     |     | k k  | k    |        |
(cid:5)
In the standard DMD formulation, both data snapshot matrices Y and Y have
noise and may be expressed in terms of the true noiseless data X and X (cid:5) plus noise
(cid:5)
matricesX andX :
n n
/
Y=X+X
|     |           | n =⇒              | =Y (cid:5) Y†. |        |
| --- | --------- | ----------------- | -------------- | ------ |
|     | (cid:5)=X | (cid:5)+X (cid:5) | A              | (8.14) |
|     | Y         |                   | Y              |        |
n
TheoriginalDMDalgorithmsolvesforA usingstandardregression,whichassumes
(cid:5) Y
noise on the Y matrix but not on the Y matrix. This introduces a systematic bias,
makingtheDMDeigenvaluesofA differfromthetrueeigenvaluesofthenoiseless
Y
systemA .
X
InDawsonetal.[77],thematrixA isrelatedtotheunderlyingtruesystemA
Y X
bytheexpression
|     |     | !   | "   |     |
| --- | --- | --- | --- | --- |
−1
|     | (cid:6)(A )=A | I−(cid:6)(X | ∗)(XX ∗)−1 |     |
| --- | ------------- | ----------- | ---------- | --- |
X (8.15a)
|     | Y   | X!       | n n" |     |
| --- | --- | -------- | ---- | --- |
|     |     | I−mη2Σ−2 | −1   |     |
≈A (8.15b)
|     |     | X!       | Y " |     |
| --- | --- | -------- | --- | --- |
|     | ≈A  | I+mη2Σ−2 |     |     |
. (8.15c)
|     |     | X   | Y   |     |
| --- | --- | --- | --- | --- |
Recallthat m isthenumberofsnapshotsandη2 isthevarianceofthenoise. Eachof
theapproximationsin(8.15)reliesonasmallnoisemagnitude,anditisalsoassumed
thatthenoisematrixX iscomposedofidentical,independentlydistributedGaussian
n
entries,asin§8.2.Itisnotedin[77]thatwhenthenumberofmeasurementsisgreater
thanthenumberofsnapshots,n>m,thenXX ∗
isnotinvertible,soitisnecessaryto
workinatruncatedPODsubspacewherer <m. Ifthenoisevarianceη2isknown,it
ispossibletomanuallydebiastheexpectationofthematrixA Y andremovetheextra
I+mη2Σ−2
term. However, this removes the expectation bias but does not reduce
Y
thevariance of theDMD spectrum due tonoise. Thisisaddressed in thefollowing
sections.
Toseethesystematicbias,wehaveconstructedasimplelineardynamicalsystem,
inspiredbythesysteminDawsonetal.[77]:
|     |     | + (cid:9)   | (cid:9) ,   |        |
| --- | --- | ----------- | ----------- | ------ |
|     |     | 1/ (cid:9)3 | 1/ (cid:9)3 |        |
|     | x   | =           | x .         | (8.16) |
|     | k+1 | −1/         | 2/ k        |        |
|     |     | 3           | 3           |        |
The eigenvalues of this di(cid:9)screte-time system form a complex conjugate pair on the
λ = 3/2±1/2,
complex unit circle, indicating that the system is neutrally stable.
Figure8.9showstheeigenvaluesobtainedbythestandardDMDmethod(bluedots)

8.3. CompensatingfornoiseintheDMDspectrum 129
η=0.25,m=100 η=0.50,m=100
| 0.8 |     |     |     | 0.8 |     |
| --- | --- | --- | --- | --- | --- |
DMD
|     | (cid:4) |     | tlsDMD |     |     |
| --- | ------- | --- | ------ | --- | --- |
| 0.7 |         |     | fbDMD  | 0.7 |     |
true
| 0.6 |     |     |     | 0.6 |     |
| --- | --- | --- | --- | --- | --- |
| 0.5 |     |     |     | 0.5 |     |
#
| 0.4 |     |     |     | 0.4     |       |
| --- | --- | --- | --- | ------- | ----- |
| 0.3 |     |     |     | 0.3     |       |
| 0.2 |     |     |     | 0.2     |       |
| 0.1 |     |     |     | 0.1     |       |
| 0   |     |     |     | 0       |       |
| 0.4 | 0.6 | 0.8 | 1   | 0.4 0.6 | 0.8 1 |
"
η=0.25,m=50 η=0.50,m=50
| 0.8 |     |     |     | 0.8     |       |
| --- | --- | --- | --- | ------- | ----- |
| 0.7 |     |     |     | 0.7     |       |
| 0.6 |     |     |     | 0.6     |       |
| 0.5 |     |     |     | 0.5     |       |
| 0.4 |     |     |     | 0.4     |       |
| 0.3 |     |     |     | 0.3     |       |
| 0.2 |     |     |     | 0.2     |       |
| 0.1 |     |     |     | 0.1     |       |
| 0   |     |     |     | 0       |       |
| 0.4 | 0.6 | 0.8 | 1   | 0.4 0.6 | 0.8 1 |
Figure 8.9. Ensembles of DMD eigenvalue spectra using standard DMD, total-least-
squaresDMD(tlsDMD),andforward-backwardDMD(fbDMD)denoisingforvariousnoisemag-
nitudesηandnumbersofsnapshotsm.
withadditivesensornoise. Asystematicbiasisintroduced,forcingtheensembleeigen-
valuecloudintotheunitcircle,makingtheeigenvaluesappearstable. Increasingthe
number m ofsnapshotscollecteddecreasesthevariancebutdoesnotchangethebias
inthemean.
ALGORITHM8.5.Generatedynamics(LDS_DMD_eig.m).
% parameters
| sig = 0.5;  | % noise  | standard | deviation      |          |     |
| ----------- | -------- | -------- | -------------- | -------- | --- |
| niterations | = 500;   | %        | size of random | ensemble |     |
| m = 100;    | % number | of       | snapshots      |          |     |

| 130 |     |     |     | Chapter8. | NoiseandPower |     |
| --- | --- | --- | --- | --------- | ------------- | --- |
A = [1, 1; -1, 2]/sqrt(3);
n = 2;
X = zeros(n, m);
| X(:, | 1) = [0.5, | 1]’; |     |     |     |     |
| ---- | ---------- | ---- | --- | --- | --- | --- |
for k = 2:m,
| X(:, | k) = A | * X(:, | k-1); |     |     |     |
| ---- | ------ | ------ | ----- | --- | --- | --- |
end;
| 8.3.1 Forward/backward |     | DMD |     |     |     |     |
| ---------------------- | --- | --- | --- | --- | --- | --- |
InthefirstmethodtodebiastheDMDspectrum,weconsidertheforward-backward
[77].
DMD method of Dawson et al. A strength of this approach is its simple im-
plementation and interpretation. The main observation is that if we swap the data
matrices X and X (cid:5) and compute DMD on the pair (X (cid:5) ,X), we obtain a new propa-
gatormatrixAb
|     | forthebackward |     | dynamicalsysteminreversetime. |     | Thisbackward |     |
| --- | -------------- | --- | ----------------------------- | --- | ------------ | --- |
X
propagatormatrixshouldbetheinverseofthedirectmatrixifthisdatawasgenerated
|     |     |     | ! "  |     |     |     |
| --- | --- | --- | ---- | --- | --- | --- |
|     |     |     | = −1 |     |     |     |
byalineardynamicalsystem,sothatA Ab .
|     |     |     | X X |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
However, whennoiseisadded,and thisprocedure isrepeated on thenoisymea-
surementmatrices(Y,Y (cid:5))and(Y (cid:5) ,Y),theresultingmatricesA andAb
areonlyap-
|     |     |     |     |     | Y Y |     |
| --- | --- | --- | --- | --- | --- | --- |
proximatelyinverses. Infact,bothofthesematriceswillhavethesametypeofeigen-
valuebias,andDawsonetal.[77]goontoshowthatitispossibletoobtainadebiased
estimateoftheunderlyingmatrixA from
X
|     |     |     | (cid:4) (cid:5)   |     |     |         |
| --- | --- | --- | ----------------- | --- | --- | ------- |
|     |     |     | ≈A −1             |     |     |         |
|     |     |     | A2 Ab             |     |     | (8.17a) |
|     |     |     | X Y Y             |     |     |         |
|     |     |     | 0 (cid:4) (cid:5) | 1   |     |         |
−1 1/2
|     |     | =⇒  | ≈ Ab  |     |     |         |
| --- | --- | --- | ----- | --- | --- | ------- |
|     |     |     | A A   | .   |     | (8.17b) |
|     |     |     | X Y Y |     |     |         |
This is implemented in Algorithm 8.6, and the results are shown in Figure 8.9.
Thematrixsquarerootisnotauniqueoperation, sothereisafreedom ofchoice in
(8.17b).
It is important tonote that not only does this algorithm reduce theexpectation
biasoftheDMD eigenvalueswithnoisy data(i.e., themean oftheeigenvalue cloud
isproperlycenteredonthetrueeigenvalue),butthevarianceissignificantlyreduced.
Again,itisimportanttonotethatifthestatedimensionislarge, n (cid:13) m, itmaybe
advantageoustoworkentirelyinalow-dimensionalPODsubspace.
ALGORITHM8.6.Compute forward-backward DMD, as in Dawson et al. [77]
(DMD_eig.m).
case ’fbdmd’,
|     | % compute | forward      | DMD         |     |     |     |
| --- | --------- | ------------ | ----------- | --- | --- | --- |
|     | [U, S,    | V] = svd(Y,  | ’econ’);    |     |     |     |
|     | f_Atilde  | = U’ *       | Yp * V / S; |     |     |     |
|     | % compute | backward     | DMD         |     |     |     |
|     | [U, S,    | V] = svd(Yp, | ’econ’);    |     |     |     |

| 8.3. CompensatingfornoiseintheDMDspectrum |              |     |     |     |                   | 131 |
| ----------------------------------------- | ------------ | --- | --- | --- | ----------------- | --- |
|                                           | LeastSquares |     |     |     | TotalLeastSquares |     |
| y                                         |              |     |     | y   |                   |     |
|                                           |              |     | x   |     |                   | x   |
Figure 8.10. Schematic illustrating the geometric difference between the least-squares
algorithm(left)andthetotalleast-squaresalgorithm(right).
|             | b_Atilde      | = U’ *           | Y * V /          | S;  |        |     |
| ----------- | ------------- | ---------------- | ---------------- | --- | ------ | --- |
|             | % estimate    | forward/backward |                  | DMD |        |     |
|             | Atilde =      | (f_Atilde        | * inv(b_Atilde)) |     | ^ 0.5; |     |
| 8.3.2 Total | least-squares | DMD              |                  |     |        |     |
Now,weconsiderthetotalleast-squaresDMDalgorithmofHematietal.[129]. This
algorithmisbasedontheaboveobservation thatstandardDMDsolvesforA using
Y
(cid:5)
regression,whichassumesnoiseonYbutnotonY.
Thetotalleast-squaresalgorithm[117,118,94,95,291,115]isanextensionofthe
standardSVD-basedleast-squaresregression[114,54,116,119]thatassumesnoiseon
bothmatrices:
(cid:5)=A
|     |     |     | Y Y |     |     | (8.18a) |
| --- | --- | --- | --- | --- | --- | ------- |
Y
(cid:5)+X (cid:5)
|     |     | =⇒  | X   | =A (X+X | ).  | (8.18b) |
| --- | --- | --- | --- | ------- | --- | ------- |
|     |     |     | n   | Y       | n   |         |
In particular, the total least-squares algorithm solves an optimization that finds the
best-fit solution A that simultaneously minimizes the Frobenius norms of X (cid:5) and
|     | Y   |     |     |     |     | n   |
| --- | --- | --- | --- | --- | --- | --- |
X . ThisisshownschematicallyinFigure8.10.
n
Thisoptimizationturnsouttoberelativelystraightforward.Westackthematrices
(cid:5)
YandY intoanewmatrixZandtaketheSVD:
& ’
Y
|     |     |     | Z= =U   | Σ V | ∗ . | (8.19) |
| --- | --- | --- | ------- | --- | --- | ------ |
|     |     |     | (cid:5) | Z Z | Z   |        |
Y
Now,theleftsingularvectorsinU arepartitionedintofourequalquadrants:
Z
|     |     |     | +       | ,   |     |        |
| --- | --- | --- | ------- | --- | --- | ------ |
|     |     |     | U       | U   |     |        |
|     |     |     | U = Z,a | Z,b | .   | (8.20) |
|     |     |     | Z U     | U   |     |        |
|     |     |     | Z,c     | Z,d |     |        |

132 Chapter8. NoiseandPower
Finally,thenewtotalleast-squaresestimateforA isgivenby
Y
A =U U† . (8.21)
Y Z,c Z,a
ThisalgorithmisshowninAlgorithm8.7,andtheresultingdebiasedeigenvaluesare
showninFigure8.9.
ALGORITHM8.7.Code to compute total least-squares DMD, as in Hemati et
al.[129](DMD_eig.m).
case ’tlsdmd’,
% stack
Z = [Y; Yp];
% tls DMD
[U, ~, ~] = svd(Z, ’econ’);
U11 = U(1:r, 1:r);
U21 = U(r+1:end, 1:r);
Atilde = U21 * inv(U11);

Chapter 9
Sparsity and DMD
DMDhasbeensuccessfullyappliedtoextractunderlyinglow-rankpatternsfromhigh-
dimensionaldatageneratedbycomplexsystems. Theselargedatasetstypicallyconsist
ofhigh-dimensionalspatial measurementsacquiredatalargenumberofsnapshotsin
time. ExamplesofsystemsthathavebeenamenabletoDMDanalysisincludefluids,
epidemiologicalsystems,neuralrecordings,andimagesequences. Ineachcase,thedata
exhibitslow-rankspatiotemporalcoherentstructures,whichareidentifiedbyDMD.
Thefactthatdynamicsevolveonalow-dimensionalattractordefinedbyspatiotem-
poral coherentstructures suggeststhatthedynamicsaresparse inan appropriate co-
ordinatesystem. Recentadvancesincompressedsensingprovideamethodology,un-
derpinnedbyafirmtheoreticalfoundation,toexploitthissparsityandgreatlyreduce
measurements. Thereisatremendousopportunitytousecompressed sensingindy-
namicalsystems,andDMDprovidesanumberofexcitingrecentadvancesinthisdi-
rection.
TherearetwomajorwaysinwhichsparsityhasrecentlyenteredDMDanalysis.
First,becauseofthenonorthogonalityofDMDmodes,itisoftendifficulttochoosean
appropriatelow-rankDMDrepresentation. Therefore,itmaybebeneficialtoidentify
asparsesubsetofDMDmodesthatbalancesthetrade-offbetweenaccuracyofrepre-
sentationandnumberofmodes[149]. Compressedsensingprovidesefficientcompu-
tationofthesecriticalmodes,asopposedtoalternativesusingnonconvexoptimization
thatdonotscalewithlargeproblems[64].
Thesecondopportunitytoexploitsparsityismotivatedbythedifficultyinacquir-
ingtime-resolvedmeasurementswithhighspatialresolution. Thisapproachrelieson
therecentobservationthattemporallysparsesignalsmaybesampledconsiderablyless
oftenthansuggestedbytheShannon–Nyquistsamplingfrequency[209,255];theidea
alsogeneralizestospatiallysparsesignals,whichmaybesampledbelowtheresolution
determined by the highest wavenumber. Reducing the number of measurements is
significant for applications, such as fluid dynamics, where data acquisition is expen-
sive,andsometimesprohibitive. PIVisanexperimentaltechniquetoimagefluidsand
extractatimeseriesofvelocityfields. Time-resolvedPIVmaybequiteexpensivefor
certainflowsbecauseofmultiscalephenomenainbothspaceandtime;PIVsystemsare
typicallylimitedbythebandwidthfordatatransferbetweentheCCD(charge-coupled
device)andRAM.Reducingthespatialmeasurementswouldinturnreducethedata-
transferrequirementsforeachtimesnapshot,increasingthetemporal samplingrate.
133

134 Chapter9. SparsityandDMD
Therearealsoapplicationswhereindividualsensorsmaybeexpensive,suchasocean
samplingandatmosphericmonitoring.
Inthischapter, wereview themodern theory ofcompressed sensing[82,58,60,
59,17,18]andinvestigatethebenefitofincorporating sparsitytechniquesinDMD.
Inparticular,wehighlightrecentworkthathasleveragedcompressedsensingfortem-
porally[289]andspatially[48]enhancedDMD.
9.1 Compressed sensing
Compressedsensingisarecenttechniquethatexploitsthesparsityofasignalinsome
basistoachievefullsignalreconstructionwithsurprisinglyfewmeasurements[82,58,
60,59,17,18]. TheShannon–Nyquistsamplingtheorem[209,255]suggeststhatto
resolveasignalperfectly,itmustbesampledattwicetherateofthehighestfrequency
present. However,thisrestrictiononlyappliestosignalswithbroadband frequency
content, and it may be relaxed if the signal is sparse in some basis, meaning that its
vector representation contains mostly zeros. A signal x ∈ (cid:2)n is K-sparse in a basis
Ψ∈(cid:2)n×n
if
x=Ψs (9.1)
andshasexactlyK nonzeroelements.
Mostnaturalsignalsaresparseinsomebasis,asevidencedbytheircompressibility.
Images and audio signals are compressible in Fourier or wavelet bases, so that after
takingtheFourierorwavelettransform,themajorityofthecoefficientsaresmalland
maybesetexactlyequaltozerowithnegligiblelossofquality. Thiscompressibilityis
theprinciplebehindJPEGcompressionforimagesandMP3compressionforaudio.
Manycomplex, high-dimensional systemsdescribedbypartial differential equations
alsoexhibit low-rank structure, asthedynamicsevolveon alow-dimensionalattrac-
tor[133]. Thesparsityinherentinnonlinearpartialdifferentialequationspresentsan
opportunity to reduce theburden of measurements in characterizing system behav-
ior[245].
IfthesignalxisK-sparseinΨ,theninsteadofmeasuringxdirectlyandthencom-
pressing,itispossibletocollectasubsampleofmeasurementsandsolveforthenonzero
elementsofsinthetransformbasis. Considerarestrictedsetofmeasurementsy∈(cid:2)p
withK< p(cid:20)n:
y=Cx. (9.2)
ThematrixC∈(cid:2)p×n representsasetof plinearmeasurementsonthestatex.6 These
measurementsmayberandomprojectionsofthestate,inwhichcasetheentriesofC
areGaussian-distributedrandomvariables. Alternatively,wemaymeasureindividual
entriesofx,i.e.,singlepixelsinthecasewherexisanimage,inwhichcasetherows
ofCarefullofzerosexceptforasingleunitentryperrow.
Ifweknowthesparsevectors,thenwecanreconstructthefullstatexusing(9.1).
Wemaythussolvethefollowingsystemofequationsfors,givenmeasurementsyand
knowledgeofthesparsebasisΨ andmeasurementmatrixC:
y=CΨs. (9.3)
6ThematrixCisoftenreferredtoasΦinthecompressed-sensingliterature.WealreadyuseΦtodenote
theDMDmodes,andweinsteadchooseCtobeconsistentwiththeoutputequationincontroltheory.

9.1. Compressedsensing 135
Thissystemofequationsisunderdetermined,andthereareinfinitelymanysolutions
s. Weseekthesparsestsolutionˆsthatsatisfiestheoptimizationproblem
ˆs=argmin(cid:7)s(cid:7) , suchthaty=CΨs, (9.4)
0
s
where(cid:7)s(cid:7) isthenumberofnonzeroelementsins. Unfortunately,theoptimization
0
in(9.4)isnonconvexandcanonlybesolvedthroughabrute-forcesearch. Thecom-
putationalcomplexityofthissearchiscombinatorialinnandK,makingitanonpoly-
nomial(NP)timeproblem. Therefore,solving(9.4)isinfeasibleforevenmoderately
large n and K, and our abilitytosolve largerproblems doesnot scalewith Moore’s
law.
Fortunately,therecentadventofcompressedsensingprovidesconditionsonwhich
wemayrelax(9.4)toaconvex(cid:2) -minimization[59,82]:
1
ˆs=argmin(cid:7)s(cid:7) , suchthaty=CΨs. (9.5)
1
s
(cid:2)
The(cid:2) -norm is defined by (cid:7)s(cid:7) = n |s |, which is the sum of the absolute value
1 1 j=1 j
of the elements. The minimization in (9.5) willalmost certainly result in the sparse
solutionto(9.4)aslongasthefollowingtwoconditionshold:
1. The measurement matrix C must be incoherent with respect to the basis Ψ,
meaningthattherowsofCareuncorrelatedwiththecolumnsofΨ.
2. We must collect (cid:23)(Klog(n/K)) measurements [57, 58, 17]. The specific con-
stantmultiplierdependsonhowincoherentCandΨ are.
Theseconditionsguarantee thatthematrixproductCΨ satisfiesarestrictedisometry
property(RIP)forK-sparsevectorss:
(1−δ )(cid:7)s(cid:7)2≤(cid:7)CΨs(cid:7)2≤(1+δ )(cid:7)s(cid:7)2, (9.6)
K 2 2 K 2
whereδ istherestrictedisometryconstant. TheRIPmeansthatCΨactsasanearly
K
unitarytransformationonK-sparsevectors,preservingrelativedistances,whichisthe
keyobservationguaranteeingalmostcertainsignalreconstructionfrom(9.5).Thefact
thatCΨ isapproximately unitary on K-sparse vectors will play acritical rolein the
compressed-sensing approximation totheSVD,andthereforeincompressed-sensing
DMD.
SamplingStrategies
Another significant result of compressed sensing is that there are generic sampling
matricesCthataresufficientlyincoherentwithrespecttonearlyalltransformbases.
Specifically,BernoulliandGaussianrandommeasurementmatricessatisfytheRIPfor
agenericbasisΨ withhighprobability[60]. Thereareadditionalresultsgeneralizing
theRIPandinvestigatingincoherenceofsparsematrices[111].
Inmanyengineeringapplications,itisadvantageoustorepresentthesignalxina
genericbasis,suchasFourierorwavelets. Onekeyadvantageisthatsingle-pointmea-
surementsareincoherentwithrespecttothesebases,excitingabroadbandfrequency
response. Samplingatrandompointlocationsisappealinginapplicationswhereindi-
vidualmeasurementsareexpensive,suchasinoceanmonitoring.
A particularly useful transform basis for compressed sensing is obtained by the
SVD,7 resultinginatailoredbasisinwhichthedataisoptimallysparse[166,36,15,
7TheSVDprovidesanoptimallow-rankmatrixapproximation,anditisusedinPCAandPOD.

136 Chapter9. SparsityandDMD
43]. Atruncated SVDbasis mayresult inmoreefficient signalrecovery fromfewer
measurements. Progress has been made in developing a compressed SVD and PCA
based on theJohnson–Lindenstrauss (JL)lemma[146,97,225,112]. TheJLlemma
iscloselyrelatedtotheRIP,indicatingwhenitispossibletoembedhigh-dimensional
vectorsinalow-dimensionalspacewhilepreservingspectralproperties.
AlternativeComputationalConsiderations
In addition to the (cid:2) -minimization in (9.5), there are alternative approaches based
1
on greedy algorithms [284, 286, 205, 112] that determine the sparse solution of (9.3)
throughaniterativematchingpursuitproblem. Forinstance,thecompressed-sensing
matchingpursuit(CoSaMP)[205]iscomputationallyefficient,easytoimplement,and
freelyavailable.
When the measurements y have additive noise, say white noise of magnitude (cid:20),
therearevariantsof(9.5)thataremorerobust:
ˆs=argmin(cid:7)s(cid:7) , suchthat(cid:7)CΨs−y(cid:7) <(cid:20). (9.7)
1 2
s
Arelatedconvexoptimizationis
ˆs=argmin(cid:7)CΨs−y(cid:7) +λ(cid:7)s(cid:7) , (9.8)
2 1
s
whereλ≥0isaparameterthatweightstheimportanceofsparsity. (9.7)and(9.8)are
closelyrelated[285].
9.1.1 Example: Temporal compressed sensing
Asasimpleexampletodemonstratecompressedsensing,considerthefollowingtwo-
tonesignalintime:
f(t)=sin(73×2πt)+sin(531×2πt). (9.9)
Toresolvethehigh-frequencycomponentat531Hz,theShannon–Nyquistsampling
theoremstatesthatwemustsamplethesignalatarateofatleast1062samples/second.
Forsimplicityandeaseofvisualization,let’sassumethatwecollect4096measurements
inaone-secondinterval,whichisjustunderfourtimestheShannon–Nyquistsampling
rate. Thus,x∈(cid:2)4096isshowninFigure9.1(a);however,thissignalisextremelysparse
in the Fourier domain, having exactly two nonzero frequency components (Figure
9.1(c)). Ifwerandomlysamplethissignalat128samples/second(Figure9.1(b)),which
isaboutoneeighthoftheShannon–Nyquistrate,weobtainthecompressedmeasure-
menty=Cx=CΨs,wherey∈(cid:2)128 andΨ istheinverse discretecosinetransform
(iDCT). Finally, using CoSaMP [205] to solve the compressed-sensing problem, we
mayapproximatethesparsevectorsandreconstructthefullsignal(redcurves,Figure
9.1(c)and(d)).8
ALGORITHM9.1.Temporalcompressedsensing.
%% Generate signal
n = 4096, p = 128;
t = linspace(0, 1, n);
8CoSaMPrequirestheusertospecifyadesiredsparsitylevel,andweuseK=10.

9.2. Sparsity-promotingDMD 137
| (a) (cid:4)      |     | (b) (cid:4)      |
| ---------------- | --- | ---------------- |
| (cid:3)          |     | (cid:3)          |
| f (cid:2)        |     | f (cid:2)        |
| (cid:239)(cid:3) |     | (cid:239)(cid:3) |
| (cid:239)(cid:4) |     | (cid:239)(cid:4) |
(cid:2) (cid:2)(cid:1)(cid:4) (cid:2)(cid:1)(cid:5) (cid:2)(cid:1)(cid:6) (cid:2)(cid:1)(cid:7) (cid:3) (cid:2)(cid:1)(cid:4)(cid:5) (cid:2)(cid:1)(cid:4)(cid:6) (cid:2)(cid:1)(cid:4)(cid:7) (cid:2)(cid:1)(cid:4)(cid:8) (cid:2)(cid:1)(cid:4)(cid:9)
Time[s] Time[s]
| (c) 1500 |     | (d) (cid:4) |
| -------- | --- | ----------- |
(cid:3)
1000
DSP
f (cid:2)
500
(cid:239)(cid:3)
| 0   |     | (cid:239)(cid:4) |
| --- | --- | ---------------- |
0 200 400 600 800 1000 (cid:2)(cid:1)(cid:4)(cid:5) (cid:2)(cid:1)(cid:4)(cid:6) (cid:2)(cid:1)(cid:4)(cid:7) (cid:2)(cid:1)(cid:4)(cid:8) (cid:2)(cid:1)(cid:4)(cid:9)
Frequency[Hz] Time[s]
Figure9.1.Temporalcompressedsensingonasparsetwo-tonetime-domainsignal(black,
(a)–(c)). Thecompressed-sensingreconstruction(red,(c)–(d))isquiteaccurate,evenwithsampling
roughlyoneeighththeShannon–Nyquistrate.Randommeasurementsareshowninredin(b).
| x = sin(73*2*pi*t)   | + sin(531*2*pi*t); |     |
| -------------------- | ------------------ | --- |
| %% Randomly sample   | signal             |     |
| perm = round(rand(p, | 1) * n);           |     |
y = x(perm)’;
| %% Form matrix operators |                 |          |
| ------------------------ | --------------- | -------- |
| Psi = dct(eye(n,         | n));            |          |
| CPsi = Psi(perm,         | :);             |          |
| %% L1 minimization       | (through linear | program) |
s = cosamp(CPsi,y,10,1.e-10,10);
| xreconstruct = idct(s); |     |     |
| ----------------------- | --- | --- |
| 9.2 Sparsity-promoting  | DMD |     |
TheDMDmodeamplitudesareusefulquantitiesfordeterminingtheimportanceof
modesinreconstructingagivendataset,asdiscussedinChapter8. Themodeampli-
tudesshouldnotbeconfusedwiththemodenorms,whichareequaltounity. Deter-
miningthemodeamplitudesisstraightforward,althoughthedescriptioninJovanovi´c
etal.[149]providesadeeperinterpretation,whichwewilldiscusshere. Thesemode
amplitudesareoftenusedtoranktheimportanceofmodes,similartothepowerspec-
truminFourieranalysis.

| 138               |     |        |            |                |                                         |     | Chapter9. |     | SparsityandDMD |     |
| ----------------- | --- | ------ | ---------- | -------------- | --------------------------------------- | --- | --------- | --- | -------------- | --- |
| 9.2.1 Amplitude   |     | of DMD | modes      |                |                                         |     |           |     |                |     |
|                   |     |        | ˜ (cid:3)U | ∗ (cid:5) VΣ−1 |                                         |     |           |     |                |     |
| ThereducedmatrixA |     |        |            | X              | determinesalow-rankdynamicalsystemonthe |     |           |     |                |     |
vectorx˜=U ∗
xofPODcoefficients:
=A˜x˜
|     |     |     |     |     | x˜ k+1 | .   |     |     |     | (9.10) |
| --- | --- | --- | --- | --- | ------ | --- | --- | --- | --- | ------ |
k
LetWbethematrixwhosecolumnsareeigenvectorsofA˜ andΛbethediagonalmatrix
˜
ofeigenvalues. IfAisdiagonalizable, i.e., ithas r linearlyindependenteigenvectors
comprisingcolumnsofamatrixW,thenwemaywriteitas
|     |     |     |     | A˜  | =WΛW | −1. |     |     |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- | --- | --- | --- |
(9.11)
Now,ifweusethedefinitionofDMDmodesfromSchmid[247],Φ=UW,then
|     |     |     | (   |     |     |     |     | )   |     |         |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------- |
|     |     | X≈U | x˜  | x˜  | x˜  | ··· | x˜  |     |     | (9.12a) |
|     |     |     |     | 1 2 | 3   |     | m)  |     |     |         |
(
|     |     |     | =U  | A˜x˜ | A˜2x˜ | ··· | A˜m−1x |     |     |         |
| --- | --- | --- | --- | ---- | ----- | --- | ------ | --- | --- | ------- |
|     |     |     | x˜  |      |       |     |        |     |     | (9.12b) |
|     |     |     |     | 1( 1 | 1     |     | 1      |     | )   |         |
Λm−1W
|     |     |     | =UW | W −1x˜ | ΛW −1x˜ | ···   |     | −1x˜ |     | (9.12c) |
| --- | --- | --- | --- | ------ | ------- | ----- | --- | ---- | --- | ------- |
|     |     |     |     | ( 1    |         | 1     | )   | 1    |     |         |
|     |     |     | =UW | b Λb   | ···     | Λm−1b | .   |      |     | (9.12d) |
Here,b=W −1x˜
|     |     | isthevectorofDMDmodeamplitudes. |     |     |     |     |     | Withabitofmanipulation, |     |     |
| --- | --- | ------------------------------- | --- | --- | --- | --- | --- | ----------------------- | --- | --- |
1
itispossibletowritethisas
|     |     |      |     | ⎤⎡        |         | ⎤⎡     |         |          | ⎤      |        |
| --- | --- | ---- | --- | --------- | ------- | ------ | ------- | -------- | ------ | ------ |
|     |     | ⎡    |     |           |         | ···    | λ       | ··· λm−1 |        |        |
|     |     |      |     | b         | 0       |        | 1       |          |        |        |
|     |     |      |     |           | 1       |        | 1       |          | 1      |        |
|     |     | X≈⎣φ |     | ···⎦ ⎢ ⎣0 | b       | · · ·⎥ | ⎢ ⎣1 λ  | · · · λ  | m −1 ⎥ |        |
|     |     |      | φ   |           | 2       | ⎦      | 2       |          | ⎦.     | (9.13) |
|     |     |      | 1 2 |           |         |        |         |          | 2      |        |
|     |     |      |     |           | . . . . | . ..   | . . . . | . .      | . .    |        |
|     |     |      |     |           | . .     |        | . .     | .        | .      |        |
ItispossibletoobtainthevectorofDMDmodeamplitudesaccordingtotheformula
b=W −1x˜ ,derivedabove.9
However,thestepfrom(9.12a)to(9.12b)assumesthatthe
1
locallylinearDMDapproximation isvalid, which mayonlybeapproximately true.
Wemayinsteadsearchfortheoptimalbthatminimizesthe(cid:2) errornormbetweenX
2
andtheapproximationin(9.13),asin[149].
ThisinvolvessolvingaRiccatiequation
tominimizeacostfunctionJ(b);detailsareprovidedin[149].
| 9.2.2 Sparse | DMD | mode | amplitudes |     |     |     |     |     |     |     |
| ------------ | --- | ---- | ---------- | --- | --- | --- | --- | --- | --- | --- |
The cost function may be modified with a sparsity-promoting term to balance the
(cid:7)b(cid:7)
trade-off between the number of modes, , and the accuracy of reconstruction,
| J(b): |     |     |     |     |     | 0   |     |     |     |     |
| ----- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
argminJ(b)+γ(cid:7)b(cid:7)
|     |     |     |     |     |     |     | .   |     |     | (9.14) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ |
0
b
However,thisexpression isnonconvex, because (cid:7)b(cid:7) isameasureofthecardinality,
0
whichinvolvesanonpolynomialtimesearch. Theminimizationabovemayberelaxed
toaconvex(cid:2)
-minimizationinspiredbycompressedsensing:
1
argminJ(b)+γ(cid:7)b(cid:7)
|     |     |     |     |     |     |     | .   |     |     | (9.15) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ |
1
b
Afterthespecificsparseelementsofbaredetermined,afinalleastsquaresregression
isperformedtodeterminethebestvaluesforthesesparsecoefficients.
9ThisisthedefinitionofDMDmodeamplitudeadoptedbymanyauthors.

9.3. Sub-NyquistsampledDMD 139
9.3 Sub-Nyquist sampled DMD
Therequirement of time-resolved measurements (at or above the Shannon–Nyquist
sampling rate) for DMD is a severe limitation for many applications. For instance,
in experimental fluid dynamics, fast sampling using PIV requires high-power lasers
and high-speed cameras, which can be prohibitively expensive. Moreover, there are
hardwarelimitsonthebandwidthfromthecameraCCDtosystemmemory,which
determineanupperboundonthecombinedspatialandtemporalresolution.
Compressedsensinghasrecentlybeenusedtoobtaintime-resolvedPIVfromnon-
time-resolvedmeasurements[15,289]. In[257],compressedsensingisusedtoobtain
highertemporal resolutioninvideoMRI,basedonpriorstudiescombiningsparsity
andlineardynamicsforvideo[240,213]. Basedontheconnectionbetweenthemeth-
ods in [257], using Hankel matrices and minimal realization theory [132], and the
existingconnectionbetweenDMDandERA,thesemethodsmaybeadaptedintothe
DMDcontext.
InTuetal.[289],compressedsensingisspecificallyusedonunderresolvedPIVdata
withthegoalofcomputingDMD.Inparticular,Tuetal.[289]demonstratedtheabil-
ity to compute dominant-frequency DMD modes from dramatically undersampled
PIVdatafromexperimentsofflowpastacylinderatlowReynoldsnumber. Amajor
contribution of their work was the observation that a low-rank subspace, based on
PODmodes,couldbebuiltfromunderresolveddata,andthentemporalcompressed
sensingcouldbeappliedtoreconstructtime-resolvedcoefficientsofthesemodes. The
alternative,whichisperformingtemporal compressedsensingontheentirefluidve-
locityfield,wouldbeprohibitivelyexpensive.
9.3.1 Algorithm
For consistency with the notation in the next section, we deviate slightly from the
notationinTuetal.[289]. Denotetime-resolveddatabyX andsub-Nyquistsampled
R
databy X = X P, where P ∈ (cid:2)m×q isa matrix whose columns consist of q select
S R
columnsfromtheidentitymatrix. ThischoiceofPachievesthedesiredsubsampling
intime,withatotalofq samples;however,allofthefollowingdiscussiongeneralizes
forPunitary,asdiscussedin§9.4.2.
IfthedataX hassufficientlylowrank r,andifthecolumnsofPsampletimein
R
asufficientlyrandom (orpseudorandom) manner,thenX willhavethesamePOD
S
modesasX :
R
X =U Σ V ∗ =U Σ V ∗ P. (9.16)
S S S S R R R
Now,considerthePODmodecoefficientsbasedonsub-Nyquistsampleddata:
β =U ∗ X (9.17a)
S S S
=U ∗ X P (9.17b)
S R
=β P. (9.17c)
R
Eachrowofβ isatime-historyofagivenPODmodecoefficient.10 Thesub-Nyquist
S
sampledDMDalgorithmreliesonthefactthatthemodecoefficientsforthedominant
PODmodesaresparseinthefrequencydomain,sothat
β =β P (9.18a)
S R
=βˆ ΨP, (9.18b)
R
10Notethatthisdiffersfrom[289],whichusesthetransposeofthismatrix.

| 140 |     |     | Chapter9. | SparsityandDMD |     |
| --- | --- | --- | --------- | -------------- | --- |
whereΨisadiscreteFouriertransform.11 SinceΨandPareincoherent,itispossibleto
reconstructthesparsesolutiontoβˆ fromsub-Nyquistsamplesβ
usingcompressed
|     |     | R   |     | S   |     |
| --- | --- | --- | --- | --- | --- |
sensing.
Finally,thecompressed-sensingsolutionto(9.18)ismorecomplicatedthanin§9.1.1,
becausewearesolvingforasparsevector-valuedsignal(i.e.,asetofsparsePODmode
coefficients). Therefore,thefollowingconvexminimizationisemployed:
argmin(cid:7)βˆT
|     | (cid:7) | , suchthatβ | =βˆ ΨP. |     | (9.19) |
| --- | ------- | ----------- | ------- | --- | ------ |
|     | R       | 1,l         | S R     |     |        |
βˆ
R
Here,(cid:7)·(cid:7) isamixednormthatweightsbothcolumnsparsityandcoherenceacross
1,l
columns:12
|     |     |  2  |     |     |     |
| --- | --- | --- | --- | --- | --- |
3
|                    |                   | (cid:7)m   (cid:7)q | 1/l   |     |        |
| ------------------ | ----------------- | ------------------- | ----- | --- | ------ |
|                    |                   |                     |       |     |        |
|                    | (cid:7)β(cid:7) = |   |β                | |l    |     |        |
|                    |                   |                     |  .    |     | (9.20) |
|                    | 1,l               |                     | ij    |     |        |
|                    |                   | i=1 j=1             |       |     |        |
| 9.4 Compressed DMD |                   |                     |       |     |        |
Now,weleveragecompressedsensingtoreconstructfull-stateDMDmodesfromfew
spatialmeasurements,basedon[48].
Thisisrelatedtootherusesofcompressedsens-
inginMRI[277,257]andPIV[217,15]. Twomajoralgorithmsaredevelopedinthis
section:
1. Compressed DMD: If full-state snapshot data is available, it is possible to com-
press the data, compute DMD on the compressed data, and reconstruct full-
stateDMD modes by linearlycombining full-state snapshots according tothe
compressedDMDtransformations. ThisismuchfasterthancomputingDMD
onthefull-statedataandhasbeenusedtoacceleratethereal-timeprocessingof
videostreamsusingDMD[91],relatedtoChapter4.
2. Compressed-sensing DMD:Ifonlycompressed measurementsareavailable(pro-
jectedorsubsampledfromthefulldata),itispossibletocomputeDMDonthe
projecteddataandthenreconstructfull-stateDMDmodesbycompressedsens-
ingonprojectedDMDmodes.
ThesemethodsdemonstratetheabilitytoperformDMDusingmuchlessdataas
longasthesnapshotsandDMDmodesaresparseinsomebasis. Thefirstalgorithm
providesatremendouscomputationalbenefitiffull-statesnapshotsareavailable,and
thesecondmethodprovidesanalternativerouteifheavilysubsampleddataisavailable.
BothmethodsresultinDMDeigenvaluesthatagreecloselywiththefull-stateDMD
eigenvalues,meaningthattheyfaithfullyreconstructthelow-dimensionalmodel.
Both algorithms rely on a set of theoretical advances built on the invariance of
DMDtounitarytransformation. AnimmediateoutcomeisthatDMDmaybeequiv-
alentlycomputedinthespatialdomain,Fourierdomain,orPODcoordinatesystem,
sincetheyareallrelated byunitarytransformations. Wethenleveragethisobserva-
tion toshow asimilar invarianceof projected DMD when themeasurement matrix
andsparsebasissatisfytheRIP,justifyingtheuseofcompressedsensing.
11ThisisthediscreteFouriertransform,asopposedtotheinversetransformin§9.1.1,becauseweare
compressingrowsinsteadofcolumns.
12NotethatwehavetransposedβˆT
sothatwemayusethesamenormasin[289].
R

| 9.4. CompressedDMD      |     |     |     |     |     |     | 141 |
| ----------------------- | --- | --- | --- | --- | --- | --- | --- |
| 9.4.1 General procedure |     |     |     |     |     |     |     |
Both methods ofcompressed DMDinvolve output-projected data Y,Y (cid:5) , whereY =
| (cid:5)=CX | (cid:5) | ∈ (cid:2)p×n |     |     |     |     |     |
| ---------- | ------- | ------------ | --- | --- | --- | --- | --- |
CX and Y , and C is the measurement matrix. Interestingly, these
(cid:5)
compressed measurements Y and Y may be viewed as observable functions in the
KoopmanframeworkfromChapter3.
(cid:5)
ItispossibletocomputeDMDonthepairY,Y,astheyarealsorelatedbyamatrix
A :
Y
(cid:5)=A
|     |     |     | Y   | Y,  |     |     | (9.21) |
| --- | --- | --- | --- | --- | --- | --- | ------ |
Y
| whereA isrelatedtoA |     | ,thematrixfromfullDMDonX,X,by |     |       |     | (cid:5) |        |
| ------------------- | --- | ----------------------------- | --- | ----- | --- | ------- | ------ |
| Y                   |     | X                             |     |       |     |         |        |
|                     |     |                               | CA  | =A C. |     |         | (9.22) |
|                     |     |                               | X   | Y     |     |         |        |
Inthefollowing,weassumethatthecolumnsofXandX (cid:5) aresparseinatransform
| basisΨ,sothatX=ΨSandX |     |     | (cid:5)=ΨS (cid:5) |     | (cid:5)            |     |        |
| --------------------- | --- | --- | ------------------ | --- | ------------------ | --- | ------ |
|                       |     |     | ,whereSandS        |     | havesparsecolumns. |     | Wealso |
assumethatthemeasurementsCareincoherentwithrespecttoΨ. Thiswillholdif
Ψ
isaninverseFouriertransformandrowsofCconsistofpointmeasurements,and
itwillalsoholdformoregeneralbasesΨ
aslongasCisaGaussianrandommeasure-
ment matrix [60]. Finally, we assume that each column of X and X (cid:5) is in the same
Ψ,
sparse subspace ofthebasis guaranteeing thatPOD modesU and DMDmodes
X
Φ arealsointhesamesparsesubspace. Thefirsttwoconditionsmakeitpossibleto
X
reconstruct columns of X and X (cid:5) directlyfrom Y and Y (cid:5) using compressed sensing,
althoughthisisinefficient.
Figure9.2showsthetwoprimarypaths,dependingonwhatdatawehaveaccessto:
Algorithm9.2(CompressedDMD)andAlgorithm9.3(Compressed-sensingDMD).
ALGORITHM9.2.CompressedDMD.
(cid:5)
Thisalgorithmstartswithfull-statedataX,X.
|                       |     | (cid:5) (cid:5) |                    |     |       |     |     |
| --------------------- | --- | --------------- | ------------------ | --- | ----- | --- | --- |
| (i) CompressX,X       |     | toY,Y.          |                    |     |       |     |     |
| (ii) ComputeDMDon(Y,Y |     |                 | (cid:5))toobtain(Λ | ,W  | )andΦ | .   |     |
|                       |     |                 |                    | Y   | Y     | Y   |     |
(iii) Reconstruct
|     |     |     |       | (cid:5) Σ−1W |     |     |        |
| --- | --- | --- | ----- | ------------ | --- | --- | ------ |
|     |     |     | Φ˜ =X | V            | .   |     | (9.23) |
|     |     |     | X     | Y Y          | Y   |     |        |
ALGORITHM9.3.Compressed-sensingDMD.
(cid:5)
Here,weonlyhaveoutput-projecteddataY,Y.
|                     |     | (cid:5) | toobtain(Λ |     | )andΦ |     |     |
| ------------------- | --- | ------- | ---------- | --- | ----- | --- | --- |
| (i) ComputeDMDonY,Y |     |         |            | ,W  |       | .   |     |
|                     |     |         |            | Y Y | Y     |     |     |
Perform(cid:2) -minimizationonΦ tosolveΦ =CΨΦ forΦ (andhenceΦ
| (ii)               |         |     |     |     |     |     | ).  |
| ------------------ | ------- | --- | --- | --- | --- | --- | --- |
|                    | 1       |     | Y   | Y   |     | S S | X   |
| 9.4.2 Mathematical | details |     |     |     |     |     |     |
ImportantmathematicaldetailsexplainingtheutilityofcompressedsensingforDMD
are presented here. However, for a full treatment, including relevant proofs, please
referto[48].

| 142 |      |     | Chapter9. | SparsityandDMD |     |
| --- | ---- | --- | --------- | -------------- | --- |
|     | Data |     | Modes     |                |     |
DMD
|     | (cid:5) |     | Λ ,Φ |     |     |
| --- | ------- | --- | ---- | --- | --- |
X,X
|     |     |            | X    | X   |     |
| --- | --- | ---------- | ---- | --- | --- |
|     |     | Alg.       | 9.2: |     |     |
|     | C   | Compressed |      |     |     |
DMD
|     | (cid:5) |     | Λ ,Φ |     |     |
| --- | ------- | --- | ---- | --- | --- |
Y,Y
|     |     |     | Y   | Y   |     |
| --- | --- | --- | --- | --- | --- |
Alg. 9.3: Compressed-SensingDMD
Figure9.2.SchematicofcompressedDMD(Algorithm9.2)andcompressedsensingDMD
(Algorithm9.3)astheyrelatetodata X,X(cid:5) andprojecteddataY,Y(cid:5). Cisaprojection downto
measurementsthatareincoherentwithrespecttothesparsebasis. Reprintedwithpermissionfrom
theAmericanInstituteofMathematicalSciences[48].
Thefirst major result isthateigenvectors φ ofA project toeigenvectors Cφ
|     |     |     | x X |     | x   |
| --- | --- | --- | --- | --- | --- |
withthesameeigenvalueλ.
ofA Thisresultisverifiedusing(9.22)above,whichis
provenasalemmain[48]: Y
|     | CA φ =A | Cφ =⇒ | λCφ =A | Cφ . | (9.24) |
| --- | ------- | ----- | ------ | ---- | ------ |
|     | X x     | Y x   | x Y    | x    |        |
Thisrelationshipistrueforalleigenvectorsφ
ofA ,whicharemorenumerousthan
x X
the eigenvectors of A , and so the above relationship holds trivially for φ in the
|     | Y   |     |     |     | x   |
| --- | --- | --- | --- | --- | --- |
nullspaceofC.Typically,therankrofXisrelativelysmallcomparedwiththenumber
ofsnapshotsmorthenumberofoutputmeasurements p,sothattherelevantr DMD
eigenvaluesandmodesaresharedbybothA andA .
X Y
BasedontherelationshipbetweenDMDeigenvectorsofA andA ,itispossible
X Y
toreconstructφ fromφ =CΨφ ,whereφ isasparserepresentationofφ inΨ.
|     | x y | s   | s   |     | x   |
| --- | --- | --- | --- | --- | --- |
InvarianceofDMDtounitarytransformations
An important observation is that DMD is invariant to left and right unitary trans-
formationsofthedataXandX. (cid:5) Relaxingtheconditionofunitarity,andinsteadre-
placingitwitharestrictedisometryproperty,isakeystepinconnectingDMDwith
compressedsensing.
=
It is straightforward to verify that if C is unitary, then the SVD of Y CX is
relatedtotheSVDofX=UΣV ∗
:
|     |     | Y=CUΣV | ∗ . |     | (9.25) |
| --- | --- | ------ | --- | --- | ------ |
|     |     |        |     | =   | ∗ =    |
The left singular vectors of Y are given by CU. Similarly, if Y XP , then Y
UΣV ∗ P ∗ . Animmediateresultoftherightinvariancetounitarytransformationisthat

| 9.4. | CompressedDMD |     |     |     |     |     |     |     |     | 143 |
| ---- | ------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
(cid:5)
DMDisinvarianttocoordinatedshufflingofthecolumnsofXandX,asdiscussedin
detailin[48].
Here, we focus on left transformations C of X because this is most relevant to
compressedDMD.
[48]).
Theorem 9.1 (Reproduced from The DMD eigenvalues are invariant to left
transformationsCofdataXifCisunitary,andtheresultingDMDmodesareprojected
throughC.
Proof. ExactDMDproceedsasfollows:
∗
|     |             | 1. Y=CUΣV    |            | .                  |                |                |           |              |     |     |
| --- | ----------- | ------------ | ---------- | ------------------ | -------------- | -------------- | --------- | ------------ | --- | --- |
|     |             | ˜            | =U ∗       | ∗ (cid:5) VΣ−1=U   | ∗              | (cid:5) VΣ−1=A | ˜         |              |     |     |
|     |             | 2. A         |            | C Y                |                | X              | .         |              |     |     |
|     |             |              | Y          |                    |                |                | X         |              |     |     |
|     |             | 3. Thepair(Λ |            | ,W                 | )isthesameas(Λ |                | ,W        | )sinceA˜ =A˜ | .   |     |
|     |             |              |            | Y Y                |                |                | X X       | Y            | X   |     |
|     |             | 4. Φ         | =Y (cid:5) | VΣ−1W=CΦ           | .              |                |           |              |     |     |
|     |             | Y            |            |                    | X              |                |           |              |     |     |
|     | Therefore,Φ |              |            | istheprojectionofΦ |                |                | throughC: | Φ =CΦ        | .   |     |
|     |             |              | Y          |                    |                | X              |           | Y            | X   |     |
Thereare anumber of important consequences ofthis result. First, thediscrete
Fouriertransform$ andtheprincipalcomponentscoordinatetransformU(leftsin-
gularvectorsofSVD)arebothunitarytransformations.Therefore,DMDmodescom-
puted inthespatial domain arerelated tothose computed in theFourier domainor
$
in a principal components coordinate system by or U, respectively. The DMD
eigenvaluesremainunchanged.
IfweconsiderdataX,X (cid:5) thatissparseinΨ,wemayrelaxtheconditionthatCis
Instead,CmustbeincoherentwithrespecttoΨ,sothatCΨ
|     | unitary. |     |     |     |     |     |     |     | satisfiesaRIP. |     |
| --- | -------- | --- | --- | --- | --- | --- | --- | --- | -------------- | --- |
(cid:5))andreconstruct
|       | Thisallowsustocompute          |     |        |        | DMDon    |     | projected | data(Y,Y    |        | full-state |
| ----- | ------------------------------ | --- | ------ | ------ | -------- | --- | --------- | ----------- | ------ | ---------- |
|       | DMDmodesbycompressedsensingonΦ |     |        |        |          |     | =CΦ       | =CΨΦ        |        |            |
|       |                                |     |        |        |          |     | Y         | X           | S .    |            |
| 9.4.3 | Example:                       |     | Sparse | linear | dynamics |     | in        | the Fourier | domain |            |
ThissystemisdesignedtotestthecompressedDMDalgorithmsinawell-controlled
=5nonzero
|     | numericalexperiment. |     |     |     | WeimposesparsitybycreatingasystemwithK |     |     |     |     |     |
| --- | -------------------- | --- | --- | --- | -------------------------------------- | --- | --- | --- | --- | --- |
two-dimensional spatial Fourier modes; all other modes are exactly zero. It is also
possibletoallowtheotherFouriermodestobecontaminatedwithGaussiannoiseand
imposeaveryfaststabledynamicineachofthesedirections. Wethendefineastable
K
lineartime-invariant dynamical system on the modes. Thisisdone by randomly
choosingatemporaloscillationfrequencyandasmallbutstabledampingrateforeach
ofthemodesindependently. Inthisway,weconstructasysteminthespatialdomain
thatisalinearcombinationofcoherentspatialFouriermodes,eachofwhichoscillates
atadifferentfixedfrequency. Table9.1containsthespecificvaluesforthisexample.
Figure9.3showsasnapshotofthissystematt =2. WeseethatthefivelargeFourier
modecoefficientsgeneratedistinctspatialcoherentpatterns. Figure9.4showsthefive
Fouriermodes(real and imaginaryparts) thatcontribute tothespatial structuresin
Figure9.3.
Thisexampleisconstructedtobeanidealtestcaseforcompressed-sensingDMD.
Thelineartime-invariantsystemunderlyingthesedynamicsischosenatrandom,so
the data matrix X will contain significant energy from many of the modes. There-
fore, POD does not separate the spatial modes, as shown in Figure 9.5(a). Instead,

| 144 |     |     | Chapter9. | SparsityandDMD |
| --- | --- | --- | --------- | -------------- |
Fouriercoefficients
Spatialmodes
4 5
21 3
Spatialmodes
Figure 9.3. Schematic illustrating the dynamical system in the example in § 9.4.3.
FivecoefficientsintheFourierdomainaredrivenwithalineardynamicalsystem, givingriseto
therichspatial dynamics shown. Fifteenpoint sensorsare placedrandomly in space. For video,
seewww.siam.org/books/ot149/torus. ReprintedwithpermissionfromtheAmericanInstituteof
MathematicalSciences[48].
Table9.1. Parametersofsystemintheexamplein§9.4.3,visualizedinFigure9.3. In-
dividualmodesareobtainedbyconstructinganoscillatinganddecayingFouriermode(witheigen-
valueλ=d+iω),xˆ(I,J)=eλt! =edt(co"s(ωt)+isin(ωt)),andtakingtherealpartoftheinverse
|     | x(t)=real | $−1(xˆ) |     |     |
| --- | --------- | ------- | --- | --- |
Fouriertransform: . ReprintedwithpermissionfromtheAmericanInstitute
ofMathematicalSciences[48].
|     | Mode I | J d =Real(λ) | ω=Imag(λ)   | Initial   |
| --- | ------ | ------------ | ----------- | --------- |
|     | #      | (damping)    | (frequency) | condition |
|     | 1 2    | 2 -0.0880    | 4.7893      | -0.5357   |
|     | 2 1    | 3 -0.0524    | 8.2214      | 0.9931    |
|     | 3 6    | 2 -0.0258    | 9.7120      | -0.5434   |
|     | 4 1    | 5 -0.0637    | 6.8953      | -0.4914   |
|     | 5 3    | 6 -0.0175    | 7.1518      | -2.0610   |
PODextractsstructuresbasedontheirvarianceinthedata. SincePODisinvariantto
permutationofthecolumns,theunderlyingtemporalstructureisnotreflectedinthe
PODstructures. SinceeachofourFouriermodesisoscillatingatafixedanddistinct
frequency,thisisidealforDMD,whichisolatesthespatiallycoherentFouriermodes
exactly, asshowninFigure9.5(b). Thisexampleisgenerated withAlgorithm9.4in
§9.5below.
Inthecaseofnobackgroundnoise,thecompressed-sensingDMDalgorithmworks
extremelywell,asseeninthemodereconstructioninFigure9.5(c). Additionally,the
methodofcompressedDMDstartingwithfull-statesnapshots,compressing,perform-
ingDMD,andthenreconstructingusingformula(9.23),resultsinaccuratereconstruc-
tion,showninFigure9.5(d). BothcompressedsensingDMDandcompressedDMD
matchthetrueeigenvaluesnearlyexactly,asshowninFigure9.6.
TheX,X (cid:5) datamatricesareobtainedon a128×128spatial gridfrom times0to

9.4. CompressedDMD 145
Mode1 Mode2 Mode3 Mode4 Mode5
Real
Imag
Figure 9.4. Spatiotemporal coherent modes corresponding to nonzero Fourier modes.
ReprintedwithpermissionfromtheAmericanInstituteofMathematicalSciences[48].
Table9.2. AccuracyofeigenvaluesandmodesforvariousDMDmethodsintheexample
in§9.4.3.ReprintedwithpermissionfromtheAmericanInstituteofMathematicalSciences[48].
Mode1 Mode2 Mode3 Mode4 Mode5
rorreeulavnegiE
|
˜λ−
λ|
k
k
Standard 1.635e-13 1.025e-12 1.091e-12 6.238e-13 1.676e-13
Compressed 1.358e-13 5.266e-12 7.597e-13 9.729e-13 4.115e-13
Compressed
1.358e-13 5.266e-12 7.597e-13 9.729e-13 4.115e-13
Sensing
rorrEedoM (cid:7)
φ˜−
φ(cid:7)
2
k
k
Standard 1.219e-13 4.566e-13 1.227e-13 1.661e-11 1.370e-12
Compressed 7.333e-14 6.269e-13 2.347e-13 1.004e-11 5.727e-12
Compressed
7.542e-14 7.954e-13 2.289e-13 8.142e-12 3.858e-12
Sensing
2inincrementsofΔt =0.01,sothatX∈(cid:2)16384×200. Weuse p =15measurements;
randomlyplacedsingle-pixelmeasurementsandmeasurementsobtainedbytakingthe
dotproductofaGaussianorBernoullirandomvectorwiththestatevectorxallyield
accurateDMDeigenvaluesandmodes.
Theaccuracyofthecompressedandcompressed-sensingDMDmethodsinrecon-
structingDMDmodesandeigenvaluesissummarized inTable9.2. Theaccuracy of
thestandardDMDmethodisalsoincluded,sincethisexamplewasconstructedfrom
a true low-rank linear model on FFT modes, providing an explicit solution. Since
the DMD modes in this example are in complex conjugate pairs, and these modes
haveaphasedifference fromthetrueFFTmodes, wecomparethemagnitudes. For
eachofthefivemodes,thecorrectFFTmodalwavenumberisidentified,andallother
wavenumbersarezero. ThemodeerrorinTable9.2arisesfromsmalldifferencesin
themagnitudeof the singlenonzero wavenumber. Thecomputational timeof each
methodhasalsobeenbenchmarkedandsummarizedinTable9.3. Forthisexample,
thecompressed-sensingmethodisstillfasterthanstandardDMDbecauseofthespar-
sityofthesolutionvector.
Whenweaddsmalltomoderateamountsofbackgroundnoise(2–5%RMS)inthe
Fourierdomain,anumberofthingschange. Themodesandfrequenciesarestillvery

| 146 |     |     | Chapter9. | SparsityandDMD |
| --- | --- | --- | --------- | -------------- |
(a)PODmodes
|     | Mode1 | Mode2 Mode3 | Mode4 | Mode5  |
| --- | ----- | ----------- | ----- | ------ |
|     | Mode6 | Mode7 Mode8 | Mode9 | Mode10 |
(b)DMDmodes
|     | Mode1 | Mode2 Mode3 | Mode4 | Mode5 |
| --- | ----- | ----------- | ----- | ----- |
Real
Imag
(c)CompressedsensingDMDmodes
|     | Mode1 | Mode2 Mode3 | Mode4 | Mode5 |
| --- | ----- | ----------- | ----- | ----- |
Real
Imag
(d)CompressedDMDmodes
|     | Mode1 | Mode2 Mode3 | Mode4 | Mode5 |
| --- | ----- | ----------- | ----- | ----- |
Real
Imag
Figure 9.5. (a) POD modes obtained from data. Energetic modes mix the underly-
ing Fourier modes. (b) DMD modes correctly isolate spatially coherent modes. (c) Compressed-
sensingDMDmodes,usingmatchingpursuit. (d)DMDmodesfromcompresseddata,using(9.23).
ReprintedwithpermissionfromtheAmericanInstituteofMathematicalSciences[48].

9.4. CompressedDMD 147
| (cid:4)(cid:3) |     |     |     | (cid:1) |
| -------------- | --- | --- | --- | ------- |
(cid:4)
(cid:8)
(cid:7)
(cid:13)(cid:25)(cid:28)(cid:17)(cid:1)(cid:17)(cid:19)(cid:18)(cid:17)(cid:22)(cid:29)(cid:14)(cid:20)(cid:28)(cid:17)(cid:26)
(cid:6)
(cid:11)(cid:30)(cid:14)(cid:15)(cid:27)(cid:1)(cid:10)(cid:12)(cid:10)(cid:1)(cid:17)(cid:19)(cid:18)(cid:17)(cid:22)(cid:29)(cid:14)(cid:20)(cid:28)(cid:17)(cid:26)
| (cid:5) |     | (cid:9)(cid:23)(cid:21)(cid:24)(cid:25)(cid:17)(cid:26)(cid:26)(cid:17)(cid:16)(cid:1)(cid:10)(cid:12)(cid:10)(cid:1)(cid:17)(cid:19)(cid:18)(cid:17)(cid:22)(cid:29)(cid:14)(cid:20)(cid:28)(cid:17)(cid:26) |     |     |
| ------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- | --- |
yranigamI
(cid:3)
(cid:239)(cid:5)
(cid:239)(cid:6)
(cid:239)(cid:7)
(cid:239)(cid:8)
(cid:239)(cid:4)(cid:3)(cid:1)
| (cid:239)(cid:3)(cid:2)(cid:4) | (cid:239)(cid:3)(cid:2)(cid:3)(cid:8) (cid:239)(cid:3)(cid:2)(cid:3)(cid:7) | (cid:239)(cid:3)(cid:2)(cid:3)(cid:6) | (cid:239)(cid:3)(cid:2)(cid:3)(cid:5) | (cid:3) |
| ------------------------------ | --------------------------------------------------------------------------- | ------------------------------------- | ------------------------------------- | ------- |
Real
Figure9.6. DMDmodescapturedynamicsfaithfully. Reprintedwithpermissionfrom
theAmericanInstituteofMathematicalSciences[48].
Table9.3.ComputationtimeforDMDmethodsintheexamplein§9.4.3.Eachmethod
wasrun1000timestocomputeanaveragerun-time.ReprintedwithpermissionfromtheAmerican
InstituteofMathematicalSciences[48].
|     | Standard | Compressed | Compressed-Sensing |     |
| --- | -------- | ---------- | ------------------ | --- |
|     | DMD      | DMD        | DMD                |     |
Time[s]
|     | 1.254e-1 | 2.459e-4 | 2.459e-4 |     |
| --- | -------- | -------- | -------- | --- |
DVS
| Speed-up | baseline | 509.9 | 509.9 |     |
| -------- | -------- | ----- | ----- | --- |
Time[s]
| DMD      | 1.463e-1 | 3.271e-3 | 1.130e-2 |     |
| -------- | -------- | -------- | -------- | --- |
| Speed-up | baseline | 44.73    | 12.95    |     |
well characterized by both compressed DMD and compressed-sensing DMD. How-
ever, the resulting DMD damping is often inflated; this effect is more pronounced
whenthefull-stateDMDeigenvaluesarestronglydamped. Recentresultspredictthe
[12],
change in DMD spectrum with small additive noise and our results appear to
beconsistent. Moreworkisneededtocharacterizeandaddresstheissueofnoiseand
DMD. However, if the goal of a DMD model is closed-loop feedback control, then
controller robustness with respect to uncertain damping is desirable. The effect of
noiseonDMDisdiscussedfurtherinChapter8.

| 148            |          |      |     | Chapter9. | SparsityandDMD |     |
| -------------- | -------- | ---- | --- | --------- | -------------- | --- |
| 9.4.4 Example: | Cylinder | wake |     |           |                |     |
Werevisitthecylinderwakeexample, firstintroducedinChapter2,todemonstrate
compressedDMDandcompressed-sensingDMD.
CompressedDMD
ThecompressedDMDalgorithm,wherewestartwithfull-statesnapshotmatrices,is
extremelycomputationallyefficient,speedinguptheDMDalgorithmbymanyorders
ofmagnitude. TheSVDisthemostexpensivepartoftheDMDcomputation,having
of(cid:23)(nm2).
| acomputational | complexity |     | InFigure9.7, | weseethatdominantDMD |     |     |
| -------------- | ---------- | --- | ------------ | -------------------- | --- | --- |
modesareaccuratelydeterminedwithasfewas p =21projectedmeasurements,and
p=40.
eventhemostsubtlemodesarecapturedaccuratelyfor Thistranslatesintoa
speed-upofover30,000timesfor p=21andover8,000timesforp=40.WeuseGaus-
sianrandomprojections,althoughwehaveverifiedthatsingle-pixelmeasurementsare
alsoeffective. TheDMDspectrumisalsoaccuratelyreproduced.
Compressed-sensingDMD
IncontrasttocompressedDMD,compressed-sensingDMDisquitecomputationally
expensiveandshouldonlybeusedwhenfull-statemeasurementsareeithermoreex-
pensiveorunavailable. Figure9.8showsahandfulofDMDmodesobtainedthrough
spatiallyresolvedDMD,alongwiththeircompressed-sensingDMDcounterparts. The
moreenergeticDMDmodesarecaptured, although withsomeerror. However, the
DMDmodescontaininghigherharmonicsaredifficulttoreproduceaccurately. For
| (a) | 2        |         | (b) | 2        |           |     |
| --- | -------- | ------- | --- | -------- | --------- | --- |
|     | TrueMode |         |     | TrueMode |           |     |
|     | 1        |         |     | 1        |           |     |
| y   | 0        |         | y   | 0        |           |     |
|     | 0 1 2    | 3 4 5 6 | 7 8 | 0 1      | 2 3 4 5 6 | 7 8 |
| (c) | 2 p=21   |         | (d) | 2 p=21   |           |     |
|     | 1        |         |     | 1        |           |     |
| y   |          |         | y   |          |           |     |
|     | 0        |         |     | 0        |           |     |
|     | 0 1 2    | 3 4 5 6 | 7 8 | 0 1      | 2 3 4 5 6 | 7 8 |
|     | 2        |         |     | 2        |           |     |
| (e) | p=40     |         | (f) | p=40     |           |     |
|     | 1        |         |     | 1        |           |     |
| y   | 0        |         | y   | 0        |           |     |
|     | 0 1 2    | 3 4 5 6 | 7 8 | 0 1      | 2 3 4 5 6 | 7 8 |
|     |          | x       |     |          | x         |     |
Figure9.7. CompressedDMDforcylinderwake. ThefirstrowshowstwotrueDMD
modesfrom spatially resolvedmeasurements, and thesecond and third rows indicate compressed
|     | p=21and | p=40measurements,respectively. |     |     |     |     |
| --- | ------- | ------------------------------ | --- | --- | --- | --- |
DMDmodeswith

9.4. CompressedDMD 149
=1000randomprojectedmeasurements,whichamountstoa
| thisexample,weuse | p   |     |     |     |     |
| ----------------- | --- | --- | --- | --- | --- |
reductionofmeasurementsbyafactorof∼90.
Figure 9.9 shows the DMD mode reconstruction for two modes as the sparsity
|     |     |     | =   | =   |     |
| --- | --- | --- | --- | --- | --- |
level K is increased in the CoSaMP algorithm from K 25 to K 50 and finally
toK =75. Determiningthecorrect sparsitylevelisimportantwhenusingagreedy
method,suchasCoSaMP[205].
Thiscorrectsparsitylevelmaydifferfrommodeto
mode,asseeninFigure9.9.
Inthisexampleoffluidflowpastacylinder,weseethatdespitehighdimensionality,
underlying low-rank structures can be identified from heavily compressed measure-
ments. Inthecasethatfull-statemeasurementsareavailable,itisstilladvantageousto
performDMDoncompressedmeasurementsbecauseofthesignificantcomputational
speed-up,withoutanappreciableincreaseinerror. Itisthenpossibletousethelinear
transformations computed on the compressed datato obtain full-state DMD modes
intermsofalinearcombination ofthefull-statesnapshots. When onlycompressed
measurements are available, it is still possible to reconstruct full-state modes using
compressed sensing, although thisusesmorecompressed measurementsandcompu-
tationalresources.
| SpatiallyresolvedDMD |         |     | CompressedSensingDMD |         |     |
| -------------------- | ------- | --- | -------------------- | ------- | --- |
| (a) 2                |         | (b) | 2                    |         |     |
| 1                    |         |     | 1                    |         |     |
| y 0                  |         | y   | 0                    |         |     |
| 0 1 2                | 3 4 5 6 | 7 8 | 0 1 2                | 3 4 5 6 | 7 8 |
| 2                    |         |     | 2                    |         |     |
| (c)                  |         | (d) |                      |         |     |
| 1                    |         |     | 1                    |         |     |
| y 0                  |         | y   | 0                    |         |     |
| 0 1 2                | 3 4 5 6 | 7 8 | 0 1 2                | 3 4 5 6 | 7 8 |
| 2                    |         |     | 2                    |         |     |
| (e)                  |         | (f) |                      |         |     |
| 1                    |         |     | 1                    |         |     |
| y 0                  |         | y   | 0                    |         |     |
−1
−2
| 0 1 2 | 3 4 5 6 | 7 8 | −1 0 1 2 | 3 4 5 6 | 7 8 |
| ----- | ------- | --- | -------- | ------- | --- |
| 2     |         |     | 2        |         |     |
| (e)   |         | (f) |          |         |     |
| 1     |         |     | 1        |         |     |
| y 0   |         | y   | 0        |         |     |
| 0 1 2 | 3 4 5 6 | 7 8 | 0 1 2    | 3 4 5 6 | 7 8 |
|       | x       |     |          | x       |     |
Figure9.8. Compressed-sensingDMDforcylinderwake. (left)TrueDMDmodesfrom
spatiallyresolveddata,and(right)compressed-sensingDMDmodes.

| 150 |       |     |       |       | Chapter9. | SparsityandDMD |     |
| --- | ----- | --- | ----- | ----- | --------- | -------------- | --- |
|     | 2     |     |       |       | 2         |                |     |
|     | (a)   |     |       | (b)   |           |                |     |
|     | 1     |     |       |       | 1         |                |     |
|     | y 0   |     |       | y     | 0         |                |     |
|     | 0     | 1 2 | 3 4 5 | 6 7 8 | 0 1       | 2 3 4 5 6      | 7 8 |
|     | (c) 2 |     |       | (d)   | 2         |                |     |
|     | 1     |     |       |       | 1         |                |     |
|     | y 0   |     |       | y     | 0         |                |     |
|     | 0     | 1 2 | 3 4 5 | 6 7 8 | 0 1       | 2 3 4 5 6      | 7 8 |
|     | 2     |     |       |       | 2         |                |     |
|     | (e)   |     |       | (f)   |           |                |     |
|     | 1     |     |       |       | 1         |                |     |
|     | y 0   |     |       | y     | 0         |                |     |
|     | 0     | 1 2 | 3 4 5 | 6 7 8 | 0 1       | 2 3 4 5 6      | 7 8 |
|     |       |     | x     |       |           | x              |     |
Figure9.9.Convergenceplotofcompressed-sensingDMDonthecylinderwakeforvari-
oussparsitylevelsK.(a),(b)K=25;(c),(d)K=50;(e),(f)K=75.
| 9.5 | Code for | compressed |     | DMD |     |     |     |
| --- | -------- | ---------- | --- | --- | --- | --- | --- |
ALGORITHM9.4.Mainscripttoruntheexamplein§9.4.3.
|     | clear all, | close    | all, | clc |     |     |     |
| --- | ---------- | -------- | ---- | --- | --- | --- | --- |
|     | addpath    | ./utils/ |      |     |     |     |     |
% PARAMETERS
n = 128;
|     | K = 5;      | % degree      | of sparsity |               |             |     |     |
| --- | ----------- | ------------- | ----------- | ------------- | ----------- | --- | --- |
|     | T = 2;      | % duration    | of          | integration   |             |     |     |
|     | dt = 0.01;  | % time        | step        |               |             |     |     |
|     | r = 10;     | % number      | of PCA      | modes to keep |             |     |     |
|     | noisemag    | = 0.0;        | % magnitude | of additive   | white noise |     |     |
|     | filename    | = ’DATA/RUN’; |             |               |             |     |     |
|     | saveFLAG    | = 1;          |             |               |             |     |     |
|     | movieFLAG   | = 1;          |             |               |             |     |     |
|     | getParms    | % generate    | Damping     | rate, etc.    |             |     |     |
|     | %% GENERATE | SPARSE        | DATA        |               |             |     |     |
saveFLAG=0;
|     | noisemag | = 0.; |     |     |     |     |     |
| --- | -------- | ----- | --- | --- | --- | --- | --- |
getSparseData
|     | %% PLOT | MOVIE |     |     |     |     |     |
| --- | ------- | ----- | --- | --- | --- | --- | --- |
plotData

9.5. CodeforcompressedDMD 151
| %% COMPUTE | FFT MODES |     |     |     |
| ---------- | --------- | --- | --- | --- |
computeFFTModes
| %% COMPUTE | POD MODES |     |     |     |
| ---------- | --------- | --- | --- | --- |
computePODModes
| %% COMPUTE | DMD MODES |     |     |     |
| ---------- | --------- | --- | --- | --- |
computeDMDModes
| %% PROJECT | DATA |     |     |     |
| ---------- | ---- | --- | --- | --- |
projectData
| %% COMPUTE | DMD MODES | USING | COMPRESSIVE | SENSING |
| ---------- | --------- | ----- | ----------- | ------- |
compressedDMD
ALGORITHM9.5.getParms.m.
| xtilde =   | zeros(n,n); |          |     |     |
| ---------- | ----------- | -------- | --- | --- |
| % generate | sparse      | FFT data |     |     |
for i=1:K;
| loopbreak | = 0; |     |     |     |
| --------- | ---- | --- | --- | --- |
while(~loopbreak)
I(i) = 0+ceil(rand(1)*n/15);
J(i) = 0+ceil(rand(1)*n/15);
|     | if(xtilde(I(i),J(i)) |      | == 0) |     |
| --- | -------------------- | ---- | ----- | --- |
|     | loopbreak            | = 1; |       |     |
end
end
| IC(i)             | = randn();        |          |     |     |
| ----------------- | ----------------- | -------- | --- | --- |
| xtilde(I(i),J(i)) |                   | = IC(i); |     |     |
| F(i)              | = sqrt(4*rand()); |          |     |     |
| damping(i)        | = -rand()*.1;     |          |     |     |
end
if(saveFLAG)
save([filename,’_PARMS.mat’]);
end
ALGORITHM9.6.getSparseData.m.
| xtilde = | zeros(n,n); |     |     |     |
| -------- | ----------- | --- | --- | --- |
XDAT = [];
| XDATtilde      | = [];             |                                                |                                       |     |
| -------------- | ----------------- | ---------------------------------------------- | ------------------------------------- | --- |
| XDATtildeNoise | = [];             |                                                |                                       |     |
| for t =        | 0:dt:T            |                                                |                                       |     |
| xtilde         | = 0*xtilde;       |                                                |                                       |     |
| for            | k=1:K             |                                                |                                       |     |
|                | xtilde(I(k),J(k)) |                                                | = exp(damping(k)*t)*cos(2*pi*F(k)*t)* |     |
|                | IC(k)             | + exp(damping(k)*t)*sqrt(-1)*sin(2*pi*F(k)*t)* |                                       |     |
IC(k);
end
| XDATtilde | = [xXDATtilde |     | reshape(xtilde,n^2,1)]; |     |
| --------- | ------------- | --- | ----------------------- | --- |

| 152 |     |     |     |     | Chapter9. | SparsityandDMD |     |
| --- | --- | --- | --- | --- | --------- | -------------- | --- |
xRMS = sqrt((1/(n*n))*sum(xtilde(:).^2));
|     | xtilde = xtilde | + noisemag*xRMS*randn(size(xtilde)) |     |     |     |     | +   |
| --- | --------------- | ----------------------------------- | --- | --- | --- | --- | --- |
noisemag*xRMS*sqrt(-1)*randn(size(xtilde));
|     | XDATtildeNoise | = [XDATtildeNoise |     | reshape(xtilde,n^2,1)]; |     |     |     |
| --- | -------------- | ----------------- | --- | ----------------------- | --- | --- | --- |
x = real(ifft2(xtilde));
|     | XDAT = [XDAT | reshape(x,n^2,1)]; |     |     |     |     |     |
| --- | ------------ | ------------------ | --- | --- | --- | --- | --- |
end
if(saveFLAG)
save([filename,’_DATAX.mat’]);
end
ALGORITHM9.7.plotData.m.
% define figure
f1=figure
|     | ax1=axes(’position’,[.05  |     | .6 .2 .325]); |        |     |     |     |
| --- | ------------------------- | --- | ------------- | ------ | --- | --- | --- |
|     | ax2=axes(’position’,[.3   |     | .6 .2 .325]); |        |     |     |     |
|     | ax3=axes(’position’,[.05  |     | .075 .45      | .35]); |     |     |     |
|     | ax4=axes(’position’,[.525 |     | -.20 .475     | 1.4]); |     |     |     |
|     | set(gcf,’Position’,[100   |     | 100 1400      | 650])  |     |     |     |
% define movie
if(movieFLAG)
|     | writerObj = | VideoWriter([filename,’_Torus.mp4’],’MPEG-4’); |     |     |     |     |     |
| --- | ----------- | ---------------------------------------------- | --- | --- | --- | --- | --- |
open(writerObj);
end
|     | % define torus grid |     |     |     |     |     |     |
| --- | ------------------- | --- | --- | --- | --- | --- | --- |
r1 = 2;
r2 = 1;
[T1,T2] = meshgrid(0:2*pi/n:2*pi,0:2*pi/n:2*pi);
R = r1 + r2*cos(T2);
Z = r2*sin(T2);
X = cos(T1).*R;
Y = sin(T1).*R;
|     | % define FFT domain | grid |     |     |     |     |     |
| --- | ------------------- | ---- | --- | --- | --- | --- | --- |
x1 = 1:n;
y1 = x1;
x2 = 1:16;
y2 = x2;
for i=1:size(XDAT,2)
|     | xtilde = reshape(XDATtildeNoise(:,i),n,n); |     |     |     |     |     |     |
| --- | ------------------------------------------ | --- | --- | --- | --- | --- | --- |
x = reshape(XDAT(:,i),n,n);
set(gcf,’CurrentAxes’,ax1)
|     | imagesc(real(xtilde’),[-1 |     | 1]), | box on; |     |     |     |
| --- | ------------------------- | --- | ---- | ------- | --- | --- | --- |
axis xy
|     | set(gca,’XTick’,[1      |     | 32 64 96 128],’YTick’,[1 |                    |     | 32 64 | 96 128]); |
| --- | ----------------------- | --- | ------------------------ | ------------------ | --- | ----- | --------- |
|     | rectangle(’Position’,[1 |     | 1 16                     | 16],’LineWidth’,2) |     |       |           |
set(gcf,’CurrentAxes’,ax2)
|     | imagesc(x2,y2,real(xtilde(x2,y2)’),[-1 |     |     |     | 1]), | box on; | % added |
| --- | -------------------------------------- | --- | --- | --- | ---- | ------- | ------- |
transpose!

9.5. CodeforcompressedDMD 153
axis xy
| set(gca,’XTick’,[1 |     | 4 8 12 16],’YTick’,[1 | 4 8 12 16]); |     |
| ------------------ | --- | --------------------- | ------------ | --- |
set(gcf,’CurrentAxes’,ax3)
| imagesc(abs(x)), |     | box on; |     |     |
| ---------------- | --- | ------- | --- | --- |
axis xy
| set(gca,’XTick’,[1 |     | 32 64 96 128],’YTick’,[1 | 32 64 | 96 128]); |
| ------------------ | --- | ------------------------ | ----- | --------- |
set(gcf,’CurrentAxes’,ax4)
surf(X,Y,Z,abs(x),’EdgeColor’,’none’)
axis equal
| set(gcf,’Color’,[1 |     | 1 1]); |     |     |
| ------------------ | --- | ------ | --- | --- |
view(100,32)
colormap(jet);
drawnow
if(movieFLAG)
| frame | = getframe(f1); |     |     |     |
| ----- | --------------- | --- | --- | --- |
writeVideo(writerObj,frame);
end
end
| if(movieFLAG) | close(writerObj); |     |     |     |
| ------------- | ----------------- | --- | --- | --- |
end
ALGORITHM9.8.computeFFTModes.m.
figure
| for i=1:2 %real | vs imag |             |     |     |
| --------------- | ------- | ----------- | --- | --- |
| for k=1:K       | % all   | sparse vals |     |     |
subplot(2,K,(i-1)*K+k)
| x2tilde            | = 0*xtilde; |                     |           |         |
| ------------------ | ----------- | ------------------- | --------- | ------- |
| x2tilde(I(k),J(k)) |             | = (sqrt(-1))^(i-1); | % = 1 for | i=1 and |
=i for i=2
| x2  | = ifft2(x2tilde); |     |     |     |
| --- | ----------------- | --- | --- | --- |
surf(X,Y,Z,real(x2),’EdgeColor’,’none’);
| MODESFFT(i,k,:) |     | = x2(:); |     |     |
| --------------- | --- | -------- | --- | --- |
view(10,32)
| colormap | jet;  |     |     |     |
| -------- | ----- | --- | --- | --- |
| axis     | off   |     |     |     |
| axis     | equal |     |     |     |
drawnow
end
end
| set(gcf,’Position’,[100 |     | 100 1440 450]) |     |     |
| ----------------------- | --- | -------------- | --- | --- |
ALGORITHM9.9.computePODModes.m.
figure
[U,S,V] = svd(XDAT,0);
stairs(cumsum(diag(S))/sum(diag(S)));
figure
for i=1:10
subplot(2,5,i)
ximg = reshape(U(:,i),n,n);

| 154 |     |     |     |     | Chapter9. | SparsityandDMD |
| --- | --- | --- | --- | --- | --------- | -------------- |
surf(X,Y,Z,real(ximg),’EdgeColor’,’none’);
view(10,32)
|     | colormap | jet;  |     |     |     |     |
| --- | -------- | ----- | --- | --- | --- | --- |
|     | axis     | equal |     |     |     |     |
|     | axis     | off   |     |     |     |     |
drawnow
end
|     | set(gcf,’Position’,[100 |                    | 100 | 1440 450]) |     |     |
| --- | ----------------------- | ------------------ | --- | ---------- | --- | --- |
|     | ALGORITHM9.10.          | computeDMDModes.m. |     |            |     |     |
|     | %% COMPUTE              | DMD                |     |            |     |     |
% step 0
XD1 = XDAT(:,1:end-1);
XD2 = XDAT(:,2:end);
% step 1
|     | [U,S,V] | = svd(XD1,0); |     |     |     |     |
| --- | ------- | ------------- | --- | --- | --- | --- |
% step 2
Sinv = S(1:r,1:r)^(-1);
|     | Atilde | = U(:,1:r)’*XD2*V(:,1:r)*Sinv(1:r,1:r); |     |     |     |     |
| --- | ------ | --------------------------------------- | --- | --- | --- | --- |
% step 3
|     | [W,D] | = eig(Atilde); |     |     |     |     |
| --- | ----- | -------------- | --- | --- | --- | --- |
% step 4
Phi = XD2*V(:,1:r)*Sinv*W;
|     | %% Plot | DMD eigenvalues         |                    |     |     |     |
| --- | ------- | ----------------------- | ------------------ | --- | --- | --- |
|     | figure, | hold on                 |                    |     |     |     |
|     | dmdeigs | = log(eig(Atilde))*100; |                    |     |     |     |
|     | lambdap | = damping               | + sqrt(-1)*F*2*pi; |     |     |     |
|     | lambdan | = damping               | - sqrt(-1)*F*2*pi; |     |     |     |
|     | lambda  | = [lambdap              | lambdan];          |     |     |     |
scatter(real(lambda),imag(lambda),’kx’)
scatter(real(dmdeigs),imag(dmdeigs),’rd’)
|     | box on,                 | grid on           |     |               |     |     |
| --- | ----------------------- | ----------------- | --- | ------------- | --- | --- |
|     | legend(’True            | eigenvalues’,’DMD |     | eigenvalues’) |     |     |
|     | set(gcf,’Position’,[100 |                   | 100 | 400 300])     |     |     |
|     | %% Plot                 | Modes             |     |               |     |     |
figure
for k=1:K
|     | for | j=1:2 |     |     |     |     |
| --- | --- | ----- | --- | --- | --- | --- |
subplot(2,K,(j-1)*K+k)
if(j==1)
|     |     | ximg | = real(reshape(Phi(:,(k-1)*2+1)+Phi(:,k*2),n,n) |     |     |     |
| --- | --- | ---- | ----------------------------------------------- | --- | --- | --- |
);
end
if(j==2)
|     |     | ximg | = imag(reshape(Phi(:,(k-1)*2+1)-Phi(:,k*2),n,n) |     |     |     |
| --- | --- | ---- | ----------------------------------------------- | --- | --- | --- |
);
end
|     |     | MODESDMD(j,k,:) | = ximg(:); |     |     |     |
| --- | --- | --------------- | ---------- | --- | --- | --- |
surf(X,Y,Z,(ximg),’EdgeColor’,’none’);
|     |     | view(10,32), | colormap | jet, axis | equal, | axis off |
| --- | --- | ------------ | -------- | --------- | ------ | -------- |
end

9.5. CodeforcompressedDMD 155
end
| ALGORITHM9.11. | projectData.m.     |                           |
| -------------- | ------------------ | ------------------------- |
| M = 15;        | % number           | of measurements           |
| % projType     | = 1; %             | uniform random projection |
| projType       | = 2; % Gaussian    | random projection         |
| % projType     | = 3; %             | Single pixel measurement  |
| %% Create      | random measurement | matrix                    |
C = zeros(M,n*n);
| Theta = | zeros(M,n*n); |     |
| ------- | ------------- | --- |
xmeas= zeros(n,n);
for i=1:M
| xmeas | = 0*xmeas; |     |
| ----- | ---------- | --- |
if(projType==1)
xmeas = rand(n,n);
elseif(projType==2)
xmeas = randn(n,n);
elseif(projType==3)
xmeas(ceil(n*rand),ceil(n*rand)) = 1;
end
| C(i,:)     | = reshape(xmeas,n*n,1);          |     |
| ---------- | -------------------------------- | --- |
| Theta(i,:) | = reshape((ifft2(xmeas)),1,n*n); |     |
end
| %% Project | data |     |
| ---------- | ---- | --- |
YDAT = C*XDAT;
if(saveFLAG)
save([filename,’_DATAY.mat’]);
end
| %% plot | C             |     |
| ------- | ------------- | --- |
| figure, | colormap bone |     |
Cimg = sum(C,1);
Ximg = XDAT(:,1).*Cimg’;
imagesc(reshape(Ximg,n,n));
| figure, | colormap bone; |     |
| ------- | -------------- | --- |
surf(X,Y,Z,reshape(Cimg,n,n));
view(10,32)
| axis equal, | axis off |     |
| ----------- | -------- | --- |
drawnow
| ALGORITHM9.12. | compressedDMD.m. |     |
| -------------- | ---------------- | --- |
| %% COMPUTE     | DMD              |     |
% step 0
YD1 = YDAT(:,1:end-1);
YD2 = YDAT(:,2:end);
% step 1
| [U,S,V] | = svd(YD1,0); |     |
| ------- | ------------- | --- |

| 156 |     |     |     |     |     |     | Chapter9. | SparsityandDMD |     |
| --- | --- | --- | --- | --- | --- | --- | --------- | -------------- | --- |
% step 2
|     | r=10; | % for | two mode | and | K=5 |     |     |     |     |
| --- | ----- | ----- | -------- | --- | --- | --- | --- | --- | --- |
Sinv = S(1:r,1:r)^(-1);
|     | Atilde | = U(:,1:r)’*YD2*V(:,1:r)*Sinv(1:r,1:r); |     |     |     |     |     |     |     |
| --- | ------ | --------------------------------------- | --- | --- | --- | --- | --- | --- | --- |
% step 3
|     | [W,D] | = eig(Atilde); |     |     |     |     |     |     |     |
| --- | ----- | -------------- | --- | --- | --- | --- | --- | --- | --- |
% step 4
PhiY = YD2*V(:,1:r)*Sinv*W;
|     | PhiXr       | = XD2*V(:,1:r)*Sinv*W;  |             |                    |     | % reconstructed |     |     |     |
| --- | ----------- | ----------------------- | ----------- | ------------------ | --- | --------------- | --- | --- | --- |
|     | %% Plot     | DMD                     | eigenvalues |                    |     |                 |     |     |     |
|     | figure,     | hold                    | on          |                    |     |                 |     |     |     |
|     | dmdeigsFULL |                         | = dmdeigs;  |                    |     |                 |     |     |     |
|     | dmdeigs     | = log(eig(Atilde))*100; |             |                    |     |                 |     |     |     |
|     | lambdap     | = damping               |             | + sqrt(-1)*F*2*pi; |     |                 |     |     |     |
|     | lambdan     | = damping               |             | - sqrt(-1)*F*2*pi; |     |                 |     |     |     |
|     | lambda      | = [lambdap              |             | lambdan];          |     |                 |     |     |     |
scatter(real(lambda),imag(lambda),’kx’)
scatter(real(dmdeigsFULL),imag(dmdeigsFULL),’bo’)
scatter(real(dmdeigs),imag(dmdeigs),’rd’)
|     | box on, | grid | on  |     |     |     |     |     |     |
| --- | ------- | ---- | --- | --- | --- | --- | --- | --- | --- |
legend(’True eigenvalues’,’Exact DMD eigenvalues’,’Compressed
|     | DMD     | eigenvalues’) |     |     |       |      |     |     |     |
| --- | ------- | ------------- | --- | --- | ----- | ---- | --- | --- | --- |
|     | %% Plot | Reconstructed |     | DMD | modes | from | X   |     |     |
figure
for k=1:K
|     | for | j=1:2 |     |     |     |     |     |     |     |
| --- | --- | ----- | --- | --- | --- | --- | --- | --- | --- |
subplot(2,K,(j-1)*K+k)
if(j==1)
|     |     |     | ximg | = real(reshape(PhiXr(:,(k-1)*2+1)+PhiXr(:,k*2), |     |     |     |     |     |
| --- | --- | --- | ---- | ----------------------------------------------- | --- | --- | --- | --- | --- |
n,n));
end
if(j==2)
|     |     |     | ximg | = imag(reshape(PhiXr(:,(k-1)*2+1)-PhiXr(:,k*2), |     |     |     |     |     |
| --- | --- | --- | ---- | ----------------------------------------------- | --- | --- | --- | --- | --- |
n,n));
end
surf(X,Y,Z,(ximg),’EdgeColor’,’none’);
|     |     | view(10,32), |     | colormap |     | jet, | axis equal, | axis off, | drawnow |
| --- | --- | ------------ | --- | -------- | --- | ---- | ----------- | --------- | ------- |
end
end
|     | %% Reconstruct |     | Modes | with | Compressive |     | Sensing. |     |     |
| --- | -------------- | --- | ----- | ---- | ----------- | --- | -------- | --- | --- |
for i=1:K
|     | y   | = PhiY(:,2*i-1); |     |     |     |     |     |     |     |
| --- | --- | ---------------- | --- | --- | --- | --- | --- | --- | --- |
% cvx_begin;
|     | %   | variable   |     | ahat(n*n,1); |          |     |     |     |     |
| --- | --- | ---------- | --- | ------------ | -------- | --- | --- | --- | --- |
|     | %   | minimize(  |     | norm         | (ahat,1) | );  |     |     |     |
|     | %   | subject    |     | to           |          |     |     |     |     |
|     | %   | Theta*ahat |     | ==           | y;       |     |     |     |     |
% cvx_end;
|     | ahat         | = cosamp(Theta,y,2,10^-5,100); |     |                                                 |     |     |     |     |     |
| --- | ------------ | ------------------------------ | --- | ----------------------------------------------- | --- | --- | --- | --- | --- |
|     | Phi(:,2*i-1) |                                |     | = reshape(real(ifft2(reshape(ahat,n,n))),n*n,1) |     |     |     |     |     |
;

9.5. CodeforcompressedDMD 157
| Phi(:,2*i) = reshape(imag(ifft2(reshape(ahat,n,n))),n*n,1); |     |     |     |
| ----------------------------------------------------------- | --- | --- | --- |
end
%% Plot Modes
figure
for k=1:K
for j=1:2
subplot(2,K,(j-1)*K+k)
if(j==1)
| ximg = | reshape(Phi(:,(k-1)*2+1),n,n); |     |     |
| ------ | ------------------------------ | --- | --- |
end
if(j==2)
| ximg = | reshape(Phi(:,k*2),n,n); |     |     |
| ------ | ------------------------ | --- | --- |
end
| MODESCSDMD(j,k,:) | = ximg(:); |     |     |
| ----------------- | ---------- | --- | --- |
surf(X,Y,Z,(ximg),’EdgeColor’,’none’);
| view(10,32), | colormap jet, | axis equal, | axis off |
| ------------ | ------------- | ----------- | -------- |
end
end

Chapter 10
DMD on Nonlinear
Observables
Anunderlyingassumptionmadethroughoutthebookconcernsthechoiceofobserv-
ables and data used to execute the DMD algorithm. An implicit assumption is that
themeasuredvariablesare,infact,thecorrectvariablestouse. Inmanycases,thisis
often a reasonable assumption. For instance, one may measure the pressure and/or
velocityinafluidflowandbeconfidentthatexecutingtheDMDalgorithmonsuch
variables can yield meaningful spatiotemporal patterns and predictions. Nonlinear-
ityintheunderlyingsystem, however,can challengeour assumptionson simplyus-
ingthemeasurementsdirectlyinDMD.Koopmantheorysuggeststhatabroaderset
ofobservables, namelyfunctionsofthemeasurements,maybemoreusefulforchar-
acterizingthedynamics. Thesuggestion isthat by potentiallypicking abroader set
ofobservables, informationmaybegainedontheunderlyingnonlinearmanifoldon
whichthenonlineardynamical system evolves. Manifoldlearningisacurrent topic
ofintensiveresearchinterestinthemachinelearningcommunity. Itsgoalistomore
appropriatelycharacterize thespaceonwhichdataisembedded. Inthischapter, we
highlighthowDMDcanbemodifiedthroughthechoiceofobservablestopotentially
accountforthenonlinearmanifoldsonwhichdynamicsoccur.
10.1 Koopman observables
Machinelearningmethodsareofgrowingimportanceacrossthephysical,engineering,
andbiologicalsciences. Althoughmanyofthetechniquesdevelopedareprimarilyfor
clusteringandclassificationpurposes[204,84,29],somehavebeenmodifiedtohandle
complexspatiotemporalphenomenaunderlyingdynamicalsystems. Notsurprisingly,
machinelearningmethodshavealsobeenintegratedwiththeDMDinfrastructure.
TheintegrationofmachinelearningwithDMDarisesnaturallywithintheframe-
workoftheKoopmanoperatoranditsobservables,asdefinedin(3.18):
(cid:3)g(x)=g(f(x)). (10.1)
RecallthattheKoopmanoperatorisalinearoperatorthatactsonscalarfunctions g
j
thatcompriseasetofobservablesdenotedbycomponentsofthevectorg. Letusonce
159

| 160 |     | Chapter10. | DMDonNonlinearObservables |     |
| --- | --- | ---------- | ------------------------- | --- |
againconsidertheseobservables:
|     |     | ⎡   | ⎤   |     |
| --- | --- | --- | --- | --- |
(x)
g
|     |        | ⎢ 1     | ⎥   |        |
| --- | ------ | ------- | --- | ------ |
|     |        | ⎢ g (x) | ⎥   |        |
|     | g(x)=⎢ | 2       |     |        |
|     |        | .       | ⎥ . | (10.2) |
|     |        | ⎣ .     | ⎦   |        |
.
g (x)
n
Thechoiceofappropriateobservables g isoftendifficulttoevaluatewithoutexpert
j
knowledge. However, using ideas from the highly popular support vector machine
[53,
(SVM) clustering algorithm, which is a subset of so-called kernel methods 198,
21],
271, a principled technique for judiciously choosing the observables can befor-
mulated. Inparticular,onecanthinkoftheg(x)asamappingfromthephysicalspace
to the feature space. In the feature space, an intrinsic representation of the underly-
ingdynamical system isconstructed by thetripletpairof Koopman eigenvalues λ ,
k
Koopmaneigenfunctionsϕ (x),andKoopmanmodesv
:
|     | k   |     | k   |     |
| --- | --- | --- | --- | --- |
(cid:7)∞
|     | g(x)= | v ϕ | (x), | (10.3a) |
| --- | ----- | --- | ---- | ------- |
k k
k=1
(cid:7)∞
|     | g(f(x))= | v   | λ ϕ (x). | (10.3b) |
| --- | -------- | --- | -------- | ------- |
|     |          |     | k k k    |         |
k=1
Thus,thetimeevolutionofsolutionscanbecomputedbysimplemultiplicationwith
theKoopman eigenvalueinthespaceofKoopman eigenfunctions. Importantly,the
Koopmanoperatorthuscapturestheintrinsicpropertiesofthenonlineardynamical
system(3.17),anditseigenfunctionsdefineanonlinearchangeofcoordinatesinwhich
thesystembecomeslinear. AlthoughthiswaspresentedpreviouslyintheKoopman
chapter,theinterpretationhereisintermsofafeaturespace. Or,moreprecisely,the
observablesg(x)definealinearevolutionofafeaturespace.
|     |     | [53, | 21] |     |
| --- | --- | ---- | --- | --- |
The SVM literature and kernel methods 198, 271, suggest a number of
techniquesforconstructingthefeaturespaceg(x). Onecommonchoiceisthesetof
| polynomialssuchthat |        | 4                 | 5   |        |
| ------------------- | ------ | ----------------- | --- | ------ |
|                     | g (x)= | x,x2,x3,x4,...,xn | .   | (10.4) |
j
Alternatively,kernelmethodshavefoundahighdegreeofsuccessusing(i)radialbasis
functions,typicallyforproblemsdefinedonirregulardomains;(ii)Hermitepolyno-
mialsforproblemsdefinedon(cid:2)n;and(iii)discontinuousspectral
elementsforlarge
problemswithblockdiagonalstructures.
Regardless of the specific choice of feature space, the goal is to choose a suffi-
ciently rich and diverse set of observables that allow an accurate approximation of
theKoopmanoperator(cid:3). Insteadofchoosingthecorrectobservables,onethensim-
plychoosesalargesetofcandidateobservableswiththeexpectationthatasufficiently
diverse set will include enough features for an accurate reconstruction of thetriplet
pair (10.3), which intrinsically characterizes the nonlinear dynamical system under
consideration.
10.2 Nonlinear observables for partial differential equations
TheexamplesintheKoopmanchapterwereeasytoquantifyandunderstandsincethey
were chosen to elucidate the principles of the Koopman decomposition in relation
to DMD. Moreover, the observables chosen were easily motivated from knowledge

10.2. Nonlinearobservablesforpartialdifferentialequations 161
ofthesolution. Amorerealisticexamplecomes fromapartial differential equation
examplewhereanalyticinsightismoredifficulttoobtain. Thus,tofurtherillustrate
theKoopmandecompositioninrelationtoDMD,considerthenonlinearSchrödinger
(NLS)equation
|     |     | ∂q  | 1∂2q        |     |        |
| --- | --- | --- | ----------- | --- | ------ |
|     |     | i   | + +|q|2q=0, |     | (10.5) |
|     |     | ∂t  | 2∂ξ2        |     |        |
q(ξ,t)
where is a function of space and time and a specific example of (1.36). The
equationcanberewrittenintheform
|     |     | ∂q  | i ∂2q      |     |     |
| --- | --- | --- | ---------- | --- | --- |
|     |     |     | = +i|q|2q, |     |     |
(10.6)
|     |     | ∂t  | 2∂ξ2 |     |     |
| --- | --- | --- | ---- | --- | --- |
Fouriertransforminginξ,denoted
sothataspectralmethodsolutioncanbeapplied.
bythehatsymbol,givesthedifferentialequationintheFourierdomainvariablesqˆ:
|     |     | dqˆ | ik2           | 6   |     |
| --- | --- | --- | ------------- | --- | --- |
|     |     |     | =− qˆ+i|q|2q. |     |     |
(10.7)
|     |     | dt  | 2   |     |     |
| --- | --- | --- | --- | --- | --- |
Bydiscretizinginthespatialvariable,wecanthenevolvethisequationwithastandard
time-steppingalgorithmsuchasafourth-orderRunge–Kuttaintegrator. Thefollowing
codegeneratesanumericalapproximationtothesolutionof(10.5).
| ALGORITHM10.1.              | NLSequation.   |                |           |                |     |
| --------------------------- | -------------- | -------------- | --------- | -------------- | --- |
| %% Define spatial           |                | discretization |           |                |     |
| L=30; n=512;                | %%             | Domain length  | and #     | points         |     |
| xi2=linspace(-L/2,L/2,n+1); |                |                | %% domain | discretization |     |
| xi=xi2(1:n);                | %%             | periodic       | domain    |                |     |
| k=(2*pi/L)*[0:n/2-1         |                | -n/2:-1].’;    | %%        | wavenumbers    |     |
| %% Define time              | discretization |                |           |                |     |
slices=20;
| t=linspace(0,pi,slices+1); |     |            | dt=t(2)-t(1); |     |     |
| -------------------------- | --- | ---------- | ------------- | --- | --- |
| %% Create initial          |     | conditions |               |     |     |
q=2*(sech(xi)).’;
qt=fft(q);
| %% Combine    | signals     |     |     |     |     |
| ------------- | ----------- | --- | --- | --- | --- |
| %% Solve with | Runge-Kutta |     |     |     |     |
[t,qtsol]=ode45(’dmd_soliton_rhs’,t,qt,[],k);
| %% Bring back | to  | time domain | and store | data |     |
| ------------- | --- | ----------- | --------- | ---- | --- |
for j=1:length(t)
qsol(j,:)=ifft(qtsol(j,:));
end
X = qsol.’;
This code provides a complete numerical solution of the NLS equation (10.5),
wheretheright-handsideof(10.7)iscomputedasfollows.

| 162 |     |     |     | Chapter10. | DMDonNonlinearObservables |     |     |
| --- | --- | --- | --- | ---------- | ------------------------- | --- | --- |
|     |     | (a) |     |            | (b)                       |     |     |
(x)=x
|     |     | simulation |     |     |     | g   |     |
| --- | --- | ---------- | --- | --- | --- | --- | --- |
DMD
|     | |q| |        |       | |q| |     |        |      |
| --- | --- | ------ | ----- | --- | --- | ------ | ---- |
|     |     | (c)    | &     | ’   | (d) |        | & ’  |
|     |     |        | x     |     |     |        | x    |
|     |     | g (x)= |       |     |     | g (x)= |      |
|     |     | 1      | |x|2x |     |     | 2      | |x|2 |
|     | |q| |        |       | |q| |     |        |      |
Figure10.1. KoopmanreconstructionofthenumericalsimulationoftheNLSequation
(10.5). Thefullsimulationisshowninpanel(a)alongwiththreedifferentreconstructionsusing
differentobservables. Thereconstructioninpanel(b)usesthestandardDMDalgorithm,wherethe
observableisgivenbyg (x)=x,wherex=q(ξ,t). Twoadditionalobservablesareconsidered
|     |     | DMD |     | (      | )   | ( )             |     |
| --- | --- | --- | --- | ------ | --- | --------------- | --- |
|     |     |     |     | |x|2xT |     | T,respectively. |     |
inpanels(c)and(d),correspondingtog (x)= x andg (x)= x |x|2 As
|     |     |     | 1   |     | 2   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
showninFigure10.3,theobservablevectorg (x),whichisbasedontheNLSnonlinearity,givesa
1
superiorreconstruction,highlightingtheimpactofajudiciouschoiceofobservables.
|     | ALGORITHM10.2. | Right-handsideofNLSequation.      |     |     |     |     |     |
| --- | -------------- | --------------------------------- | --- | --- | --- | --- | --- |
|     | function       | rhs=dmd_soliton_rhs(t,qt,dummy,k) |     |     |     |     |     |
q=ifft(qt);
|     | rhs=-(i/2)*(k.^2).*qt+i*fft( |     |     | (abs(q).^2).*q |     | );  |     |
| --- | ---------------------------- | --- | --- | -------------- | --- | --- | --- |
Assumed here is that there is a total of 21 slices of time data over the interval
t ∈[0,2π). Thestatevariablesarean n-dimensionaldiscretizationof q(ξ,t)sothat
|     | q(ξ,t )→ξ | ,wheren=512. | Theseξ |     |     |     |     |
| --- | --------- | ------------ | ------ | --- | --- | --- | --- |
arethecolumnsofthegenerateddatamatrix
|     | k   | k   |     | k   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
X; i.e., they are the state variable x. In this specific example, we analyze the two-
q(ξ,0)=2sech(ξ).
|     | solitonsolutionthathastheinitialcondition |     |     |     |     | Theoutputofthis |     |
| --- | ----------------------------------------- | --- | --- | --- | --- | --------------- | --- |
simulationisshowninFigure10.1(a).
Wenow consideradynamic modedecomposition and reconstruction ofthedy-
namicsasexemplifiedbythesimulation. TheDMDalgorithmfollowsthatoutlined
|     | intheintroduction. | Herealow-rankapproximationisgiven(r |     |     |     | =10). |     |
| --- | ------------------ | ----------------------------------- | --- | --- | --- | ----- | --- |

10.2. Nonlinearobservablesforpartialdifferentialequations 163
| ALGORITHM10.3.     |                  | DMDonNLSequation.      |                |      |              |     |
| ------------------ | ---------------- | ---------------------- | -------------- | ---- | ------------ | --- |
| X1 = X(:,1:end-1); |                  | %%                     | data snapshots |      |              |     |
| X2 = X(:,2:end);   |                  | %% shifted             |                | data |              |     |
| [U2,Sigma2,V2]     |                  | = svd(X1,              | ’econ’);       |      |              |     |
| r=10;              | %% rank          | 10 truncation          |                |      |              |     |
| U=U2(:,1:r);       |                  | Sigma=Sigma2(1:r,1:r); |                |      | V=V2(:,1:r); |     |
| Atilde             | = U’*X2*V/Sigma; |                        |                |      |              |     |
| [W,D] =            | eig(Atilde);     |                        |                |      |              |     |
Phi=X2*V/Sigma*W;
lambda=diag(D);
omega=log(lambda)/dt;
| y0 = Phi\u;     |                       | %% project                    | on initial |     | conditions |     |
| --------------- | --------------------- | ----------------------------- | ---------- | --- | ---------- | --- |
| q_modes         | = zeros(r,length(t)); |                               |            | %%  | DMD modes  |     |
| for iter        | = 1:length(tf)        |                               |            |     |            |     |
| q_modes(:,iter) |                       | =(y0.*exp(omega*(tf(iter)))); |            |     |            |     |
end
| q_dmd = | Phi*q_modes; |     | %% DMD | approximation |     |     |
| ------- | ------------ | --- | ------ | ------------- | --- | --- |
Figure 10.1(b) shows the standard DMD approximation achieved. Explicitly as-
sumedintheDMDreductionisthefactthattheobservablesaresimplythestatevari-
ablesx,wherex=q(ξ,t).
Moreprecisely,forDMD,wehave
(x)=x
|     |     |     |     | g   |     | (10.8) |
| --- | --- | --- | --- | --- | --- | ------ |
DMD
fortheobservables. Thus,theDMDapproximationisaspecialcaseofKoopman. The
=10)andDMDspectrumareshownintheleftpanelofFigure10.2.
DMDmodes(r
Anidealapproximationwouldhavetheeigenvaluesalignedalongtheimaginaryaxis.
Koopmantheory,however,allowsforamuchbroadersetofobservables. Inwhat
follows,weconsidertwoadditionalobservables:
& ’
|     |     |     |     | (x)= | x     |         |
| --- | --- | --- | --- | ---- | ----- | ------- |
|     |     |     |     | g    | ,     | (10.9a) |
|     |     |     |     | 1    | |x|2x |         |
& ’
x
(x)=
|     |     |     |     | g   | |x|2 . | (10.9b) |
| --- | --- | --- | --- | --- | ------ | ------- |
2
(x),
The first observable, g is inspired by the form of the nonlinearity in the NLS
1
equation. The second, g (x), is chosen to have a simple quadratic nonlinearity. It
2
has no special relationship to the governing equations. Note that the choice of the
observable|x|2 ing (x)isrelativelyarbitrary. Forinstance,onecanconsider,instead
2
of |x|2, a function such as |x|5x, x2, x3, or x5. These all produce similar results to
(x)selectedin(10.9b). (x)isinferiortoeitherthe
| theg |     |     | Specifically,theobservableg |     |     |     |
| ---- | --- | --- | --------------------------- | --- | --- | --- |
2 2
| DMDorjudiciouslyselectedg |     |     | (x)fortheKoopmanreconstruction. |     |     |     |
| ------------------------- | --- | --- | ------------------------------- | --- | --- | --- |
1
As has been repeatedly stated, success of the Koopman decomposition relies al-
most exclusively on the choice of observables. Moreover, in practice the Koopman
decomposition is performed on the set of observables, not the state-space variables.
Todemonstratethis,wecomputetheKoopmandecompositionoftheNLSequation
(10.5)usingthetwoobservables(10.9). Weillustratethecodeontheobservablesg (x).
1

164 Chapter10. DMDonNonlinearObservables
(cid:3) (cid:4) (cid:3) (cid:4)
x x
g (x)=x g (x)= g (x)=
DMD 1 |x|2x 2 |x|2
0.4 0.05 0.3
|φ |
j 0.2 0.025 0.15
0 0 0
10 10 10
8 8 8
0 0 0
mode# 1 -8 ξ 1 -8 1 -8
20 20 20
ℑ{ω}
10 10 10
0 0 0
-10 -10 -10
-20 -20 -20
-4 -2 0 -4 -2 0 -4 -2 0
ℜ{ω}
Figure10.2. Koopmaneigenfunctionsandeigenvaluedistributionforthethreeobserv-
( )
ablesconsideredinFigure10.1:thestandardDMDalgorithmg (x)=xandg (x)= x |x|2x T ,
( ) DMD 1
g (x)= x |x|2 T. Notethattheobservableg (x)givesthebestapproximationtotheexpectedspec-
2 1
trumofpurelyimaginaryeigenvalues.
ALGORITHM10.4. Koopmandataofobservables.
Y1=[X1; (X1.*abs(X1).^2)]; %% Data observables g1
Y2=[X2; (X2.*abs(X2).^2)]; %% Shifted Data
Once the data matrices are created, which now have 2n rows of data, the DMD al-
gorithm outlined previously can be run with the matricesY1 and Y2 instead of X1
andX2. Nearthereconstructionstage,onlythestatevariablesneedtoberecovered,
whichisdonewiththefollowingcode.
ALGORITHM10.5. Koopmanreconstruction.
q2=[q; (q.*abs(q).^2)];
y0 = Phi2\q2;
q_modes = zeros(r,length(t));
for iter = 1:length(t)
q_modes(:,iter) =(y0.*exp(omega*(t(iter))));
end
q_dmd2 = Phi2*q_modes;
q_dmd = q_dmd2(1:n,:); %% Koopman approximation
Phi = Phi2(1:n,:); %% Koopman eigenfunctions
Thealgorithmproducesbothastateapproximation,sincethefirstncomponents
areactuallythestatevectorx,andtheassociatedKoopmaneigenfunctionsandeigen-
values. Fortheobservables g (x), theonlymodificationisinthedataconstruction.
2

10.2. Nonlinearobservablesforpartialdifferentialequations 165
2.5
|     |     | 2   |     | E   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
2
Error
1.5
|     |     | 1   |     |     |     | E   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
DMD
0.5
E
|     |     |     |     |     |     | →−−− 1 |     |     |
| --- | --- | --- | --- | --- | --- | ------ | --- | --- |
0
|     |     | 0   | 0.5 | 1   | 1.5 | 2 2.5 | 3   |     |
| --- | --- | --- | --- | --- | --- | ----- | --- | --- |
time
E
|     | 100   |     | 2   |     |     |     |     |     |
| --- | ----- | --- | --- | --- | --- | --- | --- | --- |
|     | Error |     |     |     | E   |     |     |     |
10-2
DMD
E
1
10-4
10-6
|     |     | 0   | 0.5 | 1   | 1.5 | 2 2.5 | 3   |     |
| --- | --- | --- | --- | --- | --- | ----- | --- | --- |
time
Figure10.3. ErroranalysisoftheKoopmanreconstructionofthesimulateddatashown
inFigure10.1(a). Thethreeobservablesconsideredinpanels(b)–(d)ofFigure10.1arecompared
against the true solution. The observable corresponding to standard DMD theory is given by
| (x)=x, |                       |     |     |     |                   | (x)andg (x)produceerrors       |     |     |
| ------ | --------------------- | --- | --- | --- | ----------------- | ------------------------------ | --- | --- |
| g      | anditproducestheerror |     |     | E   | . Theobservablesg |                                |     | E   |
| DMD    |                       |     |     | DMD |                   | 1 (x)producesaKoopmanapprox- 2 |     | 1   |
andE ,respectively.Notethatthejudiciouschoiceofobservablesg
| 2   |     |     |     |     |     | 1   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
imationtothedynamicsthatisfourordersofmagnitudebetterthanDMD.Thetoppaneldepicts
theerror(10.10),whilethebottompaneldisplaystheerroronalogarithmicscale.
Inparticular,wewouldhavethefollowing.
| ALGORITHM10.6. |              | Koopmandataofobservables. |     |         |             |     |     |     |
| -------------- | ------------ | ------------------------- | --- | ------- | ----------- | --- | --- | --- |
| Y1=[X1;        | abs(X1).^2]; |                           | %%  | Data    | observables | g1  |     |     |
| Y2=[X2;        | abs(X2).^2]; |                           | %%  | Shifted | Data        |     |     |     |
ThiscanbeusedastheinputdatafortheKoopmandecompositiontoproduceasecond
Koopmanapproximation.
Figure10.1(c)and(d)showstheKoopmanreconstructionofthesimulateddatafor
(x)providesanexceptionalapproximationto
| theobservables(10.9). |     | Theobservableg |     |     |     |     |     |     |
| --------------------- | --- | -------------- | --- | --- | --- | --- | --- | --- |
1
theevolution,whileg (x)isquitepoor. Indeed,theerrorsofthethreeapproximations
2
consideredareshowninFigure10.3,wherethefollowingerrormetricisused:
|     |     | E (t | )=(cid:7)x(t | )−x˜(t | )(cid:7), k=1,2,...,m, |     |     | (10.10) |
| --- | --- | ---- | ------------ | ------ | ---------------------- | --- | --- | ------- |
|     |     | j    | k            | k      | k                      |     |     |         |
wherexisthefullsimulationandx˜ istheDMDorKoopman approximation. Here
j correspondstotheDMDobservableoroneofthetwoobservablesgivenin(10.9).
(x),whichwasjudiciouslychosentomatchthenon-
Withthechoiceofobservableg
1
linearityoftheNLS,theKoopmanapproximationofthedynamicsisfourordersof

| 166 |     |     | Chapter10. | DMDonNonlinearObservables |     |
| --- | --- | --- | ---------- | ------------------------- | --- |
magnitudebetterthan aDMDapproximation. Apoor choice of observables, given
(x),givestheworstperformanceofall.
byg NotealsothedifferenceintheKoopman
2
eigenfunctionsandeigenvalues, asshowninFigure10.2. Inparticular, notethatthe
(x)alignstheeigenvaluesalongtheimaginaryaxis,asis
greatchoiceofobservablesg
1
expected from the dynamics. It further suggests that much better long-time predic-
(x).
tionscanbeachievedwiththeKoopmandecompositionusingg
1
In summary, the example of NLS shows that the Koopman decomposition can
greatly improve the reconstruction and future-state prediction of data. But a suit-
able observable is critical in making this happen. For NLS, a good observable can
beguessedbytheformoftheequation. However,suchaluxuryisrarelyaffordedin
systemswherethedynamicsarenotknown.
| 10.3 Extended | and kernel | DMD |     |     |     |
| ------------- | ---------- | --- | --- | --- | --- |
Williamset al. [301, 302]have recentlycapitalized on theideasof machine learning
byimplementingthekernelmethodandextendedobservables(10.4)withintheDMD
architecture. Intheirformulation,thematricesofobservablesareconstructedasfol-
lows:
|     |     | ⎡             |                       | ⎤                  |          |
| --- | --- | ------------- | --------------------- | ------------------ | -------- |
|     |     | Y=⎣ g(x       | ) g(x ) ···           | g(x )⎦             |          |
|     |     |               |                       | ,                  | (10.11a) |
|     |     |               | 1 2                   | m                  |          |
|     |     | ⎡             |                       | ⎤                  |          |
|     |     | (cid:5)=⎣ g(x | (cid:5)) g(x (cid:5)) | ··· g(x (cid:5) )⎦ |          |
|     |     | Y             |                       | ,                  | (10.11b) |
|     |     |               | 1 2                   | m                  |          |
wheretheDMDalgorithmproducesthematrixdecomposition
|     |     |     | A =Y (cid:5) Y† |     | (10.12) |
| --- | --- | --- | --------------- | --- | ------- |
Y
alongwiththelow-rankcounterpartA˜ . ThisisthestandardtreatmentoftheKoop-
Y
manoperatorreconstructionexceptnowtheoperatorA canbecomputationallyin-
Y
tractabletosolveduetothelargenumberofobservablesspecifiedbythefeaturespace
ofthemachinelearningmethodology. Indeed,itisnotclearthatonecancomputethe
low-rank A˜ duetothesizeof matrixA andthecomputational complexity of the
|     | Y   |     | Y   |     |     |
| --- | --- | --- | --- | --- | --- |
SVD.
TheextendedDMDmethodandthekernelDMDmethodarebothmathematical
techniquesthatfindnumericallyefficientwaystoapproximate A˜ ,whichisafinite-
Y
dimensional approximation of the Koopman operator. In the former method, the
numberofsnapshotsmisassumedtobemuchlargerthanthenumberofobservables
(cid:13)
n,sothat m n. Inthelattertechnique,whichisgenerallyofgreater interest,the
numberofsnapshotsismuchlessthanthenumberofobservables,sothatn(cid:13)m.
In
bothcases,asignificantreductionincomputationalexpensecanbeachievedbygener-
atingtheKoopmanoperatorusingthekerneltrickfromcomputerscience. Thus,both
theextendedDMDandthekernelDMDaresimilartothemethodofsnapshots[262],
whichcomputesPODmodesbyperforminganSVDonamatrixdeterminedbythe
numberofsnapshots.
| 10.3.1 Extended | DMD |     |     |     |     |
| --------------- | --- | --- | --- | --- | --- |
TheextendedDMDmethodwasdevelopedtoreducethecostofevaluatingtheKoop-
man operator when m (cid:13) n. Recall that the goal in constructing theKoopman op-

10.3. ExtendedandkernelDMD 167
erator istogenerate an intrinsiccharacterization of thedynamical system measured
bycomputingthetriplet-pairofKoopman eigenvaluesλ ,Koopmaneigenfunctions
k
ϕ (x),andKoopmanmodesv .
k k
GiventhatthedatamatricesY,Y (cid:5)∈(cid:4)n×m areshortandfatwithm(cid:13)n,onecan
considertheefficientcomputationfortheKoopmanoperator
A =Y (cid:5) Y†
Y
=Y (cid:5) I(cid:4)Y†
(cid:5)
=Y (cid:5) YTYT† Y† (10.13)
! "! "
= Y (cid:5) YT YYT †
=A A†,
1 2
whereIistheidentityinthesecondlineand
A = Y (cid:5) YT, (10.14a)
1
A = YYT. (10.14b)
2
Notethatinthisformulation,bothA andA
∈(cid:4)n×n.
Thus,thesearemuchsmaller
1 2
matrices to compute than the original n×m formulation. This is highly advanta-
geousnotonlyforcomputationalspeedbutalsoformemorystoragewhenmishigh
dimensional. Indeed,thecomputationalcostintheextendedDMDframeworkisde-
terminedbythenumbern offeaturesselectedinsteadofthemuchlargernumberof
snapshots taken [301]. There is another significant advantage. Unlike the formula-
tion(10.12),whichrequiresacomputationallyexpensivepseudoinversecomputation
ofY∈(cid:4)n×m,theextendedDMDformulation(10.13)onlyrequiresapseudoinverseof
thematrixA
∈(cid:4)n×n.
ThearchitectureoftheextendedDMDmethodisillustrated
2
in Figure 10.4. This figure shows that one can trade an expensive matrix computa-
tioninvolvingthepseudoinverseY†fortwomatrixmultiplications. Thesereducethe
matricestomuchsmallersquarematrices,onlyoneofwhichneedstobeinverted.
10.3.2 Kernel DMD
ThekernelDMDmethodisideallysuitedforthephysicallyrelevantcasewhenn(cid:13)
m.Specifically,whenconsideringalargeanddiversesetoffeaturespacevariables,then
then cangrowquicklytobeextremelyhigh-dimensional. Forinstance,Williamset
al.[302]estimatethatusingthespaceofmultivariatepolynomialsuptodegree20on
astate-spaceof(cid:2)256 yieldsn∼O(1030). Thus,a20th-degreepolynomialforafeature
spacewouldyieldacomputationallyintractableproblembecausetheSVDscaleslike
O(n3), or O(1090). Thisis a classic example of the curse of dimensionality. In what
follows, we will use a kernel trick to enact the same computational reduction as in
extendedDMD.Inthiscase,thegoalistousethekernelmethodtoreducethecom-
putational complexity soastobedetermined by thenumber m ofsnapshotstaken,
wherem(cid:20)n.
GiventhatthedatamatricesY,Y (cid:5) ∈(cid:4)n×m arenowtallandskinnywithn (cid:13) m,
onecanconsidertheefficientcomputationfortheKoopman operatorbyprojecting
totheprincipalcomponentspacecapturedbytheSVDofthedatamatrixY:
Y=UΣV ∗ . (10.15)
Thus,whenconsideringtheKoopmaneigenvalueproblem
Ky =λ y , (10.16)
k k k

| 168 |     | Chapter10. | DMDonNonlinearObservables |     |
| --- | --- | ---------- | ------------------------- | --- |
(a)
(cid:5)
|     | Y Y† | A   |     |     |
| --- | ---- | --- | --- | --- |
Y
(cid:1)
(b) ! "
|     | (cid:5) YT | YYT | †   | A†  |
| --- | ---------- | --- | --- | --- |
|     | Y          |     |     | A A |
1 2 Y
(cid:1) (cid:1)
Figure10.4. ExtendedDMDarchitecturewherethenumbermofsnapshotscollectedis
muchgreaterthanthenumberofobservablesn,andexpensivematrixcomputationsaredenotedin
(a)TheKoopmandecompositionwouldrequirecomputingtheinnerproductY(cid:5)Y†.
red. Although
∈(cid:4)n×n,itrequirestheexpensivecomputationofthepseudoinverse
thisgivesthedesiredmatrixA
Y
Y†∈(cid:4)m×n. (b)ExtendedDMDcircumventstheexpensivepseudoinversecomputationbyinstead
computingtwomatricesA ,A ∈(cid:4)n×n. AlthoughthepseudoinverseofA mustbecomputed,it
|     | 1 2 |     |     | 2   |
| --- | --- | --- | --- | --- |
isamuchsmallermatrix. Thus,thecomputationalcostoftheextendedDMDisdeterminedbythe
numbernoffeaturesselectedinsteadofthemuchlargernumbermofsnapshotstaken.
onecanconsiderthattheeigenvectoritselfcanbeconstructedbytheexpansion
=Uyˆ
y . (10.17)
k k
Insertingthisprojectionintotheeigenvalueproblemresultsin
|     | λ y =Ky | ,   |     |     |
| --- | ------- | --- | --- | --- |
k k k
|     | λ Uyˆ =KUyˆ |     |     |     |
| --- | ----------- | --- | --- | --- |
|     | k k         | k   |     |     |
(cid:5)
=Y Y†Uyˆ
! k "
(cid:5)
=Y Y† YVΣ† yˆ
|     |     | ! " | k   |     |
| --- | --- | --- | --- | --- |
=Y (cid:5) VΣ† yˆ
"k
!
=IY (cid:5) VΣ†
yˆ
|     |     | ! " k ! | "   |     |
| --- | --- | ------- | --- | --- |
= YT † YTY (cid:5) VΣ†
yˆ
|     |     | ! " !            | "! " k |     |
| --- | --- | ---------------- | ------ | --- |
|     | =   | YT † YTY (cid:5) | VΣ† yˆ |     |
"k
|     |       | !      | "!          |     |
| --- | ----- | ------ | ----------- | --- |
|     | =U(ΣV | ∗) YTY | (cid:5) VΣ† |     |
yˆ
k
=UKyˆ
, (10.18)
k
whereIistheidentityinthesixthlineandtheKoopman operator isnowevaluated
| bytheexpression |     | !   | "! " |     |
| --------------- | --- | --- | ---- | --- |
∗) (cid:5)
|     | A =(ΣV | YTY | VΣ† . | (10.19) |
| --- | ------ | --- | ----- | ------- |
Y

10.3. ExtendedandkernelDMD 169
A
Y
(a)
Y (cid:5) Y†
(cid:1)
(b)
ΣV ∗ YTY (cid:5) VΣ† A
Y
(cid:1) (cid:1)
Figure10.5.KernelDMDarchitecturewherethenumbermofsnapshotscollectedismuch
smallerthanthenumberofobservablesn,andexpensivematrixcomputationsaredenotedinred.
(a)TheKoopmandecompositionwouldrequirecomputingtheinnerproductY(cid:5)Y†,thusrequiring
theexpensivecomputation of thepseudoinverseY† ∈ (cid:4)m×n and producing theunwieldymatrix
Y† ∈(cid:4)n×n. (b)ExtendedDMDcircumventstheseexpensivecomputationsbyinsteadcomputing
threematrices,whichallproduce(cid:4)m×m matrices. Onlyasingle,trivialpseudoinversemustnow
becomputed, butonthediagonal matrixΣ. Thus, thecomputational costofthekernelDMDis
determinedbythenumbermofsnapshotsratherthanthemuchlargernumbernoffeaturesselected.
Likethe!exten"dedDMDalgor!ithm",theadvantageofthisformulationisthat(ΣV ∗)∈
(cid:4)m×m, YTY (cid:5) ∈(cid:4)m×m,and VΣ† ∈(cid:4)m×m. Thus,assuggested,thecomputationof
theKoopman operator isdeterminedbythenumberofsnapshotstaken ratherthan
thenumberoffeatures. Ofcourse,anSVDoperationisrequiredtoevaluate(10.19).
ButtherequiredΣandVmatricescanbecomputedbyconsideringtheeigenvaluede-
compositionofthe m×m matrixY ∗ YV=Σ2V. Thus,onceagain,allcomputations
areconstrainedbythenumberofsnapshotsmversusthenumberoffeaturesn,where
n (cid:13) m. Figure 10.5 illustrates thekernel DMDcomputational infrastructure. The
kernel DMDcircumventsnotonly theexpensive computation of thepseudoinverse
Y† but the construction of thelargematrixA that resultsfrom the outer product.
Y
Instead, the computation is broken down into three matrix multiplications that are
projectedtothefeaturespaceembeddingU. Thus,low-dimensionalmatricesarepro-
duced,makingtheevaluationofA tractable.
Y
10.3.3 The kernel trick for observables
BoththeextendedDMDandthekernelDMDaimtoreducethecomputationalcost
ofevaluating theapproximation oftheKoopman operator, denoted here by A . In
Y
bothmethods,itisdesirabletotakealargenumberofobservablesandsnapshotsand
producetheKoopmanapproximationA ∈(cid:4)p×p,where p=min(m,n). Ultimately,
Y
thekernelDMDmethodisthemostrelevantinpractice,asthenumberofobservables

| 170 |     |     | Chapter10. | DMDonNonlinearObservables |     |     |
| --- | --- | --- | ---------- | ------------------------- | --- | --- |
(features) canrapidlygrowtomake n extremelyhighdimensional. Itisconjectured
thattakingalargeenough,andrichenough,setofobservablesallowsonetoproduce
anaccuraterepresentationoftheKoopmanoperator.
Kernelmethodsareaclassofalgorithmsusedforgenericpatternanalysistaskssuch
astheclusteringandclassificationofhigh-dimensionaldata. Indeed,theyarenowcom-
monlyusedinmachinelearningtasks,withSVMbeingoneofthemostcommonand
successfulimplementations.Formanydata-intensivealgorithmsthatperformpattern
analysistasks,thedataistypicallyrepresentedinitsrawformbeforebeingexplicitly
transformedintofeaturevectorrepresentationsviaauser-specified featuremap. For
instance,aPCAdeterminesthefeaturespaceviaSVD.However,computingtheSVD
isextremelyexpensive, perhaps prohibitivelyso, whenthedataunderconsideration
ishighdimensional. Incontrast,kernelmethodsrequireonlyauser-specifiedkernel,
i.e.,asimilarityfunctionoverpairsofdatapointsinrawrepresentation. Sojustlike
theextendedandkernelDMDarchitecture,thegoalofthekerneltechniqueistore-
duce thecomputational complexity of agiven problem by intelligentchoices of the
featuresor observables. Inwhatfollows, features andKoopman observables willbe
usedinterchangeably.
In thecontext of theKoopman operator, thekernel trick [53,198,271,21]will
|     | f(x,x (cid:5))thatcanberelatedtotheobservables |     |     |     |     | (x)usedtoconstruct |
| --- | ---------------------------------------------- | --- | --- | --- | --- | ------------------ |
defineafunction g
j
YandY. (cid:5) Considerthesimpleexampleofapolynomialkernel
|     |     |       | !         | "               |     |         |
| --- | --- | ----- | --------- | --------------- | --- | ------- |
|     |     | f(x,x | (cid:5))= | 1+xTx (cid:5) 2 |     |         |
|     |     |       |           | ,               |     | (10.20) |
wherexandx (cid:5) aredatapointsin(cid:2)2. Whenexpandedout,thekernelfunction
|       | !             |            | "          |                     |              |          |
| ----- | ------------- | ---------- | ---------- | ------------------- | ------------ | -------- |
| f(x,x | (cid:5))= 1+x | (cid:5)+x  | (cid:5) 2  |                     |              |          |
|       |               | x          | x          |                     |              |          |
|       | (cid:4)       | 1 1        | 2 2        |                     |              | (cid:5)  |
|       |               | (cid:5)+2x | (cid:5)+2x | (cid:5) (cid:5)+x2x | (cid:5)2+x2x | (cid:5)2 |
|       | = 1+2x        | x          | x          | x x x               |              |          |
|       |               | 1 1        | 2 2        | 1 2 1 2             | 1 1          | 2 2      |
=YT(x (cid:5))Y(x),
(10.21)
provided
|     |     |     | ⎡   | ⎤   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
(cid:9)1
|     |     |     | ⎢   | ⎥           |     |     |
| --- | --- | --- | --- | ----------- | --- | --- |
|     |     |     | ⎢   | (cid:9)2x ⎥ |     |     |
1
|     |     |        | ⎢       | ⎥      |     |         |
| --- | --- | ------ | ------- | ------ | --- | ------- |
|     |     | Y(x)=⎢ | (cid:9) | 2x ⎥   |     |         |
|     |     |        | ⎢       | 2 ⎥.   |     | (10.22) |
|     |     |        | ⎢       | 2x x ⎥ |     |         |
|     |     |        | ⎣       | 1 2 ⎦  |     |         |
2
x
1
x 2
2
Notethatforthiscase,boththeKoopmanobservablesin(10.22)andthekernelfunc-
tion(10.20)areequivalentrepresentationsthatarepairedthroughtheexpansion(10.21).
However, the kernel trick is basically centered around the realization that (10.20) is
asignificantlymoreefficient representation ofthepolynomial variables thatemerge
from expanding as in (10.21). More precisely, instead of defining our typical Koop-
manobservables g (x)usedtoconstruct(10.22),weinsteaddefinethekernelfunction
i
(10.20),asitprovidesanidealrepresentationofthefeaturespaceforthevariouskernels
selectedandprovidesanimplicitcomputationoftheinnerproductsrequiredforthe
Koopman operator. Indeed, thecomputation oftheobservables reduces toasimple
innerproductbetweenvectorpairs,providinganefficientalgorithmforproducingthe
featurespace(Koopmanobservables)representation.
Toillustratethecomputationalsavingsofthekerneltrickmoreclearly,considera
polynomialkernelofdegree p actingondatavectorsxandx (cid:5) in(cid:2)n. Inthiscase,the

10.3. ExtendedandkernelDMD 171
kernelmethodsimplydefines
|     |                 | ! "             |         |
| --- | --------------- | --------------- | ------- |
|     | f(x,x (cid:5))= | 1+xTx (cid:5) p |         |
|     |                 | ,               | (10.23) |
(cid:5)
whichrequiresthecomputation oftheinnerproduct α =xTx . Thisrequires(cid:23)(n)
operationsandproducestheconstantα. Itisthentrivialtofinishcomputingf(x,x (cid:5))=
(1+α)p.
Thus,overall,thecomputationalcostforthis pth-degreepolynomialkernel
is (cid:23)(n). In contrast, to construct the equivalent set of observables using Y would
requireavectorofobservablesoflengthO(n2),whichtakestheform
|     | ⎡   | ⎤   |     |
| --- | --- | --- | --- |
1
|     | ⎢   | ⎥   |     |
| --- | --- | --- | --- |
x
|     | ⎢   | 1 ⎥ |     |
| --- | --- | --- | --- |
|     | ⎢   | . ⎥ |     |
|     | ⎢   | . ⎥ |     |
|     | ⎢   | . ⎥ |     |
|     | ⎢   | ⎥   |     |
|     | ⎢   | x ⎥ |     |
|     | ⎢   | n ⎥ |     |
x2
|     | ⎢   | ⎥     |     |
| --- | --- | ----- | --- |
|     | ⎢   | 1 ⎥   |     |
|     | ⎢   | . . ⎥ |     |
|     | ⎢   | . ⎥   |     |
|     | ⎢   | ⎥     |     |
|     | ⎢   | x2 ⎥  |     |
|     | ⎢   | ⎥     |     |
|     | ⎢   | n ⎥   |     |
x p
|     | ⎢      | 1 ⎥   |         |
| --- | ------ | ----- | ------- |
|     | ⎢      | . ⎥   |         |
|     | Y(x)=⎢ | . ⎥ . | (10.24) |
|     | ⎢      | . ⎥   |         |
|     | ⎢      | ⎥     |         |
|     | ⎢      | x p ⎥ |         |
|     | ⎢      | n ⎥   |         |
|     | ⎢      | x x ⎥ |         |
|     | ⎢      | 1 2 ⎥ |         |
|     | ⎢      | x x ⎥ |         |
|     | ⎢      | 1 3 ⎥ |         |
|     | ⎢      | . ⎥   |         |
|     | ⎢      | . ⎥   |         |
|     | ⎢      | . ⎥   |         |
|     | ⎢      | ⎥     |         |
x x
|     | ⎢   | 1 p ⎥ |     |
| --- | --- | ----- | --- |
|     | ⎢   | ⎥     |     |
|     | ⎢   | x x ⎥ |     |
|     | ⎢   | 2 3 ⎥ |     |
|     | ⎣   | . ⎦   |     |
. .
x x
p p
Once it was formed, one would still be required to compute YT(x (cid:5))Y(x). This is a
significantlylargercomputation thanthekernelform(10.23). Indeed,foralargeset
ofobservables,thekerneltrickenablestheactualcomputationoftheinnerproducts,
whiletheform(10.24)canremainintractable.
Thechoiceofkernelisimportant. Althoughthereisaninfinitesetofpossibilities,
a few common choices are typically used in machine learning. Thefollowing three
kernelsaretheworkhorsesofSVM-baseddatamethods:
! "
polynomialkernel(degree p) f(x,x (cid:5))= a+xTx (cid:5) p , (10.25a)
! "
|                      |     | f(x,x (cid:5))=exp −a|x−x (cid:5)|2 |          |
| -------------------- | --- | ----------------------------------- | -------- |
| radialbasisfunctions |     | ,                                   | (10.25b) |
! "
(cid:5))=tanh (cid:5)+a
| sigmoidkernel |     | f(x,x xTx . | (10.25c) |
| ------------- | --- | ----------- | -------- |
The advantages of the kernel trick are quite clear. For the polynomial kernel, for
instance,a20th-degreepolynomial(p =20)using(10.25a)istrivial.
Infact,theker-
nelfunctiondoesnotcomputealltheinnerproductsdirectly. Incontrast,usingour
standardKoopmanobservables g(x )wouldrequireonetoexplicitlywriteoutallthe
j
termsgeneratedfroma20th-degreepolynomialonan n-dimensionaldataset,which
isamonumentalcomputationaltaskincomparison.
Inpractice,then,insteadofdefiningtheobservablesYTY (cid:5)
in(10.19)with(10.11),
wewilldefinetheobservablesYusingthekernel f(x,x (cid:5))forproducinginnerproducts

| 172 |     |     | Chapter10. |     | DMDonNonlinearObservables |     |
| --- | --- | --- | ---------- | --- | ------------------------- | --- |
associatedwiththefeaturespace. Specifically,wewillconsidertheobservablematrix
elementsasdefinedby
|     |     |     | YTY (cid:5)(j,k)= | f(x ,x | (cid:5)), | (10.26) |
| --- | --- | --- | ----------------- | ------ | --------- | ------- |
j
k
where (j,k) denotes the jth row and kth column of the correlation matrix, and x
j
(cid:5)
and x are the jth and kth columns of data. Thekernel DMD formulation (10.19)
k
alsorequiresthatwecomputethematricesVandΣ.
Recallthedefinition(10.15),so
that
|     |     |     | Y ∗ YV=Σ2V. |     |     | (10.27) |
| --- | --- | --- | ----------- | --- | --- | ------- |
∗
Asbefore, wecancomputethematrixelementsofY Yusingthekernelmethod,so
that
|     |     |     | ∗ Y(j,k)= | f(x | )   |         |
| --- | --- | --- | --------- | --- | --- | ------- |
|     |     |     | Y         | ,x  |     | (10.28) |
j k
where(j,k)denotesthe
|     |     | jthrowandkthcolumnofthecorrelationmatrix,andx |     |     |     | and |
| --- | --- | --------------------------------------------- | --- | --- | --- | --- |
j
x arethe jthand kthcolumnsofdata. Thus,allofthekeyinnerproductsarepro-
k
ducedbyusingtheefficientkernelmethodandprojectingdirectlytothefeaturespace.
Allthatremainsistochoose akernel. Oncedetermined, theinnerproducts(10.26)
and(10.28)onthekernelfunctionallowustoevaluatethematrixA via(10.19). As
|     |     |     |     | f(x,x) | = Y |     |
| --- | --- | --- | --- | ------ | --- | --- |
a final note, if the linear kernel function xTy is chosen, the kernel DMD
reducestothestandardDMDalgorithm.
| 10.4 | Implementing | extended | and | kernel | DMD |     |
| ---- | ------------ | -------- | --- | ------ | --- | --- |
TodemonstratehowtheextendedandkernelDMDmethodsareimplementedinprac-
tice,weonceagainreturntotheexamplecodefortheNLSAlgorithm10.3. Thistoy
modelwillexemplify themeritsofandpotentialchallengeswiththemethodsdevel-
opedintheprecedingsection.
FortheextendedDMDtechnique,itisassumedthatthenumberofsnapshotstaken
istypicallyfarlargerthanthenumberofstatevariables, orobservables, recorded in
the data matrix Y. In the example Algorithm 10.3, only 21 snapshots of data were
collected relativetothe512Fouriermodes (statevariables) used torepresent theso-
lution. Instead,wecouldtakealargenumberofsnapshotsbysimplyredefiningour
timevariablewiththefollowingcode.
|     | ALGORITHM10.7. | ExtendedDMDsampling. |     |     |     |     |
| --- | -------------- | -------------------- | --- | --- | --- | --- |
slices=2000;
|     | t=linspace(0,2*pi,slices+1); |     |     | dt=t(2)-t(1); |     |     |
| --- | ---------------------------- | --- | --- | ------------- | --- | --- |
Thisgives2000snapshotsrelativetothe512statemeasurements,thussuggesting
theuseoftheextendedDMDalgorithmoutlinedinFigure10.4. Thefollowingcode
producesthematricesA andA thatareusedinefficientlycomputingA in(10.13).
|     |                | 1                                | 2                |     | Y   |     |
| --- | -------------- | -------------------------------- | ---------------- | --- | --- | --- |
|     | ALGORITHM10.8. | ExtendedDMDKoopmanapproximation. |                  |     |     |     |
|     | X=usol.’;      | X1=(X(:,1:end-1));               | X2=(X(:,2:end)); |     |     |     |
tic
Ay1=X2*pinv(X1);
toc

10.4. ImplementingextendedandkernelDMD 173
1000
500
ℑ{ω }
k
0
-500
-1000
-10000 -8000 -6000 -4000 -2000 0 2000
1000
◦Fig.10.4(a)
500 ◦Fig.10.4(b)
ℑ{ω }
k
◦Fig.10.5(b)
0
-500
-1000
-1000 -500 0 500
ℜ{ω }
k
Figure 10.6. Comparison of eigenvaluespectrum for the extended (black circles) and
kernel(bluecircles)DMDmethods. Thefullcomputationofthespectrumisalsoshown(redcircles).
ThelogarithmsoftheeigenvaluesofA ,dividedbyΔt,areplottedinthepanels.
Y
tic
A1=X2*X1.’;
A2=X1*X1.’;
Ay2=A1*pinv(A2);
toc
Notethatthetic-toccommandsinMATLABareusedtoestimatethecomputational
timefor thetwo procedures. Extended DMD (Figure 10.4(b)) computes the spectra
approximatelyanorderofmagnitudefasterthanthestandardmethod(Figure10.4(a))
forthematricesused. Thecomputationalsavingsscaleswiththesizeofthematrices
andthedisparitybetweenthenumberofsnapshotsandthenumberofstatevariables
recorded,i.e.,m(cid:13)n.
The extended DMD method can be compared to the full spectral computation.
Figure 10.6 shows both the full computation of the eigenvalues A (red circles) and
Y
theextendedDMDapproximationtotheeigenvalues(blackcircles).
The kernel DMD is also considered using the kernel method for evaluating the
observables. For this case, we once again consider a more limited snapshot matrix
givenbyAlgorithm10.9.

174 Chapter10. DMDonNonlinearObservables
ALGORITHM10.9. KernelDMDsampling.
slices=200;
t=linspace(0,2*pi,slices+1); dt=t(2)-t(1);
Inaddition,aradialbasisfunctionkernelisassumedforthekernelfunction
! "
f(x,x (cid:5))=exp −|x−x (cid:5)|2 . (10.29)
Theabsolute value isimportant for thecaseof theNLS equation considered dueto
thenonlinearevolution ofthephase. Thefollowingcodecomputes theobservables
fortheDMDalgorithmusingtheradialbasisfunctionkernel.
ALGORITHM10.10. KernelDMDapproximation.
X=usol.’; X1=(X(:,1:end-1)); X2=(X(:,2:end));
[n,m]=size(X);
for j=1:m-1
for jj=1:m-1
YtYp(j,jj)=exp(-abs((X1(:,jj)-X2(:,j)).’*(X1(:,jj)-X2(:,j)))^2
);
YsY(j,jj)=exp(-abs((X1(:,jj)-X2(:,j)).’*(X1(:,jj)-X2(:,j)))^2
);
end
end
[V,Sig]=eig(YsY);
Ay=(Sig*V’)*(YtYp)*(V/Sig);
[W,D]=eig(Ay);
TheeigenvaluesofthematrixapproximatingA (seeFigure10.5)areshowninFigure
Y
10.6 (blue dots). Comparison can be made totheextended DMD approximation as
well.
One of the most challenging aspects of Koopman theory, extended DMD, and
kernelDMDistheselectionofobservables, orfunctionsofthestate-spacevariables.
ThisremainsanopenquestionintheKoopmanarchitecture: whatarethemostaccu-
rate g (x)tobeusedformappingafinite-dimensionalnonlineardynamicalsystemto
j
theKoopmanrepresentationofahigh-dimensionallinearoperator? Tohighlightthe
significance ofthisquestion, consider thatanumber ofkernels could be used toap-
proximatethedynamicsoftheNLS.So,insteadofsimplyconsideringtheradialbasis
functions,wecanalsoconsiderthreeadditionalobservables:
! "
f(x,x (cid:5))= 1+xTx (cid:5) 20 , (10.30a)
! "
f(x,x (cid:5))= a+|xT||x (cid:5)| 20 , (10.30b)
f(x,x (cid:5))=exp(−xTx (cid:5)). (10.30c)
Thefirstisthestandardpolynomialkernelof20thdegree. Thesecondinsteadtakes
theabsolutevalueofthevariableinapolynomialvariabletoremovethephase,andthe
thirdisaGaussiankernelthatusesthesameinnerproductasthepolynomialkernel.

10.4. ImplementingextendedandkernelDMD 175
| 100 | 100 |     |     |
| --- | --- | --- | --- |
| 50  |     | 50  |     |
ℑ{ω }
k
| 0       |      | 0       |      |
| ------- | ---- | ------- | ---- |
| -50     | -50  |         |      |
| -100    | -100 |         |      |
| -2000 0 | 2000 | -2000 0 | 2000 |
| 100     | 100  |         |      |
| 50      |      | 50      |      |
ℑ{ω }
k
| 0       |      | 0       |      |
| ------- | ---- | ------- | ---- |
| -50     | -50  |         |      |
| -100    | -100 |         |      |
| -2000 0 | 2000 | -2000 0 | 2000 |
| ℜ{ω     | }    | ℜ{ω     | }    |
|         | k    |         | k    |
Figure10.7. Comparisonofdifferentspectrageneratedfromthekernelmethod. Clock-
wisefromtoprightarethekernels(10.30(a)),(10.30(b)),(10.29),and(10.30(c)). Notethetremen-
dousvariabilityinthespectrumfromthedifferentkernels.ThelogarithmsoftheeigenvaluesofA ,
Y
dividedbyΔt,areplottedinthepanels.
Thecodetoproducethesethreekernels,aswellastheoriginalradialbasisfunction,is
giveninAlgorithm10.11.
ALGORITHM10.11. Differentkernelapproximations.
YtYp1(j,jj)=(1+((X1(:,jj)).’)*(X2(:,j)))^p;
YsY1(j,jj)=(1+((X1(:,jj)).’)*(X1(:,j)))^p;
YtYp2(j,jj)=(1+(abs(X1(:,jj)).’)*abs(X2(:,j)))^p;
YsY2(j,jj)=(1+(abs(X1(:,jj)).’)*abs(X1(:,j)))^p;
YtYp3(j,jj)=exp(-abs((X1(:,jj)-X2(:,j)).’*(X1(:,jj)-X2(:,j)))
^2 );
YsY3(j,jj)=exp(-abs((X1(:,jj)-X2(:,j)).’*(X1(:,jj)-X2(:,j)))
^2 );
YtYp4(j,jj)=exp(-abs((X1(:,jj).’)*(X2(:,j))));
YsY4(j,jj)=exp(-abs((X1(:,jj).’)*(X2(:,j))));
Thesethreenewkernelsarecomparedtoeachotherandtheradialbasisfunction
already used in Figure 10.6. Figure 10.7 shows the spectra generated by these four
kernels. Notethetremendousvariabilityoftheresultsbasedonthechoiceofkernel.
Ultimately, much likethe NLS example considered previously, thechoice ofkernel
must be carefully selected for either the extended or kernel DMD to give anything
reasonable. Cross-validation techniquescould potentiallybeusedtoselectasuitable

| 176 | Chapter10. | DMDonNonlinearObservables |
| --- | ---------- | ------------------------- |
kernelforapplicationsofinterest. Itcouldalsoensurethatoverfittingofthedatadoes
notoccur.

Chapter 11
Epidemiology
Arresting the spread of infectious diseases is a fundamental objective for the global
healthcommunity. Numerousat-riskindividualsandsocietiesasawholebenefitfrom
adecreaseininfectiousdisease. Theeradicationofsmallpoxthroughhumaninterven-
tionisasubstantialhistoricalachievement. Childrenarenolongersubjecttothepo-
tentiallyfataldisease;further,withouttheneedtovaccinatechildrenagainstsmallpox,
resourcescanbereallocatedtootherinfectiousdiseases. Poliomyelitis,alsoknownas
polio,willlikelyjoinsmallpoxasthesecondhumaninfectiousdiseaseeradicated,rid-
dingtheworld ofa devastatingdisease thatparalyzes children. Withtheincrease in
datafromadvancedsurveillancesystemsfordisease,computationalresourcesformod-
elingandanalysis,andmultibilliondollarinterventioneffortsforvaccinesandvector-
controlprograms, humanityispoised tomakesubstantialgainsagainstanumberof
infectious diseases. For example, the Bill and Melinda Gates Foundation is focused
on supporting global health initiatives, such as the fight against polio, having pro-
vidednearlythirty-sevenbilliondollarsingrantssinceinception[28]. Inthischapter,
wedescribehowDMDcanhelpanalyzeinfectiousdiseasedataandsupportongoing
eradicationefforts.
Thespreadofinfectiousdiseasecanbeachallengetomodelduetothelackofasin-
glesetofphysics-based governingequations. Further, theunderlyingdiseasesystem
canbemathematicallymodeledwithalargevarietyofmethods,includingdeterminis-
ticordinarydifferentialequations,stochasticdifferentialequations,andmicrosimula-
tionsviaagent-basedmodels[157].TheadvantageouscharacteristicsofDMD,namely
theequation-freeaspectofoperatingsolelyondatasnapshots,canhelpintheanalysis
of infectious disease data. DMD is a powerful method that can help with the large
numberofmeasurementsandthenonlineardynamicswithinthedataaswellasiden-
tifyimportantcoherentspatiotemporal structuresofdiseasespread[224]. Webegin
bydescribinghowDMDcanbeformulatedforinfectiousdiseasedata. Twoexamples
are presented that include data of actual infectious disease spread: flu in the United
StatesandmeaslesintheUnitedKingdom.
11.1 Modeling infectious disease spread
Mathematically modeling the spread of infectious disease has a rich history, going
back to the early twentieth century with the seminal work of Kermack and McK-
177

178 Chapter11. Epidemiology
Figure11.1. Imagesrepresentinginfectiousdiseasespread. Theleftpanelillustrateshu-
mansinteractingaroundacommonwatersource. Therightpanelindicatesacommondiseasevec-
tor: themosquito.Avectorisanyspeciesthattransmitsapathogentoanotherspecies.Inthecaseof
malaria,themosquitoactsasavectorformalariaspreadinginhumanpopulations. Reprintedwith
permissionfromtheInstituteforDiseaseModeling.
Time
noitalupoP Compartmental Model
Susceptible Infected Recovered
Figure11.2. Theleftpanelillustratesathree-compartmentdynamicalmodelwiththree
states(SIR).Therightpanelshowsanepidemiccurveintime.Thecolorsofthetrajectoriescorrespond
tothecompartmentstates.
endrick[159]. Oneoftheprimarygoalsofcomputationalepidemiologyistoinvesti-
gatehowapopulationinteractswithapathogeninthecontextofaplethoraofcomplex
phenomena, such as the environment, heterogeneity in the population, and demo-
graphics. Figure11.1illustratestwocomplexdiseaseinteractions: peopleinteracting
atalocalwatersourceandthemosquitoasanintegralpartofthetransmissioncycle
ofmalaria. Oneoftheearlyinnovationsinmodelingwastoabstractthepopulation
intogroupsaccordingtotheirdiseasestatus. Forexample,peoplethataresusceptible
toacquiringadiseasearegroupedintoastatecalledS.Thepopulationthatiscurrently
infectedwiththediseaseisgroupedintothestateIandtherecoveredinR.Thesestates
giverisetoamodelcalledSIR.Eachindividual inapopulation isthusgrouped into
oneofthreedynamicalstatesorcompartments,asintheleftpanelofFigure11.2. This
abstractionallowsforamuchlowerdimensionaldynamicalmodeltobeinvestigated
versusmodelingeachindividualinthepopulationseparately. Anexampleofonesuch
modelisasfollows:

11.2. Infectiousdiseasedata 179
dS
(cid:7)n
i =− β S I ,
dt j i j
j=1
dI
(cid:7)n
i = β S I −γI , (11.1)
dt j i j i
j=1
dR
i = γI ,
dt i
whereβisaninfectiousparameterandγ istherateofrecovery. Thesetwoparameters
helpdefineanimportantepidemiologicalcharacteristic: thebasicreproductionnum-
berdefinedbyR =β/γ. IfR >1,thedisease-freesolutionof(11.1),wheretheentire
0 0
population iscontainedincompartmentS,isunstable. Theintroductionofasingle
infectedindividualwouldcauseanepidemic. R representshowmanypeoplearein-
0
fected,onaverage,byasingleinfectionintoanaivepopulation. Figure11.2showsan
epidemiccurvefromaSIR-typemodel. Alargenumberofmodelshavebeenheuristi-
callyconstructedtostudydifferentdiseasesandenvironmentalsituations;see[9,157]
foranextensivedescriptionofcompartmentalmodelsbothdeterministicandstochas-
tic,aswellasagent-basedmodels,whereeachindividualismodeledindependently.
The construction of a compartmental model to represent an infectious disease
withinapopulation requiresaconsiderablenumberofmodelingchoices. Thenum-
ber of states within these models can be combinatorially large when considering a
varietyofheterogeneitieswithinthepopulationand/orpathogen. In(11.1),theindex
i couldrepresentdifferentagegroups,wheretheinfectiousnessofthediseaseβ isage
i
dependent. Consider(11.1)withmoreindicesrepresentingdifferentheterogeneities.
Tofittheparametersofthismodel,eitherextensiveknowledgeofthesystemorasig-
nificant amount of dataisrequired. Instead ofinvestigatingthe spread of infectious
diseasewithmodelssuchasthese,DMDcanbeusedtodiscoverimportantdynamical
characteristicssolelyfromthedata.
11.2 Infectious disease data
DMD can analyze snapshots of infectious disease datafrom experiments, numerical
simulations, or historical records to extract coherent spatiotemporal patterns. Data
collectedfromseparatespatiallocationscanbeformedintovectorsrepresentingstate
snapshotsthat evolve in time. Figure 11.3 illustrates thecollection of dataand how
toform it intodata matrices. Influid dynamics, themeasured statex isclearly re-
k
latedtothephysics,forexample,thevelocity,vorticity,andstreamfunctionsateach
discretizedspatialgridpoint. Forwell-curateddiseasedata,asfoundintheoutputof
detailednumericalsimulations,thechoiceofstatesx maybeequallywelldefined,for
k
example,thenumberofinfectionsinagivenspatialnode. Fordatacollectedfromthe
field,anaggregationstepisrequiredacrossbothspaceandtime. Oftenthedataarrives
intheformofindividualpatientrecordswithatimeandlocationstamp. Toformthe
data matrices, the records have to be binned in space and time. Temporally resolv-
ingtheindividualrecordsdependsonthetimescalesinvolvedindiseasetransmission.
Onenaturalchoiceforunitsoftimeistheaveragedurationofanincubationforthe
disease. Inspace, politicallydefined boundaries such asstates, counties, orcitiesare
oftenused. Afterdecidingontheaggregation,eachpairofstatesnapshotsx andx
k k+1

| 180 |     |     |     |     |     |     | Chapter11. | Epidemiology |     |
| --- | --- | --- | --- | --- | --- | --- | ---------- | ------------ | --- |
Experiments
|     |     | Numerical |     |     | Laboratory |     | Historical |     |     |
| --- | --- | --------- | --- | --- | ---------- | --- | ---------- | --- | --- |
noitcelloC ataD
20042005200620072008200920102011201220132014
State Snapshots
Data Matrices
|     |     | in Time            |         |     |     |     | ⎡      |     | ⎤   |
| --- | --- | ------------------ | ------- | --- | --- | --- | ------ | --- | --- |
|     |     | State Measurements |         |     |     | X=  | ⎣x x x | ··· | x ⎦ |
|     |     |                    |         |     |     |     | 1 2 3  |     | m−1 |
|     |     |                    |         |     |     |     | ⎡      |     | ⎤   |
|     |     | x x x x            | x       |     |     |     |        |     |     |
|     |     | 1 2 3              | 4 ··· m |     |     |     | ⎣x     |     | ⎦   |
|     |     |                    |         |     |     | X = | x x    | ··· | x   |
|     |     |                    |         |     |     |     | 2 3 4  |     | m   |
Figure11.3. Anillustrationregardingthecollectionofdatafromavarietyofsources.
Also,thesnapshotdataiscollectedintothedatamatricesforDMD.Reprintedwithpermissionfrom
OxfordUniversityPress;figureadaptedfrom[224].
canbecollectedandformedintotheDMDdatamatrices:
|     |     | ⎡       |     | ⎤   |             |     | ⎡       |     | ⎤   |
| --- | --- | ------- | --- | --- | ----------- | --- | ------- | --- | --- |
|     |     | | |     |     | |   |             |     | | |     |     | |   |
|     | X=⎣ |         |     | ⎦   |             | =⎣  |         |     | ⎦   |
|     |     | x x ... | x   |     | , X (cid:5) |     | x x ... | x   | ,   |
|     |     | 1 2     |     | m−1 |             |     | 2 3     |     | m   |
|     |     | | |     |     | |   |             |     | | |     |     | |   |
whereeachcolumnrepresentsadifferentsnapshotintime. Eachrowdescribesaspe-
cificstateofthesystem,forexample,thenumberofnewdiseasecasesinvolvingchil-
dren, at a given spatial location. DMD does not require sequential time-series data,
where x ,x ,...,x are measured from a single trajectory in phase space. The data
|     | 1   | 2 m |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
canbeoftheform
|     |     | ⎡       |       | ⎤   |         |     | ⎡               |         | ⎤     |
| --- | --- | ------- | ----- | --- | ------- | --- | --------------- | ------- | ----- |
|     |     | | |     |       | |   |         |     | | |             |         | |     |
|     | X=⎣ |         |       | ⎦   | (cid:5) | =⎣  | (cid:5) (cid:5) | (cid:5) | ⎦     |
|     |     | x x ... | x m−1 |     | , X     |     | x x ...         | x       | m−1 , |
|     |     | | 1 | 2 |       | |   |         |     | | 1 | 2         |         | |     |
(cid:5)
wherethedynamicsrelate x tox , but x ,x ,... may benonsequential. Thisisan
|     |     |     | k   | k   | 1   | 2   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
importantdistinction,especiallyifDMDisbeingapplied todatacollected fromnu-
merical simulations. In this case, the simulation can be executed with a variety of
initialconditionsrepresentingdifferentareasofphasespace.
| 11.3 DMD | for | infectious | disease |     | data |     |     |     |     |
| -------- | --- | ---------- | ------- | --- | ---- | --- | --- | --- | --- |
Figure11.4illustratestheDMDcomputationforinfectiousdiseasedata. Thecollec-
tionofeigenvaluesandtheirrespectivedynamicmodesrepresentthespatiotemporal
patternsdiscoveredwithinthedataset. Theeigenvaluesofferdynamiccharacteristics
suchasgrowth/decayandoscillatorybehaviorofeachdynamicmode. InFigure11.4,
twopairsofcomplexeigenvaluesarerepresentedwithredandblueopencircles. The
eigenvalues are plotted in the complex plane for a discrete dynamical system. Note

| 11.4. Examples |     |     |     |     | 181 |
| -------------- | --- | --- | --- | --- | --- |
Dynamic Mode Decomposition on infectious disease data
A=XX†
Find the dynamic properties of
| SVD and Truncation |     | Eigenvalue Spectrum |     | Dynamic Modes |     |
| ------------------ | --- | ------------------- | --- | ------------- | --- |
| X≈UΣV∗             |     | A˜ =UXVΣ−1          |     | Φ=XVΣ−1W      |     |
A˜W=WΛ
| U Σ | V∗  |     |     | Magnitude |     |
| --- | --- | --- | --- | --------- | --- |
1.0
imag(λ)
| σ 1σ | V   |     |     |     | 0 . 8 |
| ---- | --- | --- | --- | --- | ----- |
... 1
| 2              |     |     |     |     | 0 . 6 |
| -------------- | --- | --- | --- | --- | ----- |
| U1U2···Ur ...σ |     |     |     |     | 0 . 4 |
| r              | V r | 3   |     |     |       |
|                |     |     | 1   |     | 0 . 2 |
real(λ)
0.0
Phase
| U 1 |     |     | 2   |     | 1.0 |
| --- | --- | --- | --- | --- | --- |
|     | σ   | 4   |     |     |     |
|     | i   |     |     |     | 0.8 |
| U   |     |     |     |     | 0.6 |
| 2   |     |     |     |     | 0.4 |
i
0.2
Discrete-time eigenvalues λ
0.0
Figure11.4. AdepictionoftheDMDalgorithmforinfectiousdiseasedata. Reprinted
withpermissionfromOxfordUniversityPress;figureadaptedfrom[224].
thatiftheeigenvaluesarewithintheunitcircle,theyarestable. Ifoutside,theeigen-
valuesareunstable. Onepairofeigenvaluesisonthecomplexunitcircle,representing
apurelyoscillatorymode. Interpretingtheoscillatoryfrequencyinthecomplexplane
foragivenΔt canbedifficult. Instead,thediscreteeigenvaluecanbeconvertedina
continuousoscillatoryfrequencybytherelationship
imag(ln(λ ))
j
|     |     | frequency = |      | .   | (11.2) |
| --- | --- | ----------- | ---- | --- | ------ |
|     |     | j           | 2πΔt |     |        |
Therelationshipbetweendiscrete-andcontinuous-timeeigenvalueswasdiscussedin
ω =
Chapter 1. In this chapter, we often refer to the continuous-time frequencies
ln(λ)/Δt for interpretability. For example, examining continuous frequencies with
unitsof(1/year)canbemoreconvenientthanwiththeirdiscreteeigenvaluecounter-
parts.
Thedynamicmodesofferarichsetofinformationaboutthediseasesystem. For
eachmode,twoimportantpiecesofinformationareincludedforeachelementofthe
modevector. Theabsolutevalueoftheelementprovidesameasureofthespatialloca-
tion’sparticipationforthatmode. Iftheelementiscomplexvalued,theanglebetween
therealandimaginarycomponentsoffersadescriptionofthephaseofthatelementrel-
ativetotheothersoscillatingatthefrequencyassociatedwiththatmode. Figure11.4
showshowasingledynamicmodecan beplotted intermsofmagnitudeand phase,
whereeachelementofthedynamicmodeisalocationonthemapofthecontiguous
UnitedStates.
11.4 Examples
Inthissection,DMDisappliedtotwoinfectiousdiseaseexamples. Foreachofthese
examples, adiscussionisincludedexaminingboththedataandtheoutputofDMD.
EachexampleshowshowDMDcanextracttherelevantspatiotemporalmodesfrom
thedata.

| 182 |     |              |     |     |                    |     | Chapter11. |             | Epidemiology |
| --- | --- | ------------ | --- | --- | ------------------ | --- | ---------- | ----------- | ------------ |
|     |     | (a) Raw Data |     |     | (c) Mode Selection |     | (d)        | Discrete    |              |
|     |     | 2x 104       |     |     |                    |     |            | Eigenvalue  |              |
0.5
Spectrum
|     |             | 1.5            |                                    |                        | 0.4              |                   |         |         |      |
| --- | ----------- | -------------- | ---------------------------------- | ---------------------- | ---------------- | ----------------- | ------- | ------- | ---- |
|     |             | 1              |                                    |                        | 0.3              |                   |         |         |      |
|     |  ulF elgooG |                |                                    |                        | 0.2              |                   | real(λ) |         |      |
|     |             | 0.5            |                                    |                        | 0.1              |                   |         |         |      |
|     |             | 020            |                                    |                        | 00               | 1 2 3             | 4 5     |         |      |
|     |             | 04 2 0 05      | 20 06 2 0 07 2 00 8 2 0 0 9 2 01 0 | 20 1 1 20 12 201 3 2 0 | 1 4              | F requ ency  (1/y | r)      |         |      |
|     |             | (b) D a t a  S | n a p s h o t s   i n   T i m      | e   N o rm a l i z     | e d              |                   |         | imag(λ) |      |
|     |             |                |                                    |                        | (e) Dynamic Mode |                   |         |         |      |
|     |             | States         |                                    |                        |                  |                   |         |         | 11.0 |
0.8
|     |     | Health R |     |     |     |     |     |     | .05.6 Phase |
| --- | --- | -------- | --- | --- | --- | --- | --- | --- | ----------- |
(year)
0.4
0.2
Cities
0.0 0
20042005200620072008200920102011201220132014
Figure11.5. AnillustrationshowingthedatafromtheGoogleFluTrendtoolandthe
output of DMD. (a) shows the raw data of four states’ timeseries. (b) shows all of the locations;
eachtimeserieshasbeennormalized. (c)showsthemodeselectionplot. (d)illustratesthediscrete
eigenvaluedistribution. (e)showsthephaseofeachelementofadynamicmodeassociatedwiththe
yearlyfrequency. Reprinted with permission from Oxford UniversityPress; figure adapted from
[224].
| 11.4.1 | Google | Flu Trend |     |     |     |     |     |     |     |
| ------ | ------ | --------- | --- | --- | --- | --- | --- | --- | --- |
Google has analyzed how specific search terms can be indicators for predicting the
spread offluwithintheUnited States. Theoutput oftheanalysishasbeen publicly
distributedastheGoogleFluTrendtool,providingspatiotemporaldataoffluinthe
UnitedStates[113].
|     |     |     | Despiterecent | scientificinvestigationscastingdoubt |     |     |     |     | on theva- |
| --- | --- | --- | ------------- | ------------------------------------ | --- | --- | --- | --- | --------- |
lidityoftheGoogleFlupredictions[171],thedatasetcanbeusedasanexamplefor
applyingDMD.Inthisexample,wefocusonthedatafromtheUnitedStates.
Thedataprovidedbythetoolcomesintheformofatwo-dimensionalarraywith
state,city,andhealth-human-serviceregiononthelocationaxisandtimeinseven-day
incrementsontheotheraxis. Figure11.5(a)showsfourtracesofrawdatafromAlaska
(black), California(red), Texas(green), andNewYork(blue). Allofthespatialloca-
tions’timeseriescan be visualized byaheat mapin(b) afternormalizing each time
tracebyitsownmeanandsettingthevariancetoone. Thisnormalizationhelpstoac-
countforlargerpopulationcenters;see[158]forasimilarnormalization. Figure11.5
illustratestheclearseasonalityoffluintheUnitedStates. Inthisexample,wetakedata
fromJune2007toJuly2014andfocussolelyonthestateinformationtovisualizethe
dynamicmodesasamapofthecontiguousUnitedStates.
TheoutputofDMDisillustrated inFigure11.5(c). Theeigenvaluestructurein-
dicatesanumberofmodesthatarewellwithintheunitcircle. Theseeigenvalueswill
quicklydecayandnotcontributetolongertime-scalebehavior. Themodeselection
plot suggests the data contains a yearly frequency. The mode and frequency from
DMDalignwiththestrikingseasonallyvaryingprofileinFigure11.5(d). Thephase
ofthedynamicmodeassociatedwiththisyearlyfrequencyisplottedinFigure11.5(e).
Thephaseisplottedbetween0and1,representingthetimeoftheyear. Thedynamic
modeplotted on themapshowsanumber ofinterestingfeatures. Onesuch feature
isthesmooth transitionofphase travelingnorth from CaliforniatoWashingtonon
thewestcoast. Thephaseinformationforthisyearlyseasonalfludynamicmodecan

11.4. Examples 183
(a) (c) Mode Selection (d) Discrete
8000 0.03 Eigenvalue
Spectrum
6000
0.02
4000 real(λ)
0.01
2000
0
1 0 944 1946 1948 1950 1952 1954 1956 1958 1960 1962 1964 1966 0 F 1 reque 2 ncy (1 3 /yr) im a1g(λ)
(b) Data Snapshots in Time Normalized
(e) Dynamic Mode 0.91
0.8
0.7
0.6
Cities Phase
0.5 (year)
.5 0.4
0.3
0.2
0.1
194419461948195019521954195619581960196219641966 0 0
selsaeM
noitaniccaV-erP
Raw Data
Figure11.6.AnillustrationshowingthedatafromprevaccinationmeaslesintheUnited
KingdomandtheoutputofDMD.(a)showstherawdataoffourcities’timeseries. (b)showsallof
thelocations;eachtimeserieshasbeennormalized. (c)showsthemodeselectionplot. (d)illustrates
thediscreteeigenvaluedistribution.(e)showsthephaseofeachelementofadynamicmodeassociated
withtheyearlyfrequency.ReprintedwithpermissionfromOxfordUniversityPress;figureadapted
from[224].
provideinsightforpublicservicecampaignsagainstfluandtimingofvaccinationcam-
paigns.
11.4.2 Prevaccination measles in the United Kingdom
DMDisnowappliedtodatadescribingcasesofmeaslesfromtheprevaccinationeraof
theUnitedKingdomovera22-yearperiod. Themeaslescasesarereportedeverytwo
weeksfrom60cities. Othertraditionaltime-seriesanalysismethods,liketheFourier
decomposition, have been previously applied tothisdataset [158]. Figure 11.6(a) il-
lustratesfourtimetracesoftherawdatafromfourcities,London(black),Liverpool
(red), Colchester (green), and Cardiff (blue). Similar tothefirst example, each loca-
tion’stimeseriesisnormalizedinmeanandvariance,allowingforvisualcomparison.
Thenormalizationallowsforplaceswithlargepopulations,likeLondon,tobecom-
paredtosmallertowns.
SimilartotheGoogleFludata,aclearseasonalitycanbeobservedinFigure11.6for
themeaslesdataset. AcontrastcanbeobservedintheUnitedKingdomdata,though,
wherethephaseoftheseasonaloscillationforeachcitycanbesubstantiallydifferent
thanforthefluexample. ApplyingDMD,wecandiscovertheseasonalmodeandfind
thephasedifferenceacrossdifferentcities. Figure11.6(d)showstheeigenvaluedistri-
bution. Thephaseofthedynamicmodeassociatedwiththeyearlycycle(computedat
≈0.98peryear)isillustratedinFigure11.6(e). GroupingsofcitiesnearLondonshare
similarphasewhereasanumberofcitiesinwesternUnitedKingdomaremorethan
fourmonthsoutofphase.

184 Chapter11. Epidemiology
11.5 The epidemiological interpretation of DMD modes
ThedynamicmodesdiscoveredbyDMDallowforanumberofinterestingandrele-
vantepidemiologicalinterpretationsofthelarge-scaledynamicpatternsofinfectious
disease spread. DMD can automatically identify the frequency content of the time
series. Inadditiontoidentifyingoscillations,theeigenvaluesoftheDMDoutputcan
also have adecay or growth component. Thedynamic modes associated withthese
eigenvalues can indicate the relative phase of oscillation by examining the angle of
eachelementinthedynamicmode,asshowninboththefluandmeaslesdataexam-
ples. Thephaseinformationalonecanbeusefulforallocatingvaccineresourcesforthe
year,sendingsurveillanceteamstomonitorthedisease,andtimingtheinterventions
toleveragenaturaldiseasedynamics.
The dynamic modes can also indicate the epidemiological connectedness of spa-
tial locations. Most disease monitoring is reported along political boundaries. The
dynamic modes can help connect politically defined areas into groupings of spatial
locations that are evolving with similar dynamics. Within each dynamic mode, the
magnitudeoftheelementprovidesameasureofthecontributionofthatlocationto
thatmode.Intheexamples,similarphaseinformationcanalsoindicatewell-connected
areas,suchastheMontana,Washington,Idaho,andWyominggroupingorthestates
inNewEnglandforflu. Itsimportanttonotethattheareasdonotnecessarilyneed
tobephysicallyconnectedtoeachothertobeepidemiologicallyconnected. Different
modesoftransportation,suchasairtravel,mightconnectareasthatareseparatedby
greatdistances,suchasLosAngelesandNewYorkCity.
Forinfectiousdiseaseslikepoliomyelitis,supplementaryimmunizationactivities
(SIAs) are conducted in portions of countries that are believed to still be endemic.
These SIAs are focused, short-term immunization campaigns. The dynamic modes
can help with campaign planning by identifying the epidemiologically linked areas
anddirectingresourcesaccordingtotheirdynamics. Further,surveillanceteamscan
be deployed according toexpected cases given the underlyingdynamics. Thishelps
minimizeredundantmeasurements. Thedynamicmodesandtheirrespectivefrequen-
ciesofferanumberofexcitingavenuesforhelpingwithongoingeradicationcampaigns
andthegeneralcontrolofthespreadofinfectiousdisease. Themethodologicalexten-
sionofDMDtoincludeinputs,describedinChapter6,canalsohelpwithplanning
eradicationcampaigns. DMDccandiscoverhowtheinputsdrivethesystem, which
couldsubstantiallybenefitinterventionefforts.

Chapter 12
Neuroscience
Thebrainisaremarkablycomplexorgan;amongotherfunctions,itenablesustoin-
terpret sensation, produce actions, experience emotions, retain memories, and form
decisions. Understandinghownetworksofbraincellscomputeandgiverisetothese
functionsisacentralchallengeinmodernbiology. Insightsintoneuralcomputation
have wide-reaching implications, from inspiring treatment of neurological disorders
tounderstandingoursenseofself. Withrecentadvancesintechnologyandinfrastruc-
ture,wecontinuetoincreaseourcapacitytorecordsignalsfrombraincellsinmuch
greaternumbersandatever-increasingtemporal resolutions. Accordingly,thestudy
ofbrain andneural systemsisundergoingaphasechange, from asciencelimitedby
ourabilitytoacquiredatatoasciencelimitedbyourabilitytounderstandcomplex
data.
Thebrainismadeupofanintricate,dynamicnetworkofcellsknownasneurons.
Theseneuronsaretremendouslyheterogeneousinshape,function,andconnectivity,
andtheirorganizationhasbeenthesubjectofsystematicstudysincethe1880s,with
the strikingly meticulous drawings of Santiago Ramón y Cajal, a few of which are
reproducedinFigure12.1. Neuronsproliferateinnumberandconnectionsduringde-
velopment,andthesenetworksremainplasticthroughoutlife;newcellsandconnec-
tionsarecontinuouslyaddedtothenetwork,andexistingconnectionsmaybepruned
andshapedbyexperience. Tothebestofourknowledge,thehuman brain contains
86×109neuronsandanapproximatelyequalnumberofnonneuronalcells[11]. Each
neuronmakesontheorderof103 connections,orsynapses,withotherneurons. The
network of connections between neurons, or more coarsely between brain areas, is
knownastheconnectome[265].
12.1 Experimental techniques to measure neural activity
Neurons maintain and actively manage an electrical potential between the inside of
thecellandtheoutsideextracellularfluidacrossitscellularmembrane. Theyencode
andprocess informationbyatransientflux ofionsacross thecell membrane, apro-
cessmediatedbyalargefamilyofproteinsembeddedwithinthecellmembraneacting
asgated ion channels. Inmost animalneurons, thision fluxculminates inan all-or-
nothingelectricaleventknownasanactionpotentialorspike. Thenumberandtim-
ingofthese action potentialsconstitutetheoutput ofaneuron, through which one
185

186 Chapter12. Neuroscience
Figure12.1.DrawingsofneuronsbyRamónyCajal.Ontheleftaredrawingsofvarious
typesofneurons,samplingthediversityofshapes,sizes,andarborizations. Ontherightisadrawing
oftheneuralcircuitryofthehippocampus,acashew-shapedbrainstructureassociatedwithmemory.
neuroncommunicateswithotherneurons,muscles, ororgans. Indeed,itisthrough
monitoringthision flux that weare able toobserve neural activityand infer neural
function.
Themostdetailedlevelofobservationofelectricalpotentialsrequiresmechanical
attachmentofafineglasspipetteontoaneuron. Thevoltageacrosstheneuron’scell
membraneismeasureddirectlythroughfillingthepipettewithaconductive,biocom-
patiblefluid. However,thisclassofintracellularorcell-attachedrecordingistechni-
callyverychallengingandprohibitivelydifficulttoscaletomorethanafewneurons.
Extracellularexperimentaltechnologiestomonitorneuralactivitycanbeelectri-
cal,optical,ormagneticinmechanism. Themostdirectformofobservingneuralac-
tivityiselectrical.Becausethefluxofionsacrossthecellmembraneinducesatransient
dipole, anyconductiveelectrodewithinreasonable proximityoftheneuronwillact
asanantennaandsensethedipoleasachangeinvoltage. Electrodesvaryinmaterial,
size, shape, andconfiguration. A finewireelectrodemay betensofmicrometers in
diameter,andwhenplacedwithinafewmicrometersofaneuron,itpicksupchanges
inelectricalpotentialfromtheneuron(aswellasfromanyotheractiveneuronsinrea-
sonableproximity). Signalsfromthesameelectrode,iffilteredbelowapproximately
300Hz, areknownasthelocal fieldpotential oftheregion; thesefield potentialsare
thoughttoreflectsomeaveragedactivityofalltheneuronswithinadiameterofhun-
dredsofmicrometers. Electrodesoflargediameterplacedundertheskullandontop
ofthebrain surface, inatechnique knownaselectrocorticography (ECoG), acquire
signalsaveragedfromneuronsoveralargerradiusstill.
Opticalmethodsofobservingneuralactivityalsomonitorchangesinvoltageacross
themembrane,eitherdirectlywithvoltage-sensitivedyesorindirectlywithfluorophores

12.2. Modaldecompositioninneuroscience 187
detectingtheinfluxofpositivelychargedcalciumionsacrossthecellmembrane,known
ascalciumimaging. Imagingthebrainhasmanyadvantages: itispossibletomonitor
many cells or brain areas simultaneously, and sometimes individual cells can be un-
ambiguously resolved. The trade-offs are (i) that the temporal resolution of optical
techniquestendstobeordersofmagnitudeslowerthanusingelectrodesand(ii)itis
difficult,butnotimpossible,toimagebrainareasatdifferentopticaldepths.
Theseinvasivetechniquesrequiresurgicalprocedurestoaccessthevertebratebrain
(see,however,aremarkableexceptioninthecaseofimagingalarvalzebrafishbrain[5]).
Evenso,wheninvasivestrategiesareeitherinfeasibleorundesirable,noninvasivemech-
anismstomonitorneural dynamicsincludeelectricalrecordingsandmagneticimag-
ing. Placingconductiveelectrodesonthesurfaceoftheskull,electroencephalography
(EEG)recordselectricalsignalsfromthebrain,albeitheavilyfilteredthroughthein-
terveningbone,cerebralspinalfluid,andduramater. EEGissimpletoperform,and
requiresnosurgery,butitsuffersfrompoorspatialspecificityandlargemeasurement
noise. Functionalmagneticresonanceimaging(fMRI)issimilarlynoninvasive;itmea-
suresspatiallylocalchangesinbloodoxygenationlevelsthroughdetectionofdifferen-
tialresponseofthehemoglobinproteintoamagneticfieldwhenboundorunbound
tooxygen. fMRIisperformedusingthesamemachineasusedinclinicalMRI,making
itrelativelyaccessibletoneuroscientists. Thetoolisparticularlyappealingbecauseof
itsabilitytoprobeintact,normallyfunctioninghumanbrains,includingpeeringinto
deepstructure. However,itstemporalresolutionislow,samplingevery1to2seconds,
andthepreciserelationshipbetweenbloodoxygenationlevelsandneuralactivityre-
mainsasubjectofactiveresearch.
Despite the differences in measurement techniques, studying neural activity de-
mandsanalysisofdatathatishighdimensional,complex, dynamic,andnoisy. This
chapteraddressesthepotentialtoanalyzeneuraldatausingDMD.
12.2 Modal decomposition in neuroscience
Dimensionalityreductionanddynamicalsystemstheoryhavebeenpowerfultoolsin
understandingthemeasuredactivityofpopulationsofneurons[74]. Despitetheoften
staggeringnumberofcellsinaneuronalnetwork,ithasbeenobservedthattheiractiv-
ityoftenevolvesonlow-dimensionalsubspacesandcanbedescribedbyrelativelyfew
distinctpatterns[39,311,185,67]. Itfollowsthatmethodstodiscoverthesecoherent
patterns,especiallyunsupervised methods, playapivotalroleinunderstandingsuch
complexdataandenableformulationofnewtheoriesofmind.
12.2.1 Staticmethods
As in almost every other field of science and engineering, PCA is the most widely
used modal decomposition algorithm toanalyze neural data. Examples wherePCA
andPCA-derivedtechniqueshasbeensuccessfullyappliedtoanalyzehigh-dimensional
neuralrecordingsincludeexperimentsininsects[192,232],fish[5],rodents[206,69,
127],nonhumanprimates[185,67],andhumans[62,278],tonameafew.
Beyond PCA, ICA is an alternative approach to dimensionality reduction that
looks for components of the high-dimensional data space that are maximally inde-
pendentfromeachother[22]. ICAisatechniquecommonlyusedinneuroscienceto
demixsignals,forinstanceinfMRIdata[55].Anothervariantofstaticdimensionality
reductionisnonnegativematrixfactorization(NNMF),amethodwhosecomponents
arerestrainedtohavenonnegativecoefficientstoallowinterpretability[172].

188 Chapter12. Neuroscience
60
50
40
30
20
10
0
0.1 0.2 0.3 0.4 0.5 0.6 0.7 0.8 0.9 1
Time (sec)
egatloV/sedortcelE
Figure12.2. Anexcerptofaone-secondwindowofECoGrecordingfrom59electrodes.
Thenormalizedvoltagetraceasobservedateachelectrodeisshownontheverticalaxis,whereelec-
trodechannelshavebeenstackedwithaverticaloffsetsotheymaybemoreeasilyvisualized.
12.2.2 Capturing dynamics
Time-series data has the additional feature that snapshots of data are acquired in se-
quenceintime,andmethodsthatleveragethistemporalrelationshipareoftenableto
capturelow-dimensionalstructureshiddenfrompurelystaticmethods. Onecommon
strategy todenoisetime-seriesdatainvolves temporal smoothing, followedby appli-
cation of PCA.Thisstrategy leadstointerpretation of high-dimensional time-series
dataastrajectoriesinlower-dimensionalprincipalcomponentspace, wheredifferent
experimentalconditionsmaybecomparedandinterpreted.
Another approach is to perform modal decomposition with an explicit dynami-
cal model. These methods typically make some assumptions about the form of the
dynamicsandthenoise,forinstance,x˙= f(x)+η,where f(x)maybelinearornon-
linear,andthenoiseηmaybeGaussianorstructured. Muchprogresshasbeenmade
in advancing these models, as well as their interpretability in the context of neural
recordings,andtheyincludelineardynamicalsystems(LDS,[263]),Gaussianprocess
factoranalysis(GPFA,[311]),andnonlineardynamicalsystems(NLDS,[310]). For
amorecomprehensivesynthesisofmethodsbroadlyrelatedtolineardimensionality
reduction,seeCunninghamandGhahramani[73].
12.3 DMD on neural recordings
HereweshowanexampleofDMDappliedtoneuralrecordings,expandingonideas
first described in Brunton et al. [44]. We start by analyzing a one-second window
ofneural activityrecorded byagridofelectrodesplaced atthehumanbrain surface
shown in Figure 12.2.13 Here the voltage measured at each electrode is shown as a
traceintime,wheredifferentelectrodechannelsareoffsetsothattheycanbevisual-
ized. Recordingsweresubsampledat500samples/sec,high-passfilteredat1Hz,and
normalizedtohaveunitvariance.
13ThedatausedhereiskindlysharedbyJeffreyOjemann.

12.3. DMDonneuralrecordings 189
Inthisexample, andtypicallyformanyneural recordingsonewouldliketoana-
lyze,thenumberofelectrodesisexceeded bythenumberofsnapshotsintime. Fol-
lowingChapter7,ourprescriptionforthisscenarioistoemploydelaycoordinatesby
stackingtime-shifted copies ofthe recordings, thusaugmenting therank ofthedata
matrix.
Thefollowingsectionofcodeloadsthiswindowofbrainrecordingandcomputes
itsDMD.
| ALGORITHM12.1. |         | DemonstrateDMDonneuralrecordings(DMD_ECoG.m). |         |                      |     |     |
| -------------- | ------- | --------------------------------------------- | ------- | -------------------- | --- | --- |
| load([’.’      | filesep | ’Data’                                        | filesep | ’ecog_window.mat’]); |     |     |
% parameters:
| r = 200;    | % number | of         | modes         |     |      |          |
| ----------- | -------- | ---------- | ------------- | --- | ---- | -------- |
| nstacks     | = 17;    | % number   | of stacks     |     |      |          |
| % construct | the      | augmented, | shift-stacked |     | data | matrices |
Xaug = [];
| for st | = 1:nstacks, |      |                                 |     |     |     |
| ------ | ------------ | ---- | ------------------------------- | --- | --- | --- |
| Xaug   | = [Xaug;     | X(:, | st:end-nstacks+st)];%#ok<AGROW> |     |     |     |
end;
| X = Xaug(:,  | 1:end-1);   |          |         |       |     |     |
| ------------ | ----------- | -------- | ------- | ----- | --- | --- |
| Y = Xaug(:,  | 2:end);     |          |         |       |     |     |
| % SVD and    | truncate    | to       | first r | modes |     |     |
| [U, S,       | V] = svd(X, | ’econ’); |         |       |     |     |
| U_r = U(:,   | 1:r);       |          |         |       |     |     |
| S_r = S(1:r, | 1:r);       |          |         |       |     |     |
| V_r = V(:,   | 1:r);       |          |         |       |     |     |
% DMD modes
| Atilde   | = U_r’*Y*V_r/S_r; |     |     |     |     |     |
| -------- | ----------------- | --- | --- | --- | --- | --- |
| [W_r, D] | = eig(Atilde);    |     |     |     |     |     |
Phi = Y*V_r/S_r*W_r;
% DMD eigenvalues
| lambda         | = diag(D);           |     |     |     |     |     |
| -------------- | -------------------- | --- | --- | --- | --- | --- |
| omega =        | log(lambda)/dt/2/pi; |     |     |     |     |     |
| 12.3.1 The DMD | spectrum             |     |     |     |     |     |
LetusstartbyexaminingtheDMDeigenvaluesλ. Thevisualizationoftheseeigenval-
uesisshowninFigure12.3. Notethatsincetherawdataisstrictlyrealvalued,these
eigenvaluesarenecessarilyeitherrealorcomeinconjugatepairs.
PlotDMDeigenvaluesofECoGrecordings(DMD_ECoG.m).
ALGORITHM12.2.
| figure(’Position’, |     | [100 | 100 600 | 300]); |     |     |
| ------------------ | --- | ---- | ------- | ------ | --- | --- |
subplot(1,2,1);
| plot(lambda,          | ’k.’); |      |              |                    |     |        |
| --------------------- | ------ | ---- | ------------ | ------------------ | --- | ------ |
| rectangle(’Position’, |        |      | [-1 -1       | 2 2], ’Curvature’, |     | 1, ... |
| ’EdgeColor’,          |        | ’k’, | ’LineStyle’, | ’--’);             |     |        |

| 190 |     |           |     |     |     |         | Chapter12. | Neuroscience |
| --- | --- | --------- | --- | --- | --- | ------- | ---------- | ------------ |
|     |     |           |     | λ   |     |         |            | ω            |
|     |     | 1 (cid:4) |     |     | 150 | (cid:4) |            |              |
100
0.5
50
|     |     | 0   |     |     |     | 0   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
-50
-0.5
-100
|     |     | -1  |        |     | -150 |     |       |        |
| --- | --- | --- | ------ | --- | ---- | --- | ----- | ------ |
|     |     | -1  | -0.5 0 | 0.5 | 1    | -8  | -6 -4 | -2 0 2 |
Figure12.3. DMDeigenvaluesoftheexcerptofECoGrecordingshowninFigure12.2.
Herewearevisualizingboththediscretetimeeigenvaluesλrelativetotheunitcircle(dashedlineon
leftpanel)andtheeigenvaluestransformedtocontinuoustimeasω=log(λ)/(2πΔt)(rightpanel).
|     | axis(1.2*[-1 |     | 1 -1 1]); |     |     |     |     |     |
| --- | ------------ | --- | --------- | --- | --- | --- | --- | --- |
axis square;
subplot(1,2,2);
|     | plot(omega, | ’k.’);      |         |              |      |              |     |        |
| --- | ----------- | ----------- | ------- | ------------ | ---- | ------------ | --- | ------ |
|     | line([0     | 0], 200*[-1 |         | 1], ’Color’, | ’k’, | ’LineStyle’, |     | ’--’); |
|     | axis([-8    | 2 -170      | +170]); |              |      |              |     |        |
axis square;
Themagnitudeofλ
relativetotheunitcircleindicatesthestabilityofthecorre-
i
spondingDMD spatial modeφ , wheremodeswhose eigenvalues lieexactlyon the
i
Thephaseofλ
unitcircleareneutrallystable. indicatestheoscillatoryfrequencyof
i
themode. Wemakeachangeofunitsbytakingthelogarithmofλandnormalizingby
Δt,ω=log(λ)/(2πΔt),sothatnowtheimaginarycomponentofω
isthefrequency
i
ofoscillationinunitsofcyclespersecond(Hz).
Onewaytomakeuseofω istoconnectthefrequenciesofoscillationcomputed
byDMDwiththepowerspectrumofthedata. ThisstrategyofanalyzingtheDMD
spectrumofthehigh-dimensionaldataleveragestheextensiveliteratureonfrequency
bandsofbrainoscillations,sothatwemayselectspatialfeaturesbasedonwell-defined
frequencyfeaturessuchasbetaandgammabandoscillations.
To visualize the DMD spectrum, we follow the scaling of each mode φ as de-
i
scribedinChapter8andplotthesemodeamplitudesagainsttheimaginarycomponent
ofω .
i
|     | ALGORITHM12.3. |     | Codetoplot | theDMDspectrumandcomparetothepower |     |     |     |     |
| --- | -------------- | --- | ---------- | ---------------------------------- | --- | --- | --- | --- |
spectrum(DMD_ECoG.m).
|     | % alternate | scaling      |     | of DMD modes |                |     |     |     |
| --- | ----------- | ------------ | --- | ------------ | -------------- | --- | --- | --- |
|     | Ahat =      | (S_r^(-1/2)) |     | * Atilde     | * (S_r^(1/2)); |     |     |     |

12.3. DMDonneuralrecordings 191
|     | [What,          | D] = eig(Ahat); |         |     |     |
| --- | --------------- | --------------- | ------- | --- | --- |
|     | W_r = S_r^(1/2) |                 | * What; |     |     |
Phi = Y*V_r/S_r*W_r;
f = abs(imag(omega));
P = (diag(Phi’*Phi));
% DMD spectrum
|     | figure(’Position’, |     | [100 | 100 600 | 300]); |
| --- | ------------------ | --- | ---- | ------- | ------ |
subplot(1,2,1);
|     | stem(f, | P, ’k’); |     |     |     |
| --- | ------- | -------- | --- | --- | --- |
|     | xlim([0 | 150]);   |     |     |     |
axis square;
|     | % power     | spectrum  |     |     |     |
| --- | ----------- | --------- | --- | --- | --- |
|     | timesteps   | = size(X, | 2); |     |     |
|     | srate =     | 1/dt;     |     |     |     |
|     | nelectrodes | = 59;     |     |     |     |
NFFT = 2^nextpow2(timesteps);
|     | f = srate/2*linspace(0, |     |     | 1, NFFT/2+1); |     |
| --- | ----------------------- | --- | --- | ------------- | --- |
subplot(1,2,2);
hold on;
|     | for c =   | 1:nelectrodes,             |             |        |     |
| --- | --------- | -------------------------- | ----------- | ------ | --- |
|     | fftp(c,:) | =                          | fft(X(c,:), | NFFT); |     |
|     | plot(f,   | 2*abs(fftp(c,1:NFFT/2+1)), |             |        | ... |
|     |           | ’Color’,                   | 0.6*[1      | 1 1]); |     |
end;
|     | plot(f, | 2*abs(mean(fftp(c,1:NFFT/2+1), |     |     | 1)), ... |
| --- | ------- | ------------------------------ | --- | --- | -------- |
|     | ’k’,    | ’LineWidth’,                   |     | 2); |          |
|     | xlim([0 | 150]);                         |     |     |          |
|     | ylim([0 | 400]);                         |     |     |          |
axis square;
Figure12.4showstheDMDmodeamplitudesandcomparesthemtotheFourier
transformofthesamedata. Thetwoarequalitativelysimilarandhavethesamerough
amplitudedecayasfrequencyincreases. Toreiteratethekeydifferences,DMDiscom-
puted as adecomposition of thefull high-dimensional time-series datain thisshort-
timewindow,whereastheFouriertransformiscomputedoneachelectrode’svoltage
trace separately. Moreover, the frequencies of DMD modes are not uniformly dis-
tributed,sothatifregularsamplingoffrequencyspaceisdesired,someconsolidation
ofmodesmaybenecessary.
| 12.3.2 | Interpretation | of  | modes | and | dynamics |
| ------ | -------------- | --- | ----- | --- | -------- |
OnekeyadvantageofDMDasameansofanalyzingneuralrecordingsisitsstraightfor-
wardinterpretation. DMDmodescorrespond tocorrelationsinspaceatfrequencies
dictatedbytheDMDeigenvalues. Tobeexplicit,wecanunpacktherepresentationof
thehigh-dimensional time-seriesdataaboveasillustratedinFigure12.5. Modemag-
nitudesarevisualized inelectrodecoordinatesonthebrain, alongwiththeirtempo-
ralevolution. NotethatherewehavenotshownthephasecomponentoftheDMD
modes,althoughthesecanlikewisebeinterpretedastherelativephasebetweenelec-

| 192 |             |     | Chapter12.  | Neuroscience |
| --- | ----------- | --- | ----------- | ------------ |
|     | DMDspectrum |     | FFTspectrum |              |
|     | 250         |     | 400         |              |
200
300
150
200
100
100
50
|     | 0             |         | 0             |         |
| --- | ------------- | ------- | ------------- | ------- |
|     | 0 50          | 100 150 | 0 50          | 100 150 |
|     | Frequency(Hz) |         | Frequency(Hz) |         |
Figure12.4.TheDMDspectrumqualitativelyresemblesthepowerspectrumascomputed
byFFT.NotethattheFFTspectrumiscomputedseparatelyforeachelectrode(graylines),andtheir
averageisshownastheboldblackline.
trodesateachfrequency.
The spatial patterns extracted as DMD modes with coherent dynamics at a par-
ticularfrequencybandarecomparable,butnotidentical,tospatialpatternsextracted
by band-pass filtering each channel of recording at the same frequency band. One
difference is that DMD eigenvalues are complex valued, so that the dynamics have
growth/decayinadditiontofrequencyofoscillation. Thisabilitytocapturegrowth/de-
cayofspatialpatternsisimportantwhenanalyzingnonstationarysignalsandtransient
behaviors,especiallyinthecontextofmrDMD(seeChapter5).

12.3. DMDonneuralrecordings 193
φ exp(ω t)
i i
×
time
+
×
≈
+
×
time
+
×
+ …
sedortcele
amplitude
(normalized
voltage)
Note: phase not visualized
Figure12.5. AnillustrationofDMDmodesinterpretedinthecontextofECoGrecord-
ings.Therawdata,shownhereasaheatmapofvoltageforeveryelectrodeovertime,isdecomposed
intoasumofDMDmodes,eachofwhichhasaspatialpartandatemporalevolutionpart. Thespa-
tialmodescanbereadilyinterpretedasrelativemagnitudesofcorrelationamongelectrodes. These
spatialmodesalsohavephasecomponentsthatarenotvisualizedinthisillustration,andthesecan
beinterpretedasrelativesynchronybetweenelectrodes.

Chapter 13
Financial Trading
Investmentstrategieshavelongbeenthecornerstoneofthefinancialindustry. Indeed,
theeconomichealthofindustrialsectorsandnationsisoftengaugedbytheirperfor-
manceinvarious global stock market tradingcenters (e.g., theNewYork Stock Ex-
change). Thevolatilityofstockportfoliosisespeciallyinterestinginfinancialtrading
ashighvolatility,orstrongvarianceinstockpricesovertime,isthebasisforformulat-
ingbuy-sideand/orsell-sidestrategies. Specifically,formulatingaprincipledstrategy
forshortingastock(selling)orgoinglongwithastock(buying)iscriticalforsuccess-
fullycapitalizingonmarkettrendsandgeneratingstrongreturnoninvestments.
The past few decades have seen a revolution in how and when financial trading
strategiesareimplemented. Thisrevolution wasgenerated by thecomputer-enabled
riseofalgorithmictradingschemes. Asof2006,onethirdofallEuropeanUnionand
UnitedStatesstocktradeswereestimatedtobeexecutedfromacomputertradingalgo-
rithm[139,281]. TheLondonStockExchangetradingduringthistimewasestimated
to be 40% driven by algorithmic trading. Since 2006, and thus only over the past
decade, thefinancial industry hasseen the adventand dominance ofhigh-frequency
trading schemes. High-frequency trading attempts to take advantage of stock price
fluctuationsthatoccurontimescalesthatareasfastasmicroseconds. In2009,high-
frequencytradeswereestimatedtoaccounted for60–73%ofallUnitedStatesequity
trading volume [139, 281]. These high-frequency trading methods can only be exe-
cutedbycomputer,leadingtoafurtherconfluenceofautomatedtradersandinnova-
tionsinmathematicalalgorithms.
13.1 Financial investment and algorithmic trading
Algorithmictradingisdrivenbymathematicalmodels,statisticalestimation,andmod-
ern data-driven (predictive) analytics, which seek to capitalize on stock market pat-
terns, either real or perceived, to inform automated buy/sell/hold investment deci-
sions. Asonemightexpect, theunderlyingmathematicaltoolsused foralgorithmic
tradingcapitalizeonavarietyofstatisticalandprobabilisticcomputationaltoolsfor
processingthetimeseriesoffinancialdatastreams. Mostofthesemathematicaltools
arealsousedtogenerateriskassessmentsandconfidenceintervalsforagivenstrategy;
i.e., in additiontoatradingdecision, aprediction of volatilityisoften generated by
theunderlyingstatisticalmodelused.
195

196 Chapter13. FinancialTrading
Thus, atitscore, theultimategoal ofalgorithmictradingistotakeadvantageof
the speed and precision of computer-executed trading strategies that are based on a
principled, underlying mathematical or statistical structure in financial data. In the
high-frequency setting, the computer can evaluate and execute trades on time scales
thatareimpossibleforhumantraderstoachieve. Avastnumberofmathematicaland
statisticalstrategieshavebeensuggestedandimplementedindifferentmarketsandfor
avarietyoffinancialinstruments. Manyofthesearereviewedinstandardtextbooks
onfinanceandtrading[109,3],withriskassessmentsofsuchstrategiesacriticalfactor
intheirultimateviability[72,276]. Afewofthemostcommontradingmodelstake
advantageoftime-seriesanalysis[38,65,268],trendfollowing[83,126,259],technical
indicators [66,258], pairs trading[90], mean reversion [179,75, 10], Markovmod-
els [144, 99], Bayesian inference [8, 241], news and announcements [305, 312], and
potentiallycombinations of these methods [88,34, 256]. For instance, in trend fol-
lowing,thetradingstrategyfollowsthetrendsinmovingaverages,channelbreakouts,
price-levelmovements,andotherrelatedfinancialindicators[83,126,259]. Theseare
perhapsthesimpleststrategiestoimplementthroughalgorithmictrading,sincethey
donotinvolvepriceforecasting.Tradesaresimplyexecutedbasedontheoccurrenceof
desirabletrends. Incontrast,inanalgorithmlikepairstrading,thestrategymonitors
performanceoftwohistoricallycorrelated securities[90]. Whenthecorrelation be-
tweenthetwosecuritiestemporarilyweakens,i.e.,onestockmovesupwhiletheother
movesdown,thepairstradewouldbetoshorttheoutperformingstockandtolong
theunderperformingone,bettingthatthespreadbetweenthetwowouldeventually
converge. Thedivergencewithinapaircanbecausedbytemporarysupply/demand
changes,largebuy/sellordersforonesecurity,reactiontoimportantnewsaboutone
of the companies, and many other causes. Of course, this is only a small sampling
ofmethodsandreferences, andweencouragethereadertoconsulttextsonfinancial
tradingforabroaderviewpointandadditionalreferences[109,3,72,276].
Commontoallthetradingstrategiesistheuseoffinancialtime-seriesdatatomake
principleddecisionsaboutinvestment.Thestrategiesrangefromsimpleassessmentsof
thedatatosophisticatedstatisticalanalysisofdatastreams. Ineachcase,aphilosophi-
calviewpointistakenaboutthemeaningandinterpretationofthedata. Inaccordance
withthisobservation,theviewpointadvocatedbyMannandKutz[189]assumesthe
stockmarket tobeacomplex, dynamical systemthatexhibitsnonstationary, multi-
scalephenomena. Asisadvocated here,such aviewpointishighlyappropriate fora
methodlikeDMDand/ormanyofitsvariants,suchasmrDMD.Mostimportant,the
DMDmethoddoesnotenforceorprescribeanunderlyingdynamicalmodel. Rather,
theequation-freenatureofthemethodallowsthedynamicstobereconstructeddirectly
fromthedatasampledoveraspecifiedwindowoftime.Specifically,DMDdecomposes
stockportfoliodataintolow-rankfeaturesthatbehavewithaprescribedtemporaldy-
namics. Intheprocess,theleast-squarefitlineardynamicalsystemallowsonetopre-
dictshort-timefuturestatesofthesystem. Theseshort-timepredictionscanbeused
toformulate successful tradingstrategies byidentifyingtransient, evanescent signals
inthefinancialdata[189]. Themethodisadaptive,updatingitsdecompositionasthe
marketchangesintime.Itcanalsoimplementalearning(machinelearning)algorithm
totrackoptimalsamplingandpredictionwindows,asthesechangemuchmoreslowly
intimeandindifferentmarketsectors. Themethodisappliedanddemonstratedon
severalmarkets(e.g.,technology,biotech,transport,banks). Asoutlinedintheintro-
duction,DMDcanalsobeusedasadiagnostictool,allowingforaprincipledtechnique
capableofdata-drivendiscoveryofcyclicspatiotemporal featuresinagivendataset.
Indeed,theDMD method hasrecentlybeen used by Hua etal.[137]toextract and

13.2. Financialtime-seriesdataandDMD 197
analyzerobusteconomiccyclesinstockmarkettime-seriesdata.Theiralgorithmcon-
sidersaninnovativeapproachtoseparatingtime-seriesdataintorobustandnonrobust
featurestoobservepersistentcyclicactivity.
WedemonstratetheuseofDMDforafinancialtradingstrategy[189]. Wespecif-
ically consider taking advantage of the growth and decay behavior of the decompo-
sitionas thecriticalfeatures, notnecessarily thecyclicbehavior reported by Hua et
al.[137]. TheDMDalgorithmalsoallowsonetoadapt thefrequency andduration
(samplingwindow)ofthemarketdatacollection tosiftoutinformationatdifferent
timescales,makingdifferenttradingstrategies(e.g.,highfrequencytrading,dailytrad-
ing,long-termtrading,etc.) possible. Indeed,onecanuseaniterativerefinementpro-
cesstooptimizethesnapshotsamplingwindowforpredictingthefuturemarket. A
criticalinnovationofDMDisitsabilitytohandletransientphenomenaandnonsta-
tionarydata,whicharetypicallyweaknessesofSVD-basedtechniques. Onecanalso
builduponrecentinnovationsinmrDMDtominefordatafeaturesatdifferenttime
scales[167].
13.2 Financial time-series data and DMD
Asidefrom small, open-source exemplar datasets, financial dataisrarelyfree. Well-
curatedandscrubbeddataisparticularlyvaluableanddifficulttoobtainwithoutpay-
ingafee. Withthisinmind,wedemonstratetheDMDalgorithmonareadilyavailable
data source provided by Yahoo! web services. Specifically, we consider daily stock
price quotes. For intraday trading or high-frequency data streams, other sources of
data should be considered. Regardless, the efficacy of the DMD algorithm can be
demonstratedondailystockquotes.
MATLAB allows for pulling daily stock quotes directly from Yahoo! using the
data feed toolbox. Thus, the data can be imported to the MATLAB framework for
processingandevaluation. Thefollowingcodedemonstrateshowthisisdoneinprac-
tice.
ALGORITHM13.1. Yahoodatafeed.
c = yahoo;
d = fetch(c,’IBM’);
This pulls stock data information for the technological giant IBM. Specifically, the
retrieveddatainthestructuredisasfollows.
ALGORITHM13.2. Yahoodataoptions.
d =
Symbol: {’IBM’}
Last: 173.84
Date: 735529.00
Time: 0.42
Change: 0.98
Open: 173.23
High: 173.84
Low: 172.95
Volume: 1132526.00

| 198 |     |     |     | Chapter13. | FinancialTrading |
| --- | --- | --- | --- | ---------- | ---------------- |
Thisthenallowsonetoacquireimportantinformationpertainingto,forinstance,the
currentdateandtimealongwiththedailyhighandlow.Onecanalsopullthecurrent
valueofthestockwiththefetchcommand.
| ALGORITHM13.3. |     | Currentstockprice. |     |     |     |
| -------------- | --- | ------------------ | --- | --- | --- |
d = fetch(c,’IBM’,now)
d =
| 735528.0 | 174.42 | 174.75 | 172.63 172.86 7079500.0 | 172.86 |     |
| -------- | ------ | ------ | ----------------------- | ------ | --- |
Thisversionoffetchreturnsthedate,openprice,highprice,lowprice,closingprice,
volume, and adjusted closing price. For our purposes, wewould like to extract the
closingpriceforaseriesofstocksoveraprescribed timeperiod. Topulldataovera
rangeoftimes,thefollowingcanbeused.
| ALGORITHM13.4. |     | Stockpricehistory.                           |     |     |     |
| -------------- | --- | -------------------------------------------- | --- | --- | --- |
| ClosePrice     | =   | fetch(c,’IBM’,’Close’,’08/01/99’,’08/25/99’) |     |     |     |
ClosePrice =
|     | 730357.00 |     | 122.37 |     |     |
| --- | --------- | --- | ------ | --- | --- |
|     | 730356.00 |     | 122.00 |     |     |
|     | 730355.00 |     | 124.44 |     |     |
|     | 730352.00 |     | 121.75 |     |     |
|     | 730351.00 |     | 122.94 |     |     |
...
Thisgives the closing priceover aperiod specified by theuser. Onecould also pull
openingpricesorhighsandlows. Inwhatfollows,wewillspecifyanumberofstocks
traded over aprescribed period of time. The followinggives the form of command
usedforpullingourdatafromYahoo!.
| ALGORITHM13.5. |        | Yahoodailystockdata. |                |     |     |
| -------------- | ------ | -------------------- | -------------- | --- | --- |
| tickers=       | {’JPM’ | ’BOA’                | ’AMZN’ ’CVX’}; |     |     |
| date_1         | = ’Jun | 1 06’;               |                |     |     |
| date_2         | = ’May | 10 13’;              |                |     |     |
for j = 1:length(tickers);
|     | Price.(tickers{j})= |         | fetch(yahoo,tickers(j),’Adj |     | Close’, |
| --- | ------------------- | ------- | --------------------------- | --- | ------- |
|     | date_1,             | date_2, | ’d’);                       |     |         |
Temp = Price.(tickers{j});
|     | ClosePrice(:,j) | =   | Temp(:,2); |     |     |
| --- | --------------- | --- | ---------- | --- | --- |
end
| Close_Price | =   | flipud(ClosePrice); |     |     |     |
| ----------- | --- | ------------------- | --- | --- | --- |
Importantly,oneonlyneedspecifythestocktickersymbolasusedbytheNewYork
StockExchangeorNASDAQ,alongwiththestartandenddatesrequiredbythedata

13.2. Financialtime-seriesdataandDMD 199
pull. Thestocktickersymbolisthesimpleidentifierforallpubliclytradedcompanies.
Forinstance,inthebankingsector,‘JPM’and‘BOA’areJ.P.MorganBankandBank
of America, respectively. In the retail sector, ‘AMZN’ and ‘CVX’ are Amazon and
CVXpharmacies,respectively. Startandendpricesaregivenformonth(abbreviated),
day, and year(last twodigits). Inthealgorithm presented, thedailyclosingpriceof
thestockisextracted. Theopeningpricecanalsobeacquiredifdesired.
Once the daily stock prices have been collected, the data can be arranged into a
datamatrixforprocessing. Specifically,thefollowingdatamatrixisconstructed:
|     | ⎡   |     | ⎤   |
| --- | --- | --- | --- |
.
.
|     | ⎢ ··· | .            | ··· ⎥        |
| --- | ----- | ------------ | ------------ |
|     | ⎢ ··· | ‘JPM’        | ··· ⎥        |
|     | ⎢     |              | ⎥            |
|     | ⎢ · · | ·            | · · · ⎥      |
|     | X= ⎢  | ‘B O A ’     | ⎥ ↓companies |
|     | ⎢     |              | ⎥            |
|     | ⎢ · · | · ‘A M Z N ’ | · · · ⎥      |
|     | ⎢     |              | ⎥            |
|     | ···   |              | ···          |
|     | ⎣     | ‘CVX’        | ⎦            |
.
|     | ··· | . . | ··· |
| --- | --- | --- | --- |
−→
dailystockprices
wherethedailystockpricesequencesarearrangedchronologicallyfromthefirstday
tothelastdaypulledinthedataextraction. Notethatthetimedifferentialbetween
thecolumnsisimportantintheDMDprocess. Withaprescribeddifferentialofone
day (for daily stock data), the algorithm is easy to execute given the equally spaced
sampling.
The DMD method provides a decomposition of the collected data into a set of
dynamicmodesthatarederivedfromstockmarketsnapshotsoveragiventimeperiod.
AsshowninthedatamatrixX,thedatacollectionprocessinvolvestwoparameters:
n=numberofcompaniesinagivenportfolio,
m=numberofdatasnapshotstaken.
Withthisdatamatrix, wecan evaluate portfolios ofholdings and different financial
sectors,andwecandeterminehowtobestuseportionsoftheoveralldatamatrixX.
NotethatthedatamatrixX∈(cid:2)n×m isasdefinedfortheDMDalgorithmin(1.16).
The goal of a DMD-based trading algorithm is to capitalize on the predictions
(1.24)oftheDMDtheory. Thetradingalgorithmdevelopedisparameterizedbytwo
key(integer)parameters:
=numberofpastdaysofmarketsnapshotdatataken,
m
p
=numberofdaysinthefuturepredicted.
m
f
Specifically,wewillrefertotheDMDprediction(1.24)withthenotation
|     |     | (m  | )         |
| --- | --- | --- | --------- |
|     |     | x   | ,m (13.1) |
|     |     | DMD | p f       |
toindicatethepastm numberofdaysthatareusedtopredictm daysinthefuture.
p f
Thisallowsustospecifyboththemarketsamplingwindowandhowfarintothefuture
(m )usesonlyportionsof
| wearepredicting. | NotethattheDMDpredictionx |     | ,m  |
| ---------------- | ------------------------- | --- | --- |
DMD p f
thefulldatamatrixXasspecifiedbytheparameterset(m ,m ). Ourobjectiveisto
p f
usehistoricaldatatodeterminesuitablecombinationsof(m ,m )thatgivethebest
p f

200 Chapter13. FinancialTrading
predictivevalue. Inparticular,welookforwhatwetermtradinghotspots,orregions
of(m ,m )wherethepredictionsareoptimal. Amoreprecisedefinitionofatrading
p f
hotspotwillbegiveninwhatfollows.
13.3 Trading algorithms and training
The training algorithm is essentially an optimization routine over the space of pa-
rameters (m ,m ). In particular, our objective is to see which DMD predictions
p f
x (m ,m )havethehighestrateofsuccessinpredictingthefuturepositionofthe
DMD p f
market, or portfolio of holdings. Thetraining portion of the algorithm thus looks
over a historic time period, whether that is 100 days or 10 years, to determine the
bestchoicesof(m ,m ). Thisisanoff-lineprocedurerunonacollectionofhistorical
p f
data. By learning the best (m ,m ), it may be possible toexecute trading in an on-
p f
linefashionsincethispotentiallyexpensiveoptimizationprocedurehasalreadybeen
performed.
We consider all possible combinations of (m ,m ) and their associated success
p f
rates for predictingthe correct future state, whetherthe stock values have increased
or decreased. Since we are using historical data, we can compare the DMD predic-
tion with known market activity. Specifically, we evaluate whether DMD predicts
that the market increases or decreases, and we compare that to the known market
activity. We set limits that were found to be suitable for the DMD algorithm, let-
ting m =1,2,...,25daysandallowing m =1,2,...,10days. Aswillbeshownin
p f
theresults,theseappeartobereasonableandeffectivevaluesfordeterminingthebest
combinationsof(m ,m ).
p f
Whenwelookedatthetrainingalgorithmoverthelast10years,wecouldseecon-
sistent trading hot spots across sectors. Most hot spots would look at the last 8 to
10 days of prices to make the best prediction of the price in 4 to5 days. Hot spots
thathadsuccessratesgreaterthan50%werepromisingbecausetheywouldbestatis-
tically likely to make money over time. The information gathered about hot spots
allowedustocreateatradingalgorithmthatwouldenterstockmarketpositionsusing
resultsfromDMDanalysiseachdayandthesolution(13.1). Inpractice,theoptimal
valuesof(m ,m )weredeterminedfromatwo-yearperiodoftrading(July2005to
p f
July2007). ThistrainingperiodthenallowedustofindtheoptimalDMDprediction
x (m ,m )forexecutingtrades. Thus,thetrainingdataisseparatefromthetestset;
DMD p f
i.e.,thetestsetisfromJuly2007onwards. Notethatinadditiontodeterminingsuc-
cessfulpredictionwindows,anassessmentofthenetpositiveornegativegainisalso
noted. Providedthereissufficientpredictedchangeinthestock(atleast1%),thena
tradeisexecuted. Itiscriticaltooffsetthecostofthetransactionfeetomakemoney.
Intheresultsthatfollow, threebasicassumptionsaremade: (i)theinitialinvest-
ment capital is$1 million, (ii) transaction costs are $8 for each position, and (iii) all
moneyisinvestedevenlyacrossallcompaniesinagivenportfolio. Assuch,themethod
used ischaracterized asaself-financing strategy asthere isnoexogenous infusion or
withdrawalofmoney;thepurchaseofanewassetmustbefinancedbythesaleofanold
one. Wehadtheflexibilitytouseanycompany,providingithadbeenpubliclytrading
forthetimeframewewereusing,andwewereabletocombineasmanycompaniesas
wewished. Forillustrativepurposes,wetendedtouse10companiesasaproxy,orrep-
resentation,ofeachsectorconsidered. Theinitialdailytradingalgorithmtookgiven
inputs(m ,m )forthesamplingwindowandpredictionwindowandrantheDMD
p f

13.3. Tradingalgorithmsandtraining 201
analysiseachday. Specifically,tradingwasperformedusingtheDMDhotspotpredic-
tionwindowsandcapital wasdividedequallyamongallcompaniesintheportfolio.
Afterweentered theposition foragiven duration, wecalculated howmuch money
wouldhavebeenmadeorlostbyusinghistoricaldata. Wealsoreinvestedgainsover
theduration of the trade period. Afterthe algorithm had completed, we compared
ourresultstobuying thebenchmark, S&P 500,andalso compared it tobuying and
holding the individual stocks. Note that effects of slippage, for instance, have been
ignoredinthetradingscheme. However,the$8pertradeisaconservative(high)es-
timate of trading costs that should offset such effects. More precisely, it should be
notedthatthetradingfeeof$8isselectedfromthebasefeeofacompanylikeE-trade,
which charges $7.99 per trade. Thus, one would not expect topay anything higher
thanthisrate. However,Barron’sAnnualBestOnlineBrokerssurvey[136]evaluatesa
numberofbrokersforvariouscharacteristics,includingthetransactionfeepertrade.
Thisnumbercanbehighlyvariabledependingonthesizeofbrokerageandstocksbe-
ingtraded. Forinstance,InteractiveBrokerschargesanominalfeeofaslowas$1per
trade. SuchrateswereeffectiveasofNovember4,2015.Manyofthefirmslistedinthe
rankingtypicallyhadadditionalfees,andsomefirmsreducedorwaivedcommissions
orfees,dependingonaccountactivityortotalaccountvalue. Thus,settingaprecise
costfortradingisdifficult.
The second trading algorithm we created did not use any information that one
wouldn’thaveifonewantedtotradetoday;henceitwasasrealisticaspossible. The
algorithmwouldstarttradingatday101becauseitwouldcontinuouslyusetheprevi-
ous100daystofindtheoptimaltradinginputsfromthetrainingalgorithm. Therefore,
thetrainingalgorithmwouldbeusedonasliding100-daywindowpriortothedaythe
tradingalgorithm wasexecuted. Itwould update itsresults dailyusing theprevious
100 days. Throughout our research we found that most sectors had obvious, even
prominent,hotspots. However,somesectorsdidn’thaveanyclearhotspot,andthey
tendedtobethesectorsthatunderperformedinthetradingalgorithm.
Withthisinmind,wecreatedathirdtradingalgorithmthatlookedintowhether
the inputs with the maximum success rate were within a larger hot spot region or
isolatedinstancesandlikelytohaveperformedwelloverthelast100daysduetoran-
domness. Todothis,thetradingalgorithmfoundoutwhatinputshadthemaximum
successrateoverthelast100days,andthenitlookedatthesurroundinginputstosee
ifthemeansuccessrateofallnineneighboring(m ,m )wereaboveathreshold. The
p f
100-daywindowwaschosenempirically.Ourobjectivewastoconstructatestwindow
thatwassufficientlylongtocapturetherecenttrends,butnottoolongtobeweighted
bydatalongintothepast. Thus,averylongsamplingwindowmadethemethodex-
tremelyslowtoadaptduetotheneedtorespectthedistantpastofthefinancialtime
series,whereasashortsamplingwindowmadetheadaptabilityveryvolatile. Given
ourtypical(8,5)tradingwindow,the100-daywindownicelybalancedhistoricaldata
withadaptability. Ifahotspotregionwasfound,thenitwouldbeclassifiedasahot
spotandatradewouldbeexecuted. Otherwise,thetradingalgorithmwouldholdthe
moneyuntilahotspotappearedatalaterdate. Whenimplementingthisstrategy,we
usedahotspotthresholdof53%sothatwecouldbeconfidentthattheretrulywasa
hotspot. Thisisperhapsthemostrobustofthetradingstrategies,aswedemonstrated
thatmarketswithhotspotregionswerequiteamenabletotheDMDstrategy. Indeed,
all market sectors showinga stronghot spot generated significant capital gains with
thetradingalgorithm.
Insummary,threealgorithmsbasedonDMDcanbeeasilydeveloped:

202 Chapter13. FinancialTrading
(i)AlgorithmI:Wetrainonhistoricalfinancialdataoveratwo-yearperiod(June2005
toJune2007)andthentradeonthebestdiscovered(m ,m )samplingandprediction
p f
windowfromJune2007onwards. Thus, thereisatwo-yeartrainingperiod, andno
out-of-sampledataisusedtodeterminetheoptimalwindow.Wenotethatundercross-
validationanalysis, theoptimalsamplingandpredictionwindow(m ,m )isrobust
p f
tochangesinthetwo-yeartrainingperiod.
(ii)AlgorithmII:Weusetheprevious100-daywindowtofindthebest(m ,m )sam-
p f
plingand prediction window. The windowisadaptively updated with theprevious
100daysandwealwaystradebasedonthebestprediction. Wenotethatundercross-
validationanalysis,theoptimalsamplingandpredictionwindow(m ,m )isrobustto
p f
changesinthe100-daytrainingperiod. However,shortersamplingperiodscaninduce
strongvariabilityintheresultsandshouldbeavoided,whilelongerperiodsleadtothe
resultsshowninAlgorithmI.
(iii)AlgorithmIII:ThisisthesameasAlgorithmIIexceptthatweonlytradeifahot
spot(13.2)(seebelow)isfound.
Inwhatfollows,onlythefirstalgorithmisdemonstratedondata. Fordetailsre-
gardingtheotherstrategies,seeMannandKutz[189].
13.3.1 Trading hot spots
Ingeneral,oneisinterestedinthehighestprobabilityofpredictionsuccesspossible.
In practice, for financial trading, it is difficult to achieve performance success much
above50%duetothevolatilefluctuationsinthemarket. Thusfarwehavebeenusing
the term hot spot loosely. Here, we more precisely define the concept. Numerical
simulationsontrainingdatashowthattradingsuccesswithDMDdependsnotjuston
thebest probability ofprediction, but rather on havingaclusterof (m ,m )values
p f
wherestrongpredictivepowerisachieved[189].
Moreprecisely,wedefineahotspotasaparticularpairingoftheintegers(m ,m )
p f
suchthat(i)thepredictionaccuracyisabove53%atthatlocationand(ii)theaverage
predictionscoreofthislocation anditseightneighboringcellsaverages aprediction
valueof53%orabove. Denotingthesuccessrateatthelocation(m ,m )asS ,
p f m ,m
p f
wehavethehotspotconditions
1
(cid:7)1 (cid:7)1
(i) S >0.53, (ii) S >0.53. (13.2)
m p ,m f 9 m p +k,m f +j
j=−1k=−1
Thevalue of 0.53 is chosen from empirical observations of thepredictive success of
theDMDalgorithm. Inwhatfollows,wefocusontwokeysteps: (i)atrainingstep
inthealgorithmtodetermine(m ,m )and(ii)implementationoftradingbasedon
p f
theresults. Ifthereexistsatradinghotspotwiththeabovedefinition,thentheDMD
algorithmprovidesahighlyeffectivemethodforalgorithmtrading.
13.3.2 Trading hot spots by sector
BeforeproceedingtoevaluatetheperformanceoftheDMDalgorithmforalgorithm
trading,weconsidervariousfinancialsectorsandtheirpotentialforproducingahot

13.3. Tradingalgorithmsandtraining 203
m
f
m
p
Figure13.1. Sectorsthathaveahotspotwheretheprobabilityofsuccessattheoptimal
tradingpositionfor(m ,m )isabove53%alongwithitssurroundingeightcells. Thus,thedefini-
p f
tion(13.2)issatisfiedinthetransport,homeconstruction,andretailsectors. Notethatthecolorin
eachcelldenotestheprobabilityofsuccess.
m
f
m
p
Figure13.2.Sectorsthatdonothaveahotspot. Althoughindividualcellsmaybeabove
53%inpredictiveaccuracy,thesesectorsfailtohavethesurroundingeightcellsabovethethresholdin
(13.2).Thesesectorsincludedefense,healthcare,andbiotech.Notethatthecolorineachcelldenotes
theprobabilityofsuccess.
spot. Sixexamplesareconsideredintotal. Inthetransport,homeconstruction,and
retailsectors,atradinghotspotasdefinedaboveisproduced. Incontrast,thesectors
ofdefense,healthcare,andbiotechfailtoproduceahotspotasdefined. Whenahot
spotisproduced,DMDproducesaviableandeffectivetradingscheme. Whennohot
spotispresent,DMDfailstoproduceresultsthatareanybetterthansimplyinvesting
intheS&P500andholding. Thus,thedefinitionofatradinghotspotservesapractical
purposeindefiningwhentheDMDtradingalgorithmmightwork.
Figures13.1and 13.2showthesuccessrates fortheDMDalgorithm whencom-
pared tothe financial market fluctuations. Theseresults are computed on historical
datatofindthebesttradingwindows(m ,m )thatmaximizethesuccessrate. Inthe
p f
sectorswhereahotspotasdefinedin(13.2)isfound,thetradingperformancewillbe
demonstratedtobesuccessful. Ifahotspotasdefinedby(13.2)failstoexist,thenthe
DMDalgorithmstatisticallydoesnobetterthaninvestingandholdingintheS&P500.
Inthetransport,homeconstruction,andretailsectorsofFigure13.1,clearhotspots
arefound,with(m ,m )pairingsof(8,4),(11,5),and(8,5),respectively. Thedefense,
p f
healthcare,andbiotechsectorshavenohotspots. Notethatforeachsectorweselect
asmall,representativesetofcompaniestoillustratethatsector’sperformance.

| 204 |     |                       |     |     |     | Chapter13. |     | FinancialTrading |
| --- | --- | --------------------- | --- | --- | --- | ---------- | --- | ---------------- |
|     |     | (cid:6)(cid:5)(cid:5) |     |     |     |            | ψ   | (x)              |
(cid:5)(cid:1)(cid:9)
|     | j   | (cid:6)(cid:5) |     |     |     |     |     | 1   |
| --- | --- | -------------- | --- | --- | --- | --- | --- | --- |
σ
|     | (cid:2) | (cid:6)               |     |     | (cid:2)(cid:5)(cid:1)(cid:9) |     |     |     |
| --- | ------- | --------------------- | --- | --- | ---------------------------- | --- | --- | --- |
|     | /       | (cid:5)(cid:1)(cid:6) |     |     |                              |     |     |     |
ψ (x)
|     | σ k |                              |     |     | (cid:5)(cid:1)(cid:9) |     |     |     |
| --- | --- | ---------------------------- | --- | --- | --------------------- | --- | --- | --- |
|     |     | (cid:5)(cid:1)(cid:5)(cid:6) |     |     |                       |     |     | 2   |
(cid:6)(cid:8)
|     |     | (cid:5) (cid:7) | (cid:8) (cid:10) (cid:11) (cid:6)(cid:5) (cid:6)(cid:7) | (cid:6)(cid:10) | (cid:2)(cid:5)(cid:1)(cid:9) |     |     |     |
| --- | --- | --------------- | ------------------------------------------------------- | --------------- | ---------------------------- | --- | --- | --- |
k
|     |     |     | ℑ{ω } (cid:8) |     |                       |     |     |     |
| --- | --- | --- | ------------- | --- | --------------------- | --- | --- | --- |
|     |     |     | k             |     | (cid:5)(cid:1)(cid:9) |     | ψ   | (x) |
3
(cid:7)
(cid:2)(cid:5)(cid:1)(cid:9)
|     |     | (cid:2)(cid:7) | (cid:2)(cid:6) (cid:5) | (cid:6) | (cid:7)                 |     | ψ   | (x) |
| --- | --- | -------------- | ---------------------- | ------- | ----------------------- | --- | --- | --- |
|     |     |                |                        | ℜ{ω     | } (cid:5)(cid:1)(cid:9) |     |     | 4   |
|     |     |                | (cid:2)(cid:7)         | k       |                         |     |     |     |
(cid:2)(cid:5)(cid:1)(cid:9)
(cid:2)(cid:8)
|     |     |                        |     |     | (cid:5)                | (cid:9) |     | (cid:6)(cid:5) x (cid:6)(cid:9) |
| --- | --- | ---------------------- | --- | --- | ---------------------- | ------- | --- | ------------------------------- |
|     |     | (cid:5)(cid:1)(cid:10) |     |     | (cid:5)(cid:1)(cid:10) |         |     |                                 |
(cid:5)(cid:1)(cid:8)
(cid:5)(cid:1)(cid:8)
|     |     | (cid:5)(cid:1)(cid:7)        |          |     | (cid:5)(cid:1)(cid:7)        |     |          |     |
| --- | --- | ---------------------------- | -------- | --- | ---------------------------- | --- | -------- | --- |
|     |     | (cid:5)                      |          |     | (cid:5)                      |     |          |     |
|     |     | (cid:2)(cid:5)(cid:1)(cid:7) |          |     | (cid:2)(cid:5)(cid:1)(cid:7) |     |          |     |
|     |     | (cid:2)(cid:5)(cid:1)(cid:8) | Company1 |     | (cid:2)(cid:5)(cid:1)(cid:8) |     | Company2 |     |
(cid:5) (cid:9) (cid:6)(cid:5) (cid:6)(cid:9) (cid:5) (cid:9) (cid:6)(cid:5) (cid:6)(cid:9)
|     |     |     | DMDmode# |     |     |     | DMDmode# |     |
| --- | --- | --- | -------- | --- | --- | --- | -------- | --- |
Figure 13.3. DMDofan18-daysamplingofportfolio datainthebiotechandhealth-
caresector(17companies): ‘DHI’‘LEN’‘PHM’‘TOL’‘NVR’‘HD’‘LOW’‘SHW’‘ONCS’‘BIIB’
‘AMGN’‘CELG’‘GILD’‘REGN’‘VRTX’‘ALXN’‘ILMN’.Thetopleftpanelsh(cid:2)ows,onalogscale,
thepercentageofinformationcapturedineachmodefromtheSVD(1.18)(σ / σ ,whereσ
are
|     |     |     |     |     |     |     |     | j k k |
| --- | --- | --- | --- | --- | --- | --- | --- | ----- |
thediagonalelementsofΣ).Thedata,whichiscolorcodedthroughoutthefigure,isshowntobedom-
inatedbyafewleadingmodes(coloredred,blue,green,andyellowinorderofvariancecontained).
Themiddleleftpanelshowsthe17eigenvaluesω
ofeachmodeusedinthesolution(1.24). Eigen-
|     | valueswithℜ{ω |     | }>0representgrowthmodes. |     | k   |     |     |     |
| --- | ------------- | --- | ------------------------ | --- | --- | --- | --- | --- |
ThefourtoprightpanelsshowtheleadingDMD
i
modes(ψ (x))andtheircompositionfromthe17companiesselected.Thefirstmode(red)showsthe
k
“background”portfolio,oraveragepriceofstocks,overthesamplingwindow.Thedecompositionof
thefirstandsecondcompaniesonthe17DMDmodesisshowninthebottomtwopanels,wherethe
firstfourmodesarehighlighted.ReprintedwithpermissionfromTaylorandFrancis[189].
| 13.4 | Trading |     | performance |     |     |     |     |     |
| ---- | ------- | --- | ----------- | --- | --- | --- | --- | --- |
With the definition of a hot spot, the DMD-based trading strategy can be executed
and evaluated. Before assessing its performance on trading, it is instructive to first
illustrateDMD.Considerasampleof17companiesoveran 18-daytradingwindow
from the biotech and healthcare sectors: ‘DHI’ ‘LEN’ ‘PHM’ ‘TOL’ ‘NVR’ ‘HD’
‘LOW’ ‘SHW’ ‘ONCS’ ‘BIIB’ ‘AMGN’‘CELG’ ‘GILD’‘REGN’ ‘VRTX’‘ALXN’
‘ILMN’.Figure13.3showsallaspectsoftheresultingdecomposition. Specifically,the
SVDproducesadiagonalmatrixwhoseentriesdeterminethemodesofmaximalvari-
ance. Inthiscase,thereisalow-rankstructuretothedata,asdemonstratedinFigure
13.3. Thefirstmodeisparticularlyimportant,asitrepresentstheaveragepriceacross
thesamplingwindow. ThefirstfourDMDmodes,whicharecomposedofweightings
ofthe17companies,arehighlighted,astheyarethemostdominantstructuresinthe

13.4. Tradingperformance 205
(cid:2)(cid:20)(cid:17)(cid:23)(cid:25)(cid:19)(cid:27)(cid:18)(cid:21)(cid:1)(cid:12)(cid:28)(cid:14)(cid:14)(cid:16)(cid:26)(cid:26)(cid:1)(cid:11)(cid:13)(cid:27)(cid:16)(cid:32)(cid:1)(cid:5)(cid:23)(cid:21)(cid:16)(cid:1)(cid:4)(cid:23)(cid:22)(cid:26)(cid:27)(cid:25)(cid:28)(cid:14)(cid:27)(cid:19)(cid:23)(cid:22)(cid:1)
(cid:40)(cid:39)
(cid:48) (cid:39)(cid:33)(cid:44)(cid:41)
m (cid:47)
f
(cid:46) (cid:39)(cid:33)(cid:44)(cid:40)
(cid:45)
(cid:44) (cid:39)(cid:33)(cid:44)
(cid:43)(cid:43)
(cid:42) (cid:39)(cid:33)(cid:43)(cid:48)
(cid:41)
(cid:40)
(cid:40) (cid:41) (cid:42) (cid:43) (cid:44) (cid:45) (cid:46) (cid:47) (cid:48) (cid:40)(cid:39) (cid:40)(cid:40) (cid:40)(cid:41)(cid:40)(cid:42)(cid:40)(cid:43)(cid:40)(cid:44)(cid:40)(cid:45) (cid:40)(cid:46) (cid:40)(cid:47)(cid:40)(cid:48)(cid:41)(cid:39)(cid:41)(cid:40) (cid:41)(cid:41)(cid:41)(cid:42) (cid:41)(cid:43) m
p
(cid:52)(cid:1)(cid:8)(cid:13)(cid:29)(cid:1)(cid:2)(cid:14)(cid:14)(cid:28)(cid:25)(cid:13)(cid:14)(cid:30) (cid:52)(cid:1)(cid:9)(cid:23)(cid:22)(cid:35)(cid:8)(cid:13)(cid:29)(cid:19)(cid:21)(cid:19)(cid:31)(cid:16)(cid:15)(cid:1)(cid:6)(cid:22)(cid:24)(cid:28)(cid:27)(cid:26) (cid:52)(cid:1)(cid:9)(cid:23)(cid:22)(cid:35)(cid:8)(cid:13)(cid:29)(cid:19)(cid:21)(cid:19)(cid:31)(cid:16)(cid:15)(cid:1)(cid:6)(cid:22)(cid:24)(cid:28)(cid:27)(cid:26)
(cid:45)(cid:39)(cid:39)(cid:51) (cid:2)(cid:20)(cid:17)(cid:23)(cid:25)(cid:19)(cid:27)(cid:18)(cid:21)(cid:1)
(cid:44)(cid:39)(cid:39)(cid:51) (cid:12)(cid:36)(cid:10)(cid:1)(cid:44)(cid:39)(cid:39)
(cid:43)(cid:39)(cid:39)(cid:51) (cid:3)(cid:28)(cid:30)(cid:1)(cid:13)(cid:22)(cid:15)(cid:1)(cid:5)(cid:23)(cid:20)(cid:15)
(cid:42)(cid:39)(cid:39)(cid:51)
(cid:41)(cid:39)(cid:39)(cid:51)
(cid:40)(cid:39)(cid:39)(cid:51)
(cid:39)(cid:51)
(cid:7)(cid:28)(cid:22)(cid:16)(cid:1)(cid:34)(cid:39)(cid:44) (cid:7)(cid:28)(cid:22)(cid:16)(cid:1)(cid:34)(cid:40)(cid:44)
successrate
Figure 13.4. Successrates achievedusing different sampling and prediction windows
(m ,m )fortheDMDalgorithmwhenback-testing. Thehotspot(toppanel)showsasuccessrateof
p f
about52.5%overthelast10years,meaningthat52.5%ofallthetradesweexecutedwerecorrect
andmademoney.Thebottompanelsshowhowmuchmoneythealgorithmmakesifweusedifferent
inputsforDMDincomparisontotheS&P500aswellasabuy-and-holdonthestocksusedinthe
DMDalgorithm.Usingthebesthotspotx (11,5)givesthebestreturnof21.48%annualizedover
DMD
10years;however,usingotherinputs,suchasx (11,1)orx (2,5),westillgetpromisingresults
DMD DMD
of19.22%and18.59%annualized,respectively.Whencalculatingthemoneywemade,weranthe
DMDandtradedoffitssignaleachday,enteringaposition,eitherlongorshort,oneverycompany
inthealgorithm. Inthecaseaboveweusedninecompaniesinthehomeconstructionsector(‘DHI’
‘LEN’‘PHM’‘TOL’‘NVR’‘HD’‘LOW’‘SHW’‘SPY’).ReprintedwithpermissionfromTaylorand
Franics[189].
data. Thedistribution of eigenvalues ω is also illustrated, showingthemodes that
k
havegrowth,decay,and/oroscillatorybehavior. TheDMDschemetakesadvantage
ofidentifyingthelargestgrowthmodesforinvestmentpurposes. Finally,theweight-
ingofeach companyontheDMDmodesisalsoillustrated. Thisistheinformation
extractedateachpassoftheDMDalgorithmforagivendatasamplingwindow.
DMD can be used for trading by taking advantage of identifiable hot spots in
x (m ,m ). As already outlined in the learning algorithm, the optimal m and
DMD p f p
m canbeidentifiedandinvestmentsmadeaccordingly. Asaspecificexample,Figure
f
13.4showsthehotspotgeneratedinthehomeconstructionsector. Thehotspothasa
successrateof53%orgreateroverthelast10years,meaningthat53%ofallthetrades
we executed were correct and made money. The bottom panels in this figure show
howmuchmoneythealgorithmmakesifweusedifferentinputsforDMD.Usingthe
best hot spot, x (11,5), gives the best return of 21.48% annualized over 10 years;
however,usingo D t M h D erinputs,suchasx (11,1)orx (2,5),westillgetpromisingre-
DMD DMD
sultsof19.22%and18.59%annualized,respectively. Wecalculatedthemoneyearned

206 Chapter13. FinancialTrading
Figure 13.5. Trading successof Algorithm I of the DMD method for three sectorsex-
hibitinghotspots(transport, homeconstruction, andretail). Theoptimal valuesof(m ,m )are
p f
determinedduringatrainingperiodoftwoyears(July2005toJuly2007).Oncedetermined,thehot
spottradingwindowisusedtoexecutetradesfromJuly2007onwards. Whenahotspotispresent,
thealgorithmcansignificantlyincreasefinancialgainsoverinvestingandholdingintheS&P500.
Figure13.6. DemonstrationoftradingsuccessofAlgorithmIoftheDMDmethodfor
threesectorsthatdonotexhibitahotspot(defense,healthcare,andbiotech). Theoptimalvalueof
(m ,m )isstilldeterminedduringatrainingperiodoftwoyears(July2005toJuly2007). Once
p f
determined,thetradingwindowisusedtoexecutetradesfromJuly2007onwards. Whenthereisno
hotspotpresent,thealgorithmperformsnobetterthaninvestingandholdingintheS&P500.
fromtheDMDalgorithmbytradingfromitspredictionseachday,enteringaposition,
eitherlongorshort,oneverycompanyinthealgorithm. Inthecaseaboveweused
ninecompaniesinthehomeconstructionsector(‘DHI’‘LEN’‘PHM’‘TOL’‘NVR’
‘HD’‘LOW’‘SHW’‘SPY’).Thehomeconstructionindustryisinteresting,sinceeven
whentradingofftheoptimal,moneyisgenerated. ThisisnotcommonfortheDMD
algorithmandismorereflectiveofthehomeconstructionsectorgrowthduringthis
period.
To more accurately assess the DMD trading strategy, consider Figures 13.5 and
13.6. Thefirst ofthese figures showsthe performance of DMDtrading when ahot
spotispresentduringthetrainingperiodofJuly2005toJuly2007(seeFigure13.1).
FromJuly2007,theoptimal(m ,m )isusedfortrading. Withahotspot,theDMD
p f
algorithmprovidesaviabletradingstrategy,performingwellaboveholdingstockin
the S&P 500. If no hot spot is present during training (see Figure 13.2), trading is
executedontheoptimal(m ,m ),withmixedresultsachieved. Figure13.6showsthe
p f
resultsforthreesectorsthatfailtoexhibitahotspot. Inthiscase,itisunclearwhether
thealgorithmshouldbeusedinsteadofsimplyinvestingmoneyintheS&P500.

Glossary
∗
Adjoint– Forafinite-dimensionallinearmap(i.e.,amatrixA),theadjointA isgiven
bythecomplexconjugatetransposeofthematrix.Intheinfinite-dimensionalcontext,
theadjoint&∗ ofalinearoperator& isdefinedsothat〈& f,g〉=〈f,&∗ g〉,where
〈·,·〉isaninnerproduct.
Closed-loopcontrol– Acontrolarchitecturewheretheactuationisinformedbysen-
sordataabouttheoutputofthesystem.
Coherentstructure– Aspatialmodethatiscorrelatedwiththedatafromasystem.
Compressedsensing– Theprocessofreconstructingahigh-dimensionalvectorsig-
nalfromarandomundersamplingofthedatausingthefactthatthehigh-dimensional
signalissparseinaknowntransformbasis,suchastheFourierbasis.
Compression– Theprocessofreducingthesizeofahigh-dimensionalvectororarray
byapproximatingitasasparsevectorinatransformedbasis. Forexample,MP3and
JPG compression use the Fourier basis or wavelet basis tocompress audio or image
signals.
Controltheory– Theframeworkformodifyingadynamicalsystemtoconformto
desiredengineeringspecificationsthroughsensingandactuation.
Data matrix – A matrix where each column vector is a snapshot of the state of a
systemataparticularinstantintime. Thesesnapshotsmaybesequential intime,or
theymaycomefromanensembleofinitialconditionsorexperiments.
DMD amplitude – Theamplitudeofagiven DMDmodeasexpressed inthedata.
TheseamplitudesmaybeinterpretedasthesignificanceofagivenDMDmode,similar
tothepowerspectrumintheFFT.
DMDeigenvalues– Eigenvaluesofthebest-fitDMDoperatorA(seedynamicmode
decomposition)representinganoscillationfrequencyandagrowthordecayterm.
DMDmode(alsodynamicmode)– Aneigenvectorofthebest-fitDMDoperatorA
(seedynamicmodedecomposition). Thesemodesarespatiallycoherentandoscillatein
timeatafixedfrequencyandagrowthordecayrate.
Dynamicmodedecomposition(DMD)– Theleadingeigendecompositionofabest-
207

208 Glossary
fitlinearoperatorA=X (cid:5) X†thatpropagatesthedatamatrixXintoafuturedatamatrix
(cid:5)
X. TheeigenvectorsofAareDMDmodesandthecorrespondingeigenvaluesdeter-
minethetimedynamicsofthesemodes.
Dynamicalsystem– Amathematicalmodelforthedynamicevolutionofasystem.
Typically,adynamicalsystemisformulatedintermsofordinarydifferentialequations
onastate-space. Theresultingequationsmaybelinearornonlinearandmayalsoin-
cludetheeffectofactuationinputsandrepresentoutputsassensormeasurementsof
thestate.
Eigensystemrealizationalgorithm(ERA)– Asystemidentificationtechniquethat
producesbalancedinput-outputmodelsofasystemfromimpulseresponsedata. ERA
hasbeen shown toproduce equivalent models toBPOD and DMD under some cir-
cumstances.
Emission– ThemeasurementfunctionsforanHMM.
Equation-free modeling (EFM) – The process of characterizing a dynamical sys-
temthroughmeasurementdataasopposedtofirstprinciplesmodelingofphysics. It
isimportanttonotethatequation-freemodelingdoesresultinequationsthatmodel
thesystem,butthesemethodsaredatadrivenanddonotstartwithknowledgeofthe
high-fidelitygoverningequations.
Feedbackcontrol– Closed-loopcontrolwheresensorsmeasurethedownstreamef-
fectofactuators,sothatinformationisfedbacktotheactuators. Feedbackisessential
forrobustcontrolwheremodeluncertaintyandinstabilitymaybecounteractedwith
fastsensorfeedback.
Feedforwardcontrol– Controlwheresensorsmeasuretheupstreamdisturbancesto
asystem,sothatinformationisfedforwardtoactuatorstocanceldisturbancesproac-
tively.
Hidden Markov model (HMM) – A Markov model where there is a hidden state
thatisonlyobservedthroughasetofmeasurementsknownasemissions.
Hilbertspace– Ageneralizedvectorspacewithaninnerproduct. Whenusedinthis
text,aHilbertspacetypicallyreferstoaninfinite-dimensionalfunctionspace. These
spacesarealsocompletemetricspaces,providingasufficientmathematicalframework
toenablecalculusonfunctions.
Incoherentmeasurements– Measurementsthathaveasmallinnerproductwiththe
basisvectorsofasparsifyingtransform. Forinstance,single-pixelmeasurements(i.e.,
spatial delta functions) are incoherent with respect to the spatial Fourier transform
basis,sincethesesingle-pixelmeasurementsexciteallfrequenciesanddonotpreferen-
tiallyalignwithanysinglefrequency.
Kalman filter – Anestimatorthatreconstructsthefullstateofadynamicalsystem
from measurements of a time series of the sensor outputs and actuation inputs. A
Kalmanfilterisitselfadynamicalsystemthatisconstructedforobservablesystemsto
stablyconvergetothetruestateofthesystem. TheKalmanfilterisoptimalforlinear

Glossary 209
systemswithGaussianprocessandmeasurementnoiseofaknownmagnitude.
Koopmaneigenfunction– AneigenfunctionoftheKoopmanoperator. Theseeigen-
functionscorrespondtomeasurementsonthestate-spaceofadynamicalsystemthat
formintrinsiccoordinates. Inotherwords,theseintrinsicmeasurementswillevolve
linearlyintimedespitetheunderlyingsystembeingnonlinear.
Koopman operator – Aninfinite-dimensionallinearoperatorthatpropagatesmea-
surementfunctionsfromaninfinite-dimensionalHilbertspacethroughadynamical
system.
Least-squares regression – Aregression techniquewhereabest-fitlineorvectoris
foundbyminimizingthesumofsquaresoftheerrorbetweenthemodelandthedata.
Linear system – Asystemwheresuperposition ofanytwoinputsresultsinthesu-
perposition of the two corresponding outputs. In other words, doubling the input
doublestheoutput. Lineartime-invariantdynamicalsystemsarecharacterizedbylin-
earoperators,whicharerepresentedasmatrices.
Lowrank– Apropertyofamatrixwherethenumberoflinearlyindependentrows
andcolumnsissmallcompared withthesizeofthematrix. Generally, low-rankap-
proximationsaresoughtforlargedatamatrices.
Markov model – Aprobabilisticdynamicalsystemwherethestatevectorcontains
the probability that the system will be in a given state; thus, this state vector must
alwayssumtounity. ThedynamicsaregivenbytheMarkovtransitionmatrix,which
isconstructedsothateachrowsumstounity.
Markovparameters– Theoutputmeasurementsofadynamicalsysteminresponse
toanimpulsiveinput.
Moore’slaw– Theobservationthattransistordensity,andhenceprocessorspeed,in-
creaseexponentiallyintime.Moore’slawiscommonlyusedtopredictcomputational
powerandtheassociatedincreaseinthescaleofproblemthatwillbecomputationally
feasible.
Multiscale – Theproperty ofhaving manyscalesin space and/ortime. Manysys-
tems, such as turbulence, exhibit spatial and temporal scales that vary across many
ordersofmagnitude.
Observablefunction– Afunctionthatmeasuressomepropertyofthestateofasys-
tem. ObservablefunctionsaretypicallyelementsofaHilbertspace.
Overdetermined system – AsystemAx=bwheretherearemoreequationsthan
unknowns. Usuallythereisnoexactsolutionxtoanoverdeterminedsystem,unless
thevectorbisinthecolumnspaceofA.
Perron–Frobenius operator – The adjoint of the Koopman operator; an infinite-
dimensionaloperatorthatadvancesprobabilitydensityfunctionsthroughadynamical
system.

210 Glossary
Powerspectrum– ThesquaredmagnitudeofeachcoefficientofaFouriertransform
ofasignal. Thepowercorresponds totheamountofeach frequencyrequiredtore-
constructagivensignal.
Principal component – Aspatiallycorrelated modeinagivendataset,oftencom-
putedusingtheSVDofthedataafterthemeanhasbeensubtracted.
Principal component analysis (PCA) – A decomposition of a data matrix into a
hierarchy of principal component vectors that are ordered from most correlated to
leastcorrelatedwiththedata. PCAiscomputedbytakingtheSVDofthedataafter
subtractingthemean. Inthiscase, each singularvaluerepresentsthevarianceofthe
correspondingprincipalcomponent(singularvector)inthedata.
Proper orthogonal decomposition (POD) – The decomposition of data from a
dynamicalsystemintoahierarchical setoforthogonal modes, oftenusingtheSVD.
Whenthedataconsistsofvelocitymeasurementsofasystem,suchasanincompress-
ible fluid, then POD orders modes in terms of the amount of energy these modes
containinthegivendata.
Pseudoinverse– Thepseudoinversegeneralizesthematrixinversefornonsquarema-
trices, and is often used to compute the least-squares solution to a system of equa-
tions. TheSVDisacommonmethodtocomputethepseudoinverse: giventheSVD
X=UΣV ∗ ,thepseudoinverseisX†=VΣ−1U ∗ .
Reduced-ordermodel(ROM)– Amodelofahigh-dimensionalsystemintermsofa
low-dimensionalstate.Typically,anROMbalancesaccuracywithcomputationalcost
ofthemodel.
Regression– Astatisticalmodelthatrepresentsanoutcomevariableintermsofindi-
catorvariables. Least-squaresregressionisalinearregressionthatfindsthelineofbest
fittodata;whengeneralizedtohigherdimensionsandmultilinearregression,thisgen-
eralizestoPCR.Nonlinearregression,dynamicregression,andfunctionalorsemantic
regressionareusedinsystemidentification,modelreduction,andmachinelearning.
Restrictedisometryproperty(RIP)– Thepropertythatamatrixactslikeaunitary
matrix,oranisometrymap,onsparsevectors. Inotherwords,thedistancebetween
anytwosparsevectorsispreservedifthesevectorsaremappedthroughamatrixthat
satisfiestheRIP.
Singularvaluedecomposition(SVD)–
GivenamatrixX∈(cid:4)n×m,theSVDisgiven
byX=UΣV ∗ ,whereU∈(cid:4)n×n,Σ∈(cid:4)n×m,andV∈(cid:4)m×m. ThematricesUandV
areunitary,sothatUU ∗ =U ∗ U=IandVV ∗ =V ∗ V=I. ThematrixΣhasentries
alongthediagonalcorrespondingtothesingularvaluesorderedfromlargesttosmall-
est. Thisproducesahierarchicalmatrixdecompositionthatsplitsamatrixintoasum
ofrank-onematricesgivenbytheouterproductofacolumnvector(leftsingularvec-
tor)witharowvector(conjugatetransposeofrightsingularvector). Theserank-one
matricesareorderedbythesingularvaluesothatthefirst r rank-onematricesform
thebestrank-r matrixapproximationoftheoriginalmatrixinaleast-squaressense.

Glossary 211
Snapshot– Asinglehigh-dimensionalmeasurementofasystemataparticulartime.
Anumber of snapshotscollected at asequence oftimesmay be arranged ascolumn
vectorsinadatamatrix.
Sparsity – A vector issparse ifmost of itsentriesare zeroor nearlyzero. Sparsity
referstotheobservation thatmostdataaresparsewhenrepresentedasvectorsinan
appropriatetransformedbasis,suchasaFourierorPODbasis.
State-space – Theset ofallpossible system states. Often thestate-space isavector
space,suchas(cid:2)n,althoughitmayalsobeasmoothmanifold(cid:22).
System identification – Theprocessby whichamodel isconstructed forasystem
frommeasurementdata,possiblyafterperturbingthesystem.
Time-delay coordinates – Anaugmentedsetofcoordinatesconstructed byconsid-
eringameasurementatthecurrenttimealongwithanumberoftimesinthepastat
fixed intervals from thecurrent time. Time-delaycoordinates areoften useful inre-
constructingattractordynamicsforsystemsthatdonothaveenoughmeasurements,
asintheTakensembeddingtheorem.
Total least squares – Aleast-squaresregression algorithmthatminimizestheerror
on both the inputs and the outputs. Geometrically, this corresponds to finding the
linethatminimizesthesumofsquaresofthetotaldistancetoallpoints,ratherthan
thesumofsquaresoftheverticaldistancetoallpoints.
Uncertainty quantification – Theprincipled characterization and managementof
uncertaintyinengineeringsystems. Uncertaintyquantificationofteninvolvestheap-
plicationofpowerfultoolsfromprobabilityandstatisticstodynamicalsystems.
Underdeterminedsystem– AsystemAx=bwheretherearefewerequationsthan
unknowns. Generallythesystemhasinfinitelymanysolutionsxunlessbisnotinthe
columnspaceofA.
Unitarymatrix– Amatrixwhosecomplexconjugatetransposeisalsoitsinverse. All
eigenvaluesofaunitarymatrixareonthecomplexunitcircle,andtheactionofauni-
tarymatrixmaybethoughtofasachangeofcoordinatesthatpreservestheEuclidean
distancebetweenanytwovectors.

Bibliography
[1] AdvancedVideoandSignal BasedSurveillanceDatasets, 2007. i-LidsDatasetfor AVSS
London2007. (Citedonp.66)
[2] Low-RankMatrixRecoveryandCompletionviaConvexOptimizationSampleCode,2013.
PerceptionandDecisionLab,UniversityofIllinoisatUrbana-Champaign,andMicrosoft
ResearchAsia,Beijing,Copyright2009. (Citedonp.57)
[3] E. Acar and E. S. Satchell. Advanced Trading Rules. Butterworth-Heinemann, 2002.
(Citedonp.196)
[4] R. J. Adrian. Particle-imagingtechniques for experimental fluid mechanics. Annual
ReviewofFluidMechanics,23(1):261–304,1991. (Citedonp.27)
[5] M.B.Ahrens,J.M.Li,M.B.Orger,D.N.Robson,A.F.Schier,F.Engert,andR.Por-
tugues. Brain-wideneuronaldynamicsduringmotoradaptationinzebrafish. Nature,
485(7399):471–477,2012.(Citedonp.187)
[6] H.Akaike.Anewlookatthestatisticalmodelidentification.IEEETrans.onAutomatic
Control,19(6):716–723,1974. (Citedonp.114)
[7] M.R.AllenandL.A.Smith. MonteCarloSSA:Detectingirregularoscillationsinthe
presenceofcolorednoise. JournalofClimate,9(12):3373–3404,1996. (Citedonp.110)
[8] R.AlmgrenandJ.Lorenz. Bayesianadaptivetradingwithadailycycle. TheJournalof
Trading,1:38–46,2006.(Citedonp.196)
[9] R.Anderson, R.May,andB.Anderson. InfectiousDiseasesofHumans: Dynamicsand
Control. OxfordUniversityPress,1992.(Citedonp.179)
[10] M.AvellanedaandJ.Lee. StatisticalarbitrageintheU.S.equitiesmarket. Quantitative
Finance,10:761–782,2008. (Citedonp.196)
[11] F.A.Azevedo,L.R.Carvalho,L.T.Grinberg,J.M.Farfel,R.E.Ferretti,R.E.Leite,
R.Lent,andS.Herculano-Houzel. Equalnumbersofneuronalandnonneuronalcells
makethehumanbrainanisometricallyscaled-upprimatebrain. JournalofComparative
Neurology,513(5):532–541,2009. (Citedonp.185)
[12] S. Bagheri. Effects of small noise on the DMD/Koopman spectrum. Bulletin of the
AmericanPhysicalSociety,58(18):H35.0002,p.230,2013. (Citedonpp.119,147)
[13] S.Bagheri. Koopman-modedecompositionofthecylinderwake. JournalofFluidMe-
chanics,726:596–623,2013. (Citedonpp.31,37)
[14] Z. Bai, S. L. Brunton, B. W. Brunton, J. N. Kutz, E. Kaiser, A. Spohn, and B. R.
Noack. Data-driven methods in fluid dynamics: Sparse classification from experi-
mental data. In Whither Turbulence and Big Data in the 21st Century, A. Pollard, L.
213

214 Bibliography
Castillo,L.Danaila,andM.Glauser,eds.,Springer,NewYork,2017,pp.323–342(see
http://link.springer.com/chapter/10.1007%2F978-3-319-41217-7_17).(Citedonp.21)
[15] Z. Bai, T. Wimalajeewa, Z. Berger, G. Wang, M. Glauser, and P. K. Varshney. Low-
dimensionalapproachforreconstructionofairfoildataviacompressivesensing. AIAA
Journal,53(4):920–933,2014. (Citedonpp.24,136,139,140)
[16] S.P.Banks. Infinite-dimensionalCarlemanlinearization,theLieseriesandoptimalcon-
trolofnon-linearpartialdifferentialequations. InternationalJournalofSystemsScience,
23(5):663–675,1992. (Citedonp.51)
[17] R.G.Baraniuk. Compressivesensing. IEEESignalProcessingMagazine,24(4):118–120,
2007.(Citedonpp.134,135)
[18] R.G.Baraniuk,V.Cevher,M.F.Duarte,andC.Hegde. Model-basedcompressivesens-
ing. IEEETransactionsonInformationTheory,56(4):1982–2001,2010. (Citedonp.134)
[19] J. Basley, L. R. Pastur, N. Delprat, and F. Lusseyran. Space-time aspects of a three-
dimensional multi-modulatedopen cavity flow. Physics of Fluids, 25(6):064105, 2013.
(Citedonp.31)
[20] J.Basley,L.R.Pastur,F.Lusseyran,T.M.Faure,andN.Delprat. Experimentalinves-
tigationofglobalstructuresinanincompressiblecavityflowusingtime-resolvedPIV.
ExperimentsinFluids,50(4):905–918,2011. (Citedonp.31)
[21] G.BaudatandF.Anouar. Kernel-basedmethodsandfunctionapproximation. Proceed-
ingsoftheInternationalJointConferenceonNeuralNetworks,2:1244–1249,2001. (Cited
onpp.160,170)
[22] A.J.BellandT.J.Sejnowski. The“independentcomponents”ofnaturalscenesareedge
filters. VisionResearch,37(23):3327–3338,1997. (Citedonp.187)
[23] G. Bellani. Experimental studies of complex flows through image-based techniques.
Ph.D.thesis,RoyalInstituteofTechnology,Stockholm,Sweden,2011.(Citedonp.31)
[24] B.A.Belson,J.H.Tu,andC.W.Rowley.Algorithm945:modred—Aparallelizedmodel
reductionlibrary. ACMTransactions onMathematicalSoftware, 40(4):30:1–30:23,2014.
(Citedonp.32)
[25] Y.Benezeth,P.M.Jodoin,B.Emile,H.Laurent,andC.Rosenberger.Comparativestudy
ofbackgroundsubtractionalgorithms.JournalofElectronicImaging,19(3):033003,2010.
(Citedonp.55)
[26] E.Berger,M.Sastuba,D.Vogt,B.Jung,andH.B.Amor. Estimationofperturbations
inroboticbehaviorusingdynamicmodedecomposition. JournalofAdvancedRobotics,
29(5):331–343,2015. (Citedonp.128)
[27] G.Berkooz,P.Holmes,andJ.L.Lumley.Theproperorthogonaldecompositioninthe
analysisofturbulentflows. AnnualReviewofFluidMechanics,23:539–575,1993. (Cited
onpp.25,26,28)
[28] BillandMelindaGatesFoundation.Foundationfactsheet,2016. (Citedonp.177)
[29] C.Bishop. PatternRecognitionandMachineLearning. Springer,2006. (Citedonp.159)
[30] D.A.BistrianandI.M.Navon.Animprovedalgorithmfortheshallowwaterequations
model reduction: Dynamic mode decompositionvs. POD. International Journal for
NumericalMethodsinFluids,78(9):552–580,2015. (Citedonp.32)

Bibliography 215
[31] J.BongardandH.Lipson. Automatedreverseengineeringofnonlineardynamicalsys-
tems. ProceedingsoftheNationalAcademyofSciences,104(24):9943–9948,2007. (Cited
onp.24)
[32] G.E.P.Box, G.M.Jenkins, andG.C.Reinsel. TimeSeriesAnalysis: Forecasting and
Control,3rdEd. PrenticeHall,1994. (Citedonp.22)
[33] W.E.BoyceandR.C.DiPrima.ElementaryDifferentialEquations,9thEd.Wiley,2008.
(Citedonp.4)
[34] O.Brandouy, J.P.Delahaye,andL.Ma. Acomputationaldefinitionoffinancialran-
domness. QuantitativeFinance,14:761–770,2014.(Citedonp.196)
[35] M.BranickiandA.Majda.Aninformation-theoreticframeworkforimprovingimperfect
predictionsviamulti-modelensembleforecasts. JournalofNonlinearScience,25(3):489–
538,2015. (Citedonp.21)
[36] I.Bright,G.Lin,andJ.N.Kutz. Compressivesensingbasedmachinelearningstrategy
forcharacterizingtheflowaroundacylinderwithlimitedpressuremeasurements.Physics
ofFluids,25:127102,2013.(Citedonpp.21,136)
[37] R.W.Brockett.Volterraseriesandgeometriccontroltheory.Automatica,12(2):167–176,
1976.(Citedonp.51)
[38] C.Brooks,A.G.Rew,andS.Ritson.Atradingstrategybasedonthelead-lagrelationship
betweentheFTSE100spotindexandtheLIFFEtradedFTSEfuturescontract.Interna-
tionalJournalofForecasting,17:31–44,2001. (Citedonp.196)
[39] B.M.Broome,V.Jayaraman,andG.Laurent. Encodinganddecodingofoverlapping
odorsequences.Neuron,51(4):467–482,2006.(Citedonp.187)
[40] D.S.BroomheadandR.Jones.Time-seriesanalysis.InProceedingsoftheRoyalSocietyof
LondonA:Mathematical,PhysicalandEngineeringSciences,volume423,pages103–121.
TheRoyalSociety,1989. (Citedonp.110)
[41] D.S.Broomhead,R.Jones,andG.P.King.Topologicaldimensionandlocalcoordinates
fromtimeseriesdata. JournalofPhysicsA:MathematicalandGeneral,20(9):L563,1987.
(Citedonp.110)
[42] D.S.BroomheadandG.P.King. Extractingqualitativedynamicsfromexperimental
data.PhysicaD:NonlinearPhenomena,20(2–3):217–236,1986. (Citedonp.110)
[43] B.W.Brunton,S.L.Brunton,J.L.Proctor,andJ.N.Kutz. Optimalsensorplacement
andenhancedsparsityforclassification. arXivpreprint,arXiv:1310.4217,2013. (Cited
onpp.21,136)
[44] B. W. Brunton, L. A. Johnson, J. G. Ojemann, and J. N. Kutz. Extracting spatial–
temporalcoherentpatternsinlarge-scaleneuralrecordingsusingdynamicmodedecom-
position. JournalofNeuroscienceMethods,258:1–15,2016.(Citedonp.188)
[45] S.L.Brunton,B.W.Brunton,J.L.Proctor,andJ.NKutz. Koopmanobservablesub-
spacesandfinitelinearrepresentationsofnonlineardynamicalsystemsforcontrol.PLoS
ONE,11(2):e0150171,2016. (Citedonpp.24,45,46,51,52)
[46] S.L.BruntonandB.R.Noack.Closed-loopturbulencecontrol:Progressandchallenges.
AppliedMechanicsReviews,67:050801–1–050801–48,2015. (Citedonp.27)
[47] S.L.Brunton,J.L.Proctor,andJ.N.Kutz.Discoveringgoverningequationsfromdata:
Sparseidentificationofnonlineardynamicalsystems.ProceedingsoftheNationalAcademy
ofSciences,2016. (Citedonpp.24,45)

216 Bibliography
[48] S.L.Brunton,J.L.Proctor,J.H.Tu,andJ.N.Kutz. Compressedsensinganddynamic
modedecomposition. JournalofComputational Dynamics,2(2):165–191,2015. (Cited
onpp.5,32,134,140,141,142,143,144,145,146,147)
[49] S.L.Brunton,J.H.Tu,I.Bright,andJ.N.Kutz. Compressivesensingandlow-rank
librariesforclassificationofbifurcationregimesinnonlineardynamicalsystems. SIAM
JournalonAppliedDynamicalSystems,13(4):1716–1732,2014.(Citedonpp.21,24)
[50] M.Budiši´candI.Mezi´c.Anapproximateparametrizationoftheergodicpartitionusing
timeaveragedobservables. InProceedingsofthe48thIEEEConferenceonDecisionand
Control,2009heldjointlywiththe200928thChineseControlConference.CDC/CCC2009,
pages3162–3168.IEEE,2009.(Citedonp.45)
[51] M.Budiši´candI.Mezi´c. Geometryoftheergodicquotientrevealscoherentstructures
inflows. PhysicaD:NonlinearPhenomena,241(15):1255–1269,2012. (Citedonp.45)
[52] M.Budiši´c,R.Mohr,andI.Mezi´c.AppliedKoopmanisma).Chaos:AnInterdisciplinary
JournalofNonlinearScience,22(4):047510,2012. (Citedonpp.31,45)
[53] C.J.Burges.Atutorialonsupportvectormachinesforpatternrecognition.DataMining
andKnowledgeDiscovery,2:121–167,1998.(Citedonpp.160,170)
[54] P. A. Businger and G. H. Golub. Algorithm358: Singularvalue decompositionof a
complexmatrix[f1,4,5].CommunicationsoftheACM,12(10):564–565,1969.(Citedon
pp.28,131)
[55] V.D.Calhoun,T.Adali,V.B.McGinty,J.J.Pekar,T.D.Watson,andG.D.Pearlson.
fMRIactivationinavisual-perceptiontask: networkofareasdetectedusingthegeneral
linearmodelandindependentcomponentsanalysis.NeuroImage,14(5):1080–1088,2001.
(Citedonp.187)
[56] E.Candès,X.Li,Y.Ma,andJ.Wright.Robustprincipalcomponentanalysis?Computing
ResearchRepository,abs/0912.3599,2009. (Citedonpp.55,56,57,58,63)
[57] E.J.Candès. Compressivesensing. ProceedingsoftheInternational CongressofMathe-
maticians,III:1433–1452,2006. (Citedonp.135)
[58] E.J.Candès,J.Romberg,andT.Tao.Robustuncertaintyprinciples:Exactsignalrecon-
structionfromhighlyincompletefrequencyinformation.IEEETransactionsonInforma-
tionTheory,52(2):489–509,2006.(Citedonpp.134,135)
[59] E.J.Candès,J.Romberg,andT.Tao.Stablesignalrecoveryfromincompleteandinaccu-
ratemeasurements.CommunicationsonPureandAppliedMathematics,59(8):1207–1223,
2006.(Citedonpp.134,135)
[60] E.J.CandèsandT.Tao. Nearoptimalsignalrecoveryfromrandomprojections: Uni-
versalencodingstrategies? IEEETransactionsonInformationTheory,52(12):5406–5425,
2006.(Citedonpp.134,135,141)
[61] T.Carleman. Applicationdelathéoriedeséquationsintégraleslinéairesauxsystèmes
d’équationsdifférentiellesnonlinéaires.ActaMathematica,59(1):63–87,1932.(Citedon
p.51)
[62] J.K.Chapin. Usingmulti-neuronpopulationrecordingsforneuralprosthetics. Nature
Neuroscience,7(5):452–455,2004. (Citedonp.187)
[63] S.ChaturantabutandD.C.Sorensen.Nonlinearmodelreductionviadiscreteempirical
interpolation. SIAMJournalonScientificComputing,32(5):2737–2764,2010. (Citedon
p.21)

Bibliography 217
[64] K.K.Chen, J.H.Tu, andC.W.Rowley. Variantsofdynamicmodedecomposition:
Boundary condition, Koopman, and Fourier analyses. Journal of Nonlinear Science,
22(6):887–915,2012. (Citedonpp.22,32,124,133)
[65] X.Cheng,P.L.H.Yu,andW.K.Li. Baskettradingunderco-integrationwiththelogis-
ticmixtureautoregressivemodel. QuantitativeFinance,11:1407–1419,2011. (Citedon
p.196)
[66] C.Chiarella,X.Z.He,andC.Hommes. Adynamicanalysisofmovingaveragerules.
JournalofEconomicDynamicsandControl,30:1729–1753,2006.(Citedonp.196)
[67] M. M. Churchland, J. P. Cunningham, M. T. Kaufman, J. D. Foster, P. Nuyujukian,
S. I. Ryu, and K. V. Shenoy. Neural population dynamics during reaching. Nature,
487(7405):52–56,2012. (Citedonp.187)
[68] L.Clemmensen,T.Hastie,D.Witten,andB.Ersbøll.Sparsediscriminantanalysis.Tech-
nometrics,2012. (Citedonp.21)
[69] J.Y.Cohen, S.Haesler, L.Vong, B.B. Lowell, andN. Uchida. Neuron-type-specific
signalsforrewardandpunishmentintheventraltegmentalarea. Nature,482(7383):85–
88,2012.(Citedonp.187)
[70] T.ColoniusandK.Taira.Afastimmersedboundarymethodusinganullspaceapproach
andmulti-domainfar-fieldboundaryconditions.ComputerMethodsinAppliedMechanics
andEngineering,197:2131–2146,2008.(Citedonp.33)
[71] R.Courant,K.Friedrichs,andH.Lewy. Onthepartialdifferenceequationsofmathe-
maticalphysics. IBMJournalofResearchandDevelopment,11(2):215–234,1967. (Cited
onp.33)
[72] N.Crockford.AnIntroductiontoRiskManagement,2ndEd.Woodhead-Faulkner,1986.
(Citedonp.196)
[73] J.P. Cunningham and Z. Ghahramani. Linear dimensionalityreduction: Survey, in-
sights,andgeneralizations. Journal ofMachineLearningResearch,16:2859–2900,2015.
(Citedonp.188)
[74] J.P.CunninghamandB.M.Yu.Dimensionalityreductionforlarge-scaleneuralrecord-
ings. NatureNeuroscience,17(11):1500–1509,2014. (Citedonp.187)
[75] A. d’Aspremont. Identifying small mean-reverting portfolios. Quantitative Finance,
11:351–364,2011. (Citedonp.196)
[76] I.Daubechies.TenLecturesonWavelets.SIAM,1992. (Citedonpp.71,78)
[77] S.Dawson,M.S.Hemati,M.O.Williams,andC.W.Rowley. Characterizingandcor-
rectingfortheeffectofsensornoiseinthedynamicmodedecomposition. Experiments
inFluids,57:42,2016. (Citedonpp.119,128,130)
[78] L.Debnath. WaveletTransformsandTheirApplications. Birkhäuser,2002. (Citedon
pp.71,78)
[79] M.Dellnitz,G.Froyland,andO.Junge. ThealgorithmsbehindGAIO—Setoriented
numerical methods for dynamical systems. In Ergodic Theory, Analysis, and Efficient
SimulationofDynamicalSystems,pages145–174.Springer,2001.(Citedonpp.33,45)
[80] M.DellnitzandO.Junge.Setorientednumericalmethodsfordynamicalsystems.Hand-
bookofDynamicalSystems,2:221–264,2002. (Citedonpp.33,45)

218 Bibliography
[81] D.L.Donoho. De-noisingbysoft-thresholding. IEEETransactionsonInformationThe-
ory,41(3):613–627,1995. (Citedonp.126)
[82] D. L. Donoho. Compressed sensing. IEEE Transactions on Information Theory,
52(4):1289–1306,2006. (Citedonpp.134,135)
[83] M.E.Drew,R.J.Bianchi,andJ.Polichronis. Atestofmomentumtradingstrategiesin
foreignexchangemarkets:EvidencefromtheG7.GlobalBusinessandEconomicsReview,
7:155–179,2005.(Citedonp.196)
[84] R.Duda,P.Hart,andD.Stork. PatternClassification,2ndEd. Wiley,2001. (Citedon
p.159)
[85] D.Duke,D.Honnery,andJ.Soria.Experimentalinvestigationofnonlinearinstabilities
inannularliquidsheets. JournalofFluidMechanics,691:594–604,2012.(Citedonp.32)
[86] D.Duke,J.Soria,andD.Honnery. Anerroranalysisofthedynamicmodedecomposi-
tion. ExperimentsinFluids,52(2):529–542,2012. (Citedonp.32)
[87] R.DunneandB.J.McKeon.Dynamicstallonapitchingandsurgingairfoil.Experiments
inFluids,56(8):1–15,2015. (Citedonp.31)
[88] A. Duran and M. J. Bommarito. A profitable trading and risk management strategy
despitetransactioncost. QuantitativeFinance,11:829–848,2011.(Citedonp.196)
[89] S.R.Eddy.HiddenMarkovmodels.CurrentOpinioninStructuralBiology,6(3):361–365,
1996.(Citedonp.113)
[90] R.Elliott,J.VanderHoek,andW.Malcolm.Pairstrading.QuantitativeFinance,5:271–
276,2005. (Citedonp.196)
[91] N.B.Erichson,S.L.Brunton,andJ.N.Kutz. Compresseddynamicmodedecompo-
sitionforreal-timeobjectdetection. arXivpreprint,arXiv:1512.04205,2015. (Citedon
pp.55,140)
[92] R.EversonandL.Sirovich.Karhunen–Loéveprocedureforgappydata.JournalofOptical
SocietyofAmericaA,12:1657–1664,1995. (Citedonp.21)
[93] R.P.Feynman,R.B.Leighton,andM.Sands.TheFeynmanLecturesonPhysics,volume2.
BasicBooks,2013. (Citedonp.25)
[94] R.D.FierroandJ.R.Bunch. Orthogonalprojectionandtotalleastsquares. Numerical
LinearAlgebrawithApplications,2(2):135–153,1995. (Citedonp.131)
[95] R.D.Fierro,G.H.Golub,P.C.Hansen,andD.P.O’Leary.Regularizationbytruncated
totalleastsquares. SIAMJournalonScientificComputing,18(4):1223–1241,1997. (Cited
onp.131)
[96] J.W.ForemanJr.,E.W.George,andR.D.Lewis. Measurementoflocalizedflowve-
locitiesingaseswithalaserDopplerflowmeter.AppliedPhysicsLetters,7(4):77–78,1965.
(Citedonp.27)
[97] J.E.Fowler. Compressive-projectionprincipalcomponentanalysis. IEEETransactions
onImageProcessing,18(10):2230–2242,2009.(Citedonp.136)
[98] B.Friedman. PrinciplesandTechniquesofAppliedMathematics. Dover,1990. (Citedon
p.39)
[99] M.Frömmel,R.MacDonald,andL.Menkhoff.Markovswitchingregimesinamonetary
exchangeratemodel.EconomicModelling,22:485–502,2005.(Citedonp.196)

Bibliography 219
[100] G.Froyland.Statisticallyoptimalalmost-invariantsets.PhysicaD:NonlinearPhenomena,
200(3):205–219,2005. (Citedonpp.33,45)
[101] G.Froyland,G.A.Gottwald,andA.Hammerlindl.Acomputationalmethodtoextract
macroscopicvariablesandtheirdynamicsinmultiscalesystems.SIAMJournalonApplied
DynamicalSystems,13(4):1816–1846,2014.(Citedonpp.33,45)
[102] G.FroylandandK.Padberg.Almost-invariantsetsandinvariantmanifolds—Connecting
probabilistic and geometric descriptions of coherent structures in flows. Physica D,
238:1507–1523,2009. (Citedonpp.33,45)
[103] G. Froyland, N. Santitissadeekorn, and A. Monahan. Transport in time-dependent
dynamicalsystems: Finite-timecoherentsets. Chaos, 20(4):043116-1–043116-16,2010.
(Citedonpp.33,45)
[104] P.Gaspard.Chaos,ScatteringandStatisticalMechanics.Cambridge,1995.(Citedonp.50)
[105] H. Gävert, J. Hurry, J. Särelä, and A. Hyvärinen. FastICA: Fast
independent component analysis. Computing Research Repository,
http://research.ics.aalto.fi/ica/fastica/index.shtml.(Citedonp.14)
(cid:9)
[106] M.GavishandD.L.Donoho. Theoptimalhardthresholdforsingularvaluesis4/ 3.
IEEETransactionsonInformationTheory,60(8):5040–5053,2014. (Citedonpp.7,126,
127)
[107] C. W. Gear, J. M. Hyman, P. G. Kevrekidids, I. G. Kevrekidis, O. Runborg, and
C. Theodoropoulos. Equation-free, coarse-grained multiscalecomputation: Enabling
mocroscopic[sic]simulatorstoperformsystem-levelanalysis.CommunicationsinMath-
ematicalSciences,4:715–762,2003. (Citedonp.20)
[108] C.W.Gear,J.Li,andI.G.Kevrekidis. Thegap-toothmethodinparticlesimulations.
PhysicalLettersA,316:190–195,2003.(Citedonp.21)
[109] R.Gencay,M.Dacorogna,U.A.Muller,R.Olsen,andO.Pictet. AnIntroductionto
High-FrequencyFinance. AcademicPress,2001. (Citedonp.196)
[110] D.GiannakisandA.J.Majda.NonlinearLaplacianspectralanalysisfortimeserieswith
intermittencyandlow-frequencyvariability. ProceedingsoftheNationalAcademyofSci-
encesoftheUSA,109(7):2222–2227,2012. (Citedonp.110)
[111] A.C.GilbertandP.Indyk. Sparserecoveryusingsparsematrices. Proceedingsofthe
IEEE,98(6):937–947,2010.(Citedonp.135)
[112] A. C. Gilbert, J. Y. Park, and M. B. Wakin. Sketched SVD:Recovering spectral fea-
turesfromcompressivemeasurements.arXivpreprint,arXiv:1211.0361,2012.(Citedon
p.136)
[113] J.Ginsberg,M.H.Mohebbi,R.S.Patel,L.Brammer,M.S.Smolinski,andL.Brilliant.
Detectinginfluenzaepidemicsusingsearchenginequerydata. Nature,457(7232):1012–
1014,022009. (Citedonp.182)
[114] G.GolubandW.Kahan.Calculatingthesingularvaluesandpseudo-inverseofamatrix.
JournaloftheSocietyforIndustrialandAppliedMathematics,SeriesB:NumericalAnalysis,
2(2):205–224,1965. (Citedonpp.26,28,131)
[115] G.H.Golub,P.C.Hansen,andD.P.O’Leary. Tikhonovregularizationandtotalleast
squares. SIAMJournalonMatrixAnalysisandApplications,21(1):185–194,1999. (Cited
onp.131)

220 Bibliography
[116] G.H.GolubandC.Reinsch. Singularvaluedecompositionandleastsquaressolutions.
NumericalMathematics,14:403–420,1970.(Citedonpp.26,28,131)
[117] G.H.GolubandC.VanLoan. Totalleastsquares. InSmoothingTechniquesforCurve
Estimation,pages69–76.Springer,1979.(Citedonp.131)
[118] G.H.GolubandC.F.VanLoan. Ananalysisofthetotalleastsquaresproblem. SIAM
JournalonNumericalAnalysis,17(6):883–893,1980.(Citedonpp.119,131)
[119] G.H.GolubandC.F.VanLoan. MatrixComputations, volume3. JHUPress,2012.
(Citedonpp.28,131)
[120] M.Grilli,P.J.Schmid,S.Hickel,andN.A.Adams. Analysisofunsteadybehaviourin
shockwaveturbulentboundarylayerinteraction. JournalofFluidMechanics,700:16–28,
2012.(Citedonp.32)
[121] J.GrosekandJ.N.Kutz.Dynamicmodedecompositionforreal-timebackground/fore-
groundseparationinvideo. arXiv preprint, arXiv:1404.7592,2014. (Citedonpp.55,
70)
[122] F.Gueniat,L.Mathelin,andL.Pastur. Adynamicmodedecompositionapproachfor
largeandarbitrarilysampledsystems. PhysicsofFluids,27(2):025113,2015. (Citedon
p.32)
[123] I.J.Guzmán, D.Sipp,andP.J.Schmid. Adynamicobservertocaptureandcontrol
perturbationenergyinnoiseamplifiers.JournalofFluidMechanics,758:728–753,112014.
(Citedonp.24)
[124] A.Haar. Zurtheoriederorthogonalenfunktionen-systeme. MathematischeAnnalen,
69:331–371,1910.(Citedonp.73)
[125] F.H.HarlowandJ.E.Welch. Numericalcalculationoftime-dependentviscousincom-
pressibleflowoffluidwithfreesurface. PhysicsofFluids, 8(12):2182,1965. (Citedon
p.27)
[126] R.D.F.HarrisandF.Yilmaz.Amomentumtradingstrategybasedonthelowfrequency
componentoftheexchangerate. JournalofBankingandFinance,33:1575–1585,2009.
(Citedonp.196)
[127] C.D.Harvey, P.Coen,andD.W.Tank. Choice-specificsequencesinparietalcortex
duringavirtual-navigationdecisiontask.Nature,484(7392):62–68,2012.(Citedonp.187)
[128] J.He,L.Balzano,andA.Szlam. IncrementalgradientontheGrassmannianforonline
foregroundandbackgroundseparationinsubsampledvideo. In2012IEEEConference
onComputerVisionandPatternRecognition(CVPR),pages1568–1575,2012. (Citedon
p.55)
[129] M. S. Hemati, C. W. Rowley, E. A. Deem, and L. N. Cattafesta. De-biasing the dy-
namic mode decomposition for applied Koopman spectral analysis. arXiv preprint,
arXiv:1502.03854v2,2015. (Citedonpp.119,128,131,132)
[130] M.S.Hemati,M.O.Williams,andC.W.Rowley. Dynamicmodedecompositionfor
largeandstreamingdatasets.PhysicsofFluids,26(11):111701,2014. (Citedonp.70)
[131] AnthonyJGHey,StewartTansley,KristinMicheleTolle,etal. Thefourthparadigm:
data-intensivescientificdiscovery. MicrosoftResearchRedmond,WA,2009. (Citedon
p.ix)

Bibliography 221
[132] B.L.HoandR.E.Kalman. Effectiveconstructionoflinearstate-variablemodelsfrom
input/outputdata. InProceedingsofthe3rdAnnualAllertonConferenceonCircuitand
SystemTheory,pages449–459,1965. (Citedonpp.24,109,139)
[133] P.J.Holmes,J.L.Lumley,G.Berkooz,andC.W.Rowley. Turbulence,CoherentStruc-
tures,DynamicalSystemsandSymmetry. CambridgeMonographsinMechanics.Cam-
bridgeUniversityPress,Cambridge,U.K.,2ndEd.,2012. (Citedonpp.21,25,26,28,
134)
[134] H.Hotelling. Analysisofacomplexofstatisticalvariablesintoprincipalcomponents.
JournalofEducationalPsychology,24:498–520,October1933.(Citedonp.2)
[135] H.Hotelling. Analysisofacomplexofstatisticalvariablesintoprincipalcomponents.
JournalofEducationalPsychology,24:417–441,September1933. (Citedonp.2)
[136] http://www.barrons.com/articles/barrons-2015-ranking-of-online-brokers-
1425705011.(Citedonp.201)
[137] J.-C.Hua,S.Roy,J.L.McCauley,andG.H.Gunaratne. Usingdynamicmodedecom-
positiontoextractcyclicbehaviorinthestockmarket. PhysicaA,448:172–180,2016.
(Citedonpp.196,197)
[138] C.Huang,W.E.Anderson,M.E.Harvazinski,andV.Sankaran.Analysisofself-excited
combustioninstabilitiesusingdecompositiontechniques.In51stAIAAAerospaceSciences
Meeting,pages1–18,2013. (Citedonp.32)
[139] R.Iati. The realstoryof tradingsoftware espionage. AdvancedTrading.com, July10,
2009.(Citedonp.195)
[140] M.IlakandC.W.Rowley. Modelingoftransitionalchannelflowusingbalancedproper
orthogonaldecomposition.PhysicsofFluids,20:034103,2008.(Citedonp.126)
[141] G.V.Iungo,C.Santoni-Ortiz,M.Abkar,F.Porté-Agel,M.A.Rotea,andS.Leonardi.
Data-drivenreducedordermodelforpredictionofwindturbinewakes.JournalofPhysics:
ConferenceSeries,625:012009,2015. (Citedonp.31)
[142] C.P.Jackson. Afinite-elementstudyoftheonsetofvortexsheddinginflowpastvari-
ouslyshapedbodies.JournalofFluidMechanics,182:23–45,1987.(Citedonp.33)
[143] G.James,D.Witten,T.Hastie,andR.Tibshirani.AnIntroductiontoStatisticalLearning.
Springer,2013.(Citedonp.23)
[144] R.A.Jarrow,D.Lando,andS.M.Turnbull. AMarkovmodelforthetermstructureof
creditriskspreads. ReviewofFinancialStudies,10:481–523,1997. (Citedonp.196)
[145] X.JinandB.Huang.IdentificationofswitchedMarkovautoregressiveexogenoussystems
withhiddenswitchingstate.Automatica,48(2):436–441,2012. (Citedonp.114)
[146] W.B.JohnsonandJ.Lindenstrauss. ExtensionsofLipschitzmappingsintoaHilbert
space.ContemporaryMathematics,26(1):189–206.(Citedonp.136)
[147] I.Jolliffe. PrincipalComponentAnalysis. WileyOnlineLibrary,2005. (Citedonpp.2,
29)
[148] I.T.Jolliffe.Anoteontheuseofprincipalcomponentsinregression.JournaloftheRoyal
StatisticalSocietyC,31:300–303,1982. (Citedonp.23)
[149] M.R.Jovanovi´c,P.J.Schmid,andJ.W.Nichols. Sparsity-promotingdynamicmode
decomposition.PhysicsofFluids,26(2):024103,2014.(Citedonpp.32,124,133,137,138)

222 Bibliography
[150] J.N.Juang. AppliedSystemIdentification. PrenticeHallPTR,1994. (Citedonpp.24,
101,109)
[151] J.N.JuangandR.S.Pappa. Aneigensystemrealizationalgorithmformodalparam-
eteridentificationandmodelreduction. Journal ofGuidance, Control, andDynamics,
8(5):620–627,1985.(Citedonpp.23,24,32,93,101,109)
[152] J. N. Juang, M. Phan, L. G. Horta, and R. W. Longman. Identification of Ob-
server/KalmanFilterMarkovParameters: TheoryandExperiments. TechnicalMemoran-
dum104069,NASA,1991. (Citedonpp.24,93,101,110)
[153] R.E.Kalman. Anewapproachtolinearfilteringandpredictionproblems. Journalof
FluidsEngineering,82(1):35–45,1960. (Citedonp.110)
[154] T.Katayama.SubspaceMethodsforSystemIdentification.Springer-Verlag,2005.(Citedon
pp.24,101)
[155] M.Kearns.Thoughtsonhypothesisboosting.Unpublishedmanuscript(machinelearning
classproject,December1988). (Citedonp.21)
[156] M.KearnsandL.Valiant.CryptographiclimitationsonlearningBooleanformulaeand
finiteautomata.SymposiumonTheoryofComputing(ACM),21:433–444,1989.(Citedon
p.21)
[157] M.KeelingandP.Rohani.ModelingInfectiousDiseasesinHumansandAnimals.Princeton
UniversityPress,2008.(Citedonpp.177,179)
[158] M.J.KeelingandB.T.Grenfell. Diseaseextinctionandcommunitysize: Modelingthe
persistenceofmeasles. Science,275(5296):65–67,1997. (Citedonpp.182,183)
[159] W.O. Kermackand A. G. McKendrick. Acontributionto the mathematicaltheory
ofepidemics. ProceedingsoftheRoyalSocietyofLondonA:Mathematical, Physicaland
EngineeringSciences,115(772):700–721,1927.(Citedonp.178)
[160] I.G.KevrekidisandG.Samaey.Equation-freemultiscalecomputation:Algorithmsand
applications.AnnualReviewofPhysicalChemistry,60:321–344,2009. (Citedonp.20)
[161] I.G.Kevrekidis,C.W.Gear,andG.Hummer.Equation-free:Thecomputer-aidedanal-
ysisofcomplexmultiscalesystems. Journal ofNonlinear Science, 50:1346–1355,2004.
(Citedonp.20)
[162] B.O.Koopman.HamiltoniansystemsandtransformationinHilbertspace.Proceedings
oftheNationalAcademyofSciencesoftheUSA,17(5):315–318,1931. (Citedonpp.ix,1,
24,39,43,44,101)
[163] B.O.KoopmanandJ.V.Neumann.Dynamicalsystemsofcontinuousspectra.Proceed-
ingsoftheNationalAcademyofSciencesoftheUSA,18(3):255,1932. (Citedonp.43)
[164] K.Kowalski,W.-H.Steeb,andK.Kowalksi.NonlinearDynamicalSystemsandCarleman
Linearization. WorldScientific,1991. (Citedonp.51)
[165] J.R.Koza,F.H.BennettIII,andO.Stiffelman. GeneticprogrammingasaDarwinian
inventionmachine. InGeneticProgramming,pages93–108.Springer,1999. (Citedon
p.24)
[166] J.N.Kutz. Data-DrivenModelingandScientificComputation: MethodsforComplexSys-
temsandBigData. OxfordUniversityPress,2013. (Citedonpp.14,57,71,78,136)

Bibliography 223
[167] J.N.Kutz,X.Fu,andS.L.Brunton. Multiresolutiondynamicmodedecomposition.
SIAMJournalonAppliedDynamicalSystems,15(2):713–735,2016. (Citedonpp.71,76,
86,197)
[168] J.N.Kutz,J.Grosek,andS.L.Brunton.DynamicmodedecompositionforrobustPCA
with applications to foreground/background subtraction in video streams and multi-
resolutionanalysis. InT.Bouwmans,editor,CRCHandbookonRobustLow-Rankand
Sparse Matrix Decomposition: Applications in Image and Video Processing, CRC Press,
2015.(Citedonp.55)
[169] F.DelaTorreandM.Black. Aframeworkforrobustsubspacelearning. International
JournalofComputerVision,54(1-3):117–142,2003. (Citedonp.56)
[170] Y.LanandI.Mezi´c.LinearizationinthelargeofnonlinearsystemsandKoopmanoper-
atorspectrum. PhysicaD:NonlinearPhenomena,242(1):42–53,2013. (Citedonp.45)
[171] D.Lazer,R.Kennedy,G.King,andA.Vespignani.TheparableofGoogleFlu:Trapsin
bigdataanalysis. Science,343(6176):1203–1205,2014. (Citedonp.182)
[172] D.D.LeeandH.S.Seung.Algorithmsfornon-negativematrixfactorization.InAdvances
inNeuralInformationProcessingSystems,13:556–562,2000.(Citedonp.187)
[173] J.H. Lee, A. Seena, S.Lee, and H.J.Sung. Turbulentboundarylayersover rod-and
cube-roughenedwalls. JournalofTurbulence,13(1),2012. (Citedonp.31)
[174] M.Lee,N.Malaya,andR.D.Moser. Petascaledirectnumericalsimulationofturbulent
channelflowonupto786Kcores. InProceedingsofSC13: InternationalConferencefor
High Performance Computing, Networking, Storage and Analysis, page 61.ACM, 2013.
(Citedonp.27)
[175] L.Li,W.Huang,I.Gu,andQ.Tian. Statisticalmodelingofcomplexbackgroundsfor
foregroundobjectdetection. IEEETransactionsonImageProcessing,13(11):1459–1472,
2004.(Citedonp.55)
[176] Z.Lin,M.Chen,andY.Ma.TheAugmentedLagrangeMultiplierMethodforExactRecov-
eryofCorruptedLow-RankMatrices. TechnicalReport,UniversityofIllinoisatUrbana-
Champaign,2011. (Citedonp.57)
[177] Z.Lin,A.Ganesh,J.Wright,L.Wu,M.Chen,andY.Ma. Fastconvexoptimization
algorithmsforexactrecoveryofacorruptedlow-rankmatrix. ComputationalAdvances
inMulti-SensorAdaptiveProcessing(CAMSAP),61,2009. (Citedonp.57)
[178] L.Ljung.SystemIdentification:TheoryfortheUser.PrenticeHall,1999.(Citedonp.109)
[179] A.W.LoandA.C.MacKinlay.Whenarecontrarianprofitsduetostockmarketoverre-
action? ReviewofFinancialStudies,3:175–206,1990. (Citedonp.196)
[180] R.W.LongmanandJ.-N.Juang.Recursiveformoftheeigensystemrealizationalgorithm
forsystemidentification. Journal ofGuidance, Control, andDynamics, 12(5):647–652,
1989.(Citedonp.114)
[181] E.N.Lorenz. EmpiricalOrthogonalFunctionsandStatisticalWeatherPrediction. Tech-
nicalreport,MassachusettsInstituteofTechnology,December,1956. (Citedonpp.2,
22)
[182] D.M.LuchtenburgandC.W.Rowley. Modelreductionusingsnapshot-basedrealiza-
tions. BulletinoftheAmericanPhysicalSociety,56,2011. (Citedonpp.32,109)

224 Bibliography
[183] F.Lusseyran, F.Gueniat, J. Basley, C. L. Douay, L. R. Pastur, T. M. Faure, and P. J.
Schmid. Flow coherent structures and frequency signature: Application of the dy-
namicmodesdecompositiontoopencavityflow. JournalofPhysics: ConferenceSeries,
318:042036,2011.(Citedonp.31)
[184] Z.Ma,S.Ahuja,andC.W.Rowley. Reducedordermodelsforcontroloffluidsusing
theeigensystemrealizationalgorithm. TheoreticalandComputational FluidDynamics,
25(1):233–247,2011. (Citedonpp.32,101,109)
[185] C.K.Machens,R.Romo,andC.D.Brody. Functional,butnotanatomical,separation
of“what”and“when”inprefrontalcortex. TheJournalofNeuroscience,30(1):350–360,
2010.(Citedonp.187)
[186] A.Mackey,H.Schaeffer,andS.Osher. Onthecompressivespectralmethod. Multiscale
ModelingandSimulation,12(4):1800–1827,2014. (Citedonp.24)
[187] L.MaddalenaandA.Petrosino. Aself-organizingapproachtobackgroundsubtraction
forvisualsurveillanceapplications. IEEETransactionsonImageProcessing,17(7):1168–
1177,2008. (Citedonp.55)
[188] A.Majda. Challengesinclimatescienceandcontemporaryappliedmathematics. Com-
municationsonPureandAppliedMathematics,65:920–948,2012.(Citedonp.21)
[189] J.MannandJ.N.Kutz. Dynamicmodedecompositionforfinancialtradingstrategies.
QuantitativeFinance,2016. (Citedonpp.196,197,202,204,205)
[190] S.Mariappan,R.Sujith,andP.Schmid. Non-normalityofThermoacousticInteractions:
AnExperimentalInvestigation,AIAAPaper2011-5555,AIAA,Reston,VA,2011.(Cited
onp.32)
[191] L.Massa,R.Kumar,andP.Ravindran. Dynamicmodedecompositionanalysisofdeto-
nationwaves. PhysicsofFluids,24(6):066101,2012. (Citedonp.32)
[192] O.MazorandG.Laurent.Transientdynamicsversusfixedpointsinodorrepresentations
by locustantennal lobe projectionneurons. Neuron, 48(4):661–673, 2005. (Cited on
p.187)
[193] T.McConaghy. FFX:Fast,scalable,deterministicsymbolicregressiontechnology. In
GeneticProgrammingTheoryandPracticeIX,pages235–260.Springer,2011. (Citedon
p.24)
[194] I.Mezi´c.Spectralpropertiesofdynamicalsystems,modelreductionanddecompositions.
NonlinearDynamics,41(1-3):309–325,2005. (Citedonpp.ix,1,39)
[195] I.Mezi´c.AnalysisoffluidflowsviaspectralpropertiesoftheKoopmanoperator.Annual
ReviewofFluidMechanics,45:357–378,2013. (Citedonpp.1,6,24,31,39,45,101)
[196] I.Mezi´candA.Banaszuk. Comparisonofsystemswithcomplexbehavior. PhysicaD:
NonlinearPhenomena,197(1-2):101–133,2004. (Citedonpp.ix,1,24,39)
[197] I.Mezi´candS.Wiggins.Amethodforvisualizationofinvariantsetsofdynamicalsystems
basedontheergodicpartition. Chaos: AnInterdisciplinaryJournalofNonlinearScience,
9(1):213–218,1999.(Citedonp.45)
[198] S.Mika,J.Ham,D.D.LeeandB.Schölkopf.Akernelviewofthedimensionalityreduc-
tionofmanifolds. Proceedingsofthe21stInternationalConferenceonMachineLearning,
page47,2004. (Citedonpp.160,170)

Bibliography 225
[199] Y. Mizuno, D. Duke, C. Atkinson, and J. Soria. Investigation of wall-bounded tur-
bulentflowusingdynamicmodedecomposition. JournalofPhysics: ConferenceSeries,
318:042040,2011.(Citedonp.32)
[200] J.P.Moeck,J.-F.Bourgouin,D.Durox,T.Schuller,andS.Candel.Tomographicrecon-
structionofheatreleaserateperturbationsinducedbyhelicalmodesinturbulentswirl
flames.ExperimentsinFluids,54(4):1–17,2013. (Citedonp.32)
[201] B.C.Moore. Principalcomponentanalysisinlinearsystems: Controllability,observ-
ability,andmodelreduction. IEEETransactionsonAutomaticControl,AC-26(1):17–32,
1981.(Citedonpp.24,32,101,109)
[202] T.W.Muld,G.Efraimsson,andD.S.Henningson.Flowstructuresaroundahigh-speed
trainextractedusingproperorthogonaldecompositionanddynamicmodedecomposi-
tion. Computers&Fluids,57:87–97,2012. (Citedonp.32)
[203] T.W.Muld,G.Efraimsson, andD.S.Henningson. Modedecompositiononsurface-
mountedcube. Flow,TurbulenceandCombustion,88(3):279–310,2012. (Citedonp.32)
[204] K.Murphy. MachineLearning. MITPress,2012. (Citedonp.159)
[205] D.NeedellandJ.A.Tropp. CoSaMP:Iterative signalrecoveryfromincompleteand
inaccuratesamples.CommunicationsoftheACM,53(12):93–100,2010.(Citedonpp.136,
149)
[206] M.A.Nicolelis,L.A.Baccala,R.C.Lin,andJ.K.Chapin. Sensorimotorencodingby
synchronousneuralensembleactivityatmultiplelevelsofthe somatosensory system.
Science,268(5215):1353–1358,1995.(Citedonp.187)
[207] B.R.Noack,K.Afanasiev,M.Morzynski, G.Tadmor,andF.Thiele. Ahierarchyof
low-dimensionalmodelsforthetransientandpost-transientcylinderwake. Journalof
FluidMechanics,497:335–363,2003. (Citedonpp.30,33)
[208] B.R.NoackandH.Eckelmann. Aglobalstabilityanalysisofthesteadyandperiodic
cylinderwake. JournalofFluidMechanics,270:297–330,1994. (Citedonp.33)
[209] H.Nyquist.Certaintopicsintelegraphtransmissiontheory.TransactionsoftheAmerican
InstituteofElectricalEngineers,47(2):617–644,1928. (Citedonpp.133,134)
[210] C.M.Ostoich,D.J.Bodony,andP.H.Geubelle. InteractionofaMach2.25turbulent
boundarylayerwithaflutteringpanelusingdirectnumericalsimulation.PhysicsofFluids,
25(11):110806,2013.(Citedonp.32)
[211] V.Ozolin¸š,R.Lai,R.Caflisch,andS.Osher.Compressedmodesforvariationalproblems
inmathematicsandphysics. ProceedingsoftheNationalAcademyofSciencesoftheUSA,
110(46):18368–18373,2013. (Citedonp.24)
[212] C.Pan,D.Yu,andJ.Wang.DynamicalmodedecompositionofGurneyflapwakeflow.
TheoreticalandAppliedMechanicsLetters,1(1):012002,2011. (Citedonp.31)
[213] V.M.PatelandR.Chellappa.SparseRepresentationsandCompressiveSensingforImaging
andVision. BriefsinElectricalandComputerEngineering.Springer,2013. (Citedon
p.139)
[214] K.Pearson. Onlinesandplanesofclosestfittosystemsofpointsinspace.Philosophical
Magazine,2(7–12):559–572,1901.(Citedonpp.2,29)
[215] C.Penland.Randomforcingandforecastingusingprincipaloscillationpatternanalysis.
MonthlyWeatherReview,117:2165–2185,1989.(Citedonp.22)

226 Bibliography
[216] C.PenlandandT.Magorian. PredictionofNiño3sea-surfacetemperaturesusinglinear
inversemodeling. JournalofClimate,6:1067–1076,1993. (Citedonpp.22,23)
[217] S. Petra and C. Schnörr. Tomopiv meets compressed sensing. Pure Mathematics and
Applications,20(1-2):49–76,2009. (Citedonp.140)
[218] M.Phan,L.G.Horta,J.N.Juang,andR.W.Longman. Linearsystemidentification
viaanasymptoticallystableobserver. JournalofOptimizationTheoryandApplications,
79:59–86,1993. (Citedonpp.24,101)
[219] M. Phan, L. G. Horta, J. N. Juang, and R. W. Longman. Improvement of ob-
server/Kalmanfilteridentification(OKID)byresidualwhitening. JournalofVibrations
andAcoustics,117:232–238,1995.(Citedonp.110)
[220] M.Phan,J.N.Juang,andR.W.Longman.Identificationoflinear-multivariablesystems
byidentificationofobserverswithassignedrealeigenvalues.TheJournaloftheAstronau-
ticalSciences,40(2):261–279,1992. (Citedonpp.24,101)
[221] J.L.Proctor, S.L.Brunton, B.W.Brunton, andJ.N. Kutz. Exploitingsparsityand
equation-freearchitecturesin complexsystems. The European Physical Journal Special
Topics,223(13):2665–2684,2014.(Citedonp.24)
[222] J.L.Proctor,S.L.Brunton,andJ.N.Kutz.Dynamicmodedecompositionwithcontrol.
SIAMJournalonAppliedDynamicalSystems,15(1):142–161,2016. (Citedonpp.24,91,
92,93,94,100,101)
[223] J.L.Proctor,S.L.Brunton,andJ.N.Kutz. GeneralizingKoopmantheorytoallowfor
inputsandcontrol.arXivpreprint,arXiv:1602.07647,2016. (Citedonp.101)
[224] J. L. Proctor and P. A. Eckhoff. Discovering dynamic patterns from infectious dis-
easedatausingdynamicmodedecomposition. InternationalHealth,2(7):139–145,2015.
(Citedonpp.177,180,181,182,183)
[225] H.QiandS.M.Hughes. Invarianceofprincipalcomponentsunderlow-dimensional
randomprojectionof the data. IEEE International Conference on Image Processing,
October2012. (Citedonp.136)
[226] S.J.Qin.Anoverviewofsubspaceidentification.ComputersandChemicalEngineering,
30(10–12):1502–1513,2006.PapersfromChemicalProcessControl{VIICPC}{VIISev-
enth}internationalconferenceintheSeries.(Citedonpp.24,101)
[227] M.Quade,M.Abel,K.Shafi,R.K.Niven,andB.R.Noack. Predictionofdynamical
systemsbysymbolicregression.arXivpreprint,arXiv:1602.04648,2016.(Citedonp.24)
[228] A.QuarteroniandG.Rozza. ReducedOrderMethodsforModelingandComputational
Reduction. Springer,2013. (Citedonp.20)
[229] L.R.Rabiner. AtutorialonhiddenMarkovmodelsandselectedapplicationsinspeech
recognition. ProceedingsoftheIEEE,77(2):257–286,1989. (Citedonp.113)
[230] L.R.RabinerandB.-H.Juang. AnintroductiontohiddenMarkovmodels.ASSPMaga-
zine,IEEE,3(1):4–16,1986. (Citedonp.113)
[231] M.RathinamandL.R.Petzold.Anewlookatproperorthogonaldecomposition.SIAM
JournalonNumericalAnalysis,41(5):1893–1925,2003. (Citedonp.31)
[232] J.A.Riffell,H.Lei,andJ.G.Hildebrand. Neuralcorrelatesofbehaviorinthemoth
Manducasexta inresponse to complexodors. Proceedingsof theNational Academyof
SciencesoftheUSA,106(46):19219–19226,2009. (Citedonp.187)

Bibliography 227
[233] C.W.Rowley. Modelreductionforfluidsusingbalancedproperorthogonaldecompo-
sition. InternationalJournalofBifurcationandChaos,15(3):997–1013,2005. (Citedon
pp.32,101,109,126)
[234] C.W.RowleyandJ.E.Marsden. ReconstructionequationsandtheKarhunen–Loéve
expansionforsystemswithsymmetry.PhysicaD:NonlinearPhenomena,142:1–19,2000.
(Citedonp.87)
[235] C.W.Rowley,I.Mezi´c,S.Bagheri,P.Schlatter,andD.S.Henningson. Spectralanalysis
ofnonlinearflows. JournalofFluidMechanics,645:115–127,2009. (Citedonpp.ix,1,2,
6,24,25,31,39,47,50,101,124)
[236] C.W.Rowley,D.R.Williams,T.Colonius,R.M.Murray,andD.G.Macmynowski.
Linearmodelsforcontrolofcavityflowoscillations.JournalofFluidMechanics,547:317–
330,2006. (Citedonp.126)
[237] C.W.Rowley,M.O.Williams,andI.G.Kevrekidis.Dynamicmodedecompositionand
theKoopmanoperator:Algorithmsandapplications.InIPAM,UCLA,2014. (Citedon
p.47)
[238] C.W.RowleyandD.R.Williams.Dynamicsandcontrolofhigh-Reynoldsnumberflows
overopencavities.AnnualReviewofFluidMechanics,38:251–276,2006.(Citedonp.126)
[239] S.Roy, J.-C. Hua, W.Barnhill, G.H. Gunaratne, andJ.R.Gord. Deconvolutionof
reacting-flow dynamics using proper orthogonal and dynamic mode decompositions.
PhysicalReviewE,91(1):013001,2015.(Citedonp.32)
[240] A.C.Sankaranarayanan,P.K.Turaga,R.G.Baraniuk,andR.Chellappa. Compressive
acquisitionofdynamicscenes. InComputerVision–ECCV,pages129–142,2010. (Cited
onp.139)
[241] N.Sarantis. Ontheshort-termpredictabilityofexchangerates: ABVARtime-varying
parametersapproach. JournalofBankingandFinance, 2006:2257–2279,30. (Citedon
p.196)
[242] S.Sargsyan,S.L.Brunton,andJ.N.Kutz.Nonlinearmodelreductionfordynamicalsys-
temsusingsparsesensorlocationsfromlearnedlibraries. PhysicalReviewE,92:033304,
2015.(Citedonp.21)
[243] S.Sarkar,S.Ganguly,A.Dalal,P.Saha,andS.Chakraborty.Mixedconvectiveflowstabil-
ityofnanofluidspastasquarecylinderbydynamicmodedecomposition. International
JournalofHeatandFluidFlow,44:624–634,2013. (Citedonp.32)
[244] T.Sayadi,P.J.Schmid,J.W.Nichols, andP. Moin. Reduced-orderrepresentationof
near-wallstructuresinthelatetransitionalboundarylayer. JournalofFluidMechanics,
748:278–301,2014. (Citedonp.32)
[245] H.Schaeffer,R.Caflisch,C.D.Hauck,andS.Osher. Sparsedynamicsforpartialdiffer-
entialequations.ProceedingsoftheNationalAcademyofSciencesoftheUSA,110(17):6634–
6639,2013. (Citedonpp.24,134)
[246] R.Schapire. The strength ofweaklearnability. MachineLearning, 5:1997–227,1990.
(Citedonp.21)
[247] P.J.Schmid.Dynamicmodedecompositionofnumericalandexperimentaldata.Journal
ofFluidMechanics,656:5–28,August2010.(Citedonpp.ix,1,2,5,8,10,25,31,100,101,
125,138)

228 Bibliography
[248] P.J.Schmid. Applicationofthe dynamicmodedecompositionto experimentaldata.
ExperimentsinFluids,50:1123–1130,2011. (Citedonp.31)
[249] P.J.Schmid,L.Li,M.P.Juniper,andO.Pust.Applicationsofthedynamicmodedecom-
position. TheoreticalandComputationalFluidDynamics,25(1-4):249–259,2011. (Cited
onpp.31,32)
[250] P.J.SchmidandJ.Sesterhenn. Dynamicmodedecompositionofnumericalandexper-
imentaldata. In61stAnnualMeetingoftheAPSDivisionofFluidDynamics.American
PhysicalSociety,November2008.(Citedonpp.ix,1,101)
[251] P.J.Schmid,D.Violato,andF.Scarano. Decompositionoftime-resolvedtomographic
PIV. ExperimentsinFluids,52:1567–1579,2012. (Citedonpp.31,32)
[252] M.SchmidtandH.Lipson. Distillingfree-formnaturallawsfromexperimentaldata.
Science,324(5923):81–85,2009. (Citedonpp.24,45)
[253] A.SeenaandH.J.Sung. Dynamicmodedecompositionofturbulentcavityflowsfor
self-sustainedoscillations.InternationalJournalofHeatandFluidFlow,32(6):1098–1110,
2011.(Citedonp.31)
[254] O.Semeraro,G.Bellani,andF.Lundell. Analysisoftime-resolvedPIVmeasurements
of a confined turbulent jet using POD and Koopman modes. Experiments in Fluids,
53(5):1203–1220,2012. (Citedonp.31)
[255] C.E.Shannon.Amathematicaltheoryofcommunication.BellSystemTechnicalJournal,
27(3):379–423,1948. (Citedonpp.133,134)
[256] P.Shen.Markettimingstrategiesthatworked.JournalofPortfolioManagement,29:57–68,
2003.(Citedonp.196)
[257] J. V. Shi, W. Yin, A. C. Sankaranarayanan, and R. G. Baraniuk. Video compressive
sensingfordynamicMRI. BMCNeuroscience,13:183,2012. (Citedonpp.139,140)
[258] T.C.ShikandT.T.-L.Chong.AcomparisonofMAandRSIreturnswithexchangerate
intervention. AppliedEconomicsLetters,14:371–383,2007. (Citedonp.196)
[259] A.Shiryaeva,Z.Xu,andX.Y.Zhoubc.Thoushaltbuyandhold.QuantitativeFinance,
8:765–776,2008.(Citedonp.196)
[260] S.Sirisup,G.E.Karniadakis,D.Xiu,andI.G.Kevrekidis.Equation-free/Galerkin-free
POD-assistedcomputationofincompressibleflows. Journal ofComputational Physics,
207:568–587,2005. (Citedonpp.20,21)
[261] L.Sirovich. Turbulenceandthedynamicsofcoherentstructures,partsI–III. Quarterly
ofAppliedMathematics,XLV(3):561–590,1987. (Citedonpp.26,29)
[262] L.SirovichandM.Kirby. Alow-dimensionalprocedureforthecharacterizationofhu-
manfaces. Journal of theOptical Societyof AmericaA,4(3):519–524,1987. (Citedon
pp.29,166)
[263] A.SmithandE.N.Brown. Estimatingastate-spacemodelfrompointprocessobserva-
tions. NeuralComputation,15(5):965–991,2003.(Citedonp.188)
[264] G.Song,F.Alizard,J.-C.Robinet,andX.Gloerfelt. GlobalandKoopmanmodesanal-
ysisofsoundgenerationinmixinglayers. PhysicsofFluids,25(12):124101,2013. (Cited
onp.32)
[265] O.Sporns,G.Tononi,andR.Kötter.Thehumanconnectome:Astructuraldescription
ofthehumanbrain. PLoSComputationalBiology,1(4):e42,2005. (Citedonp.185)

Bibliography 229
[266] I.Stakgold.BoundaryValueProblemsofMathematicalPhysics,Volume1.SIAM,corrected
reprintofthe1967edition,2000. (Citedonp.39)
[267] W.-H.SteebandF.Wilhelm. Non-linearautonomoussystemsofdifferentialequations
andCarlemanlinearizationprocedure.JournalofMathematicalAnalysisandApplications,
77(2):601–611,1980.(Citedonp.51)
[268] F.StrozziaandJ.-M.Z.Comenges. Towardsanon-lineartradingstrategyforfinancial
timeseries.Chaos,SolitonsandFractals,28:601–615,2006. (Citedonp.196)
[269] G.Sugihara,R.May,H.Ye,C.-H.Hsieh,E.Deyle,M.Fogarty,andS.Munch.Detecting
causalityincomplexecosystems.Science,338(6106):496–500,2012.(Citedonpp.24,110)
[270] S.A.Svoronos,D.Papageorgiou,andC.Tsiligiannis.Discretizationofnonlinearcontrol
systemsviatheCarlemanlinearization.ChemicalEngineeringScience,49(19):3263–3267,
1994.(Citedonp.51)
[271] B.SchölkopfT.HofmannandA.Smola. Kernelmethodsinmachinelearning. Annals
ofStatistics,36:1171–1220,2008. (Citedonpp.160,170)
[272] K.Tairaand T.Colonius. The immersedboundary method: Aprojectionapproach.
JournalofComputationalPhysics,225(2):2118–2137,2007. (Citedonp.33)
[273] F. Takens. Detecting strange attractors in turbulence. Lecture Notes in Mathematics,
898:366–381,1981. (Citedonp.110)
[274] P.TallapragadaandS.D.Ross. Asetorienteddefinitionoffinite-timeLyapunovexpo-
nentsandcoherentsets.CommunicationsinNonlinearScienceandNumericalSimulation,
18(5):1106–1126,May2013. (Citedonpp.33,45)
[275] Z.Q.TangandN.Jiang.Dynamicmodedecompositionofhairpinvorticesgeneratedby
ahemisphereprotuberance. ScienceChinaPhysics,MechanicsandAstronomy,55(1):118–
124,2012. (Citedonp.32)
[276] C.Tapiero. RiskandFinancialManagement: MathematicalandComputationalMethods.
Wiley,2004. (Citedonp.196)
[277] A.B.Tayler,D.J.Holland,A.J.Sederman,andL.F.Gladden.Exploringtheoriginsof
turbulenceinmultiphaseflowusingcompressedsensingMRI. PhysicalReviewLetters,
108(26):264505-1–264505-5,2012. (Citedonp.140)
[278] C.G.Thomas, R.A.Harshman, andR. S.Menon. NoisereductioninBOLD-based
fMRIusingcomponentanalysis.NeuroImage,17(3):1521–1537,2002. (Citedonp.187)
[279] Y.Tian,M.Lu,andA.Hampapur.Robustandefficientforegroundanalysisforreal-time
videosurveillance.InIEEEComputerSocietyConferenceonComputerVisionandPattern
Recognition,2005,volume1,pages1182–1187,2005. (Citedonp.55)
[280] R. Tibshirani. Regression shrinkage and selectionvia the lasso. Journal of the Royal
StatisticalSocietyB,pages267–288,1996. (Citedonpp.21,24)
[281] TheNewYorkTimes. Timestopics:High-frequencytrading. AdvancedTrading.com,De-
cember20,2012. (Citedonp.195)
[282] G.Tissot,L.Cordier,N.Benard,andB.R.Noack.Modelreductionusingdynamicmode
decomposition.ComptesRendusMécanique,2014. (Citedonp.32)
[283] L.N.TrefethenandD.Bau,III. NumericalLinearAlgebra. SIAM,Philadelphia,1997.
(Citedonp.7)

230 Bibliography
[284] J.A.Tropp. Greedisgood: Algorithmicresultsforsparseapproximation. IEEETrans-
actionsonInformationTheory,50(10):2231–2242,2004.(Citedonp.136)
[285] J.A.Tropp. Justrelax: Convexprogrammingmethodsforidentifyingsparsesignalsin
noise.IEEETransactionsonInformationTheory,52(3):1030–1051,2006.(Citedonp.136)
[286] J.A.Tropp, J.N.Laska, M.F.Duarte, J.K.Romberg, andR.G.Baraniuk. Beyond
Nyquist:Efficientsamplingofsparsebandlimitedsignals.IEEETransactionsonInforma-
tionTheory,56(1):520–544,2010. (Citedonp.136)
[287] J.H.TuandC.W.Rowley. AnimprovedalgorithmforbalancedPODthroughanana-
lytictreatmentofimpulseresponsetails.JournalofComputationalPhysics,231(16):5317–
5333,2012. (Citedonp.32)
[288] J.H.Tu,C.W.Rowley,E.Aram,andR.Mittal.Koopmanspectralanalysisofseparated
flowoverafinite-thicknessflatplatewithellipticalleadingedge.AIAAPaper2011,2864,
2011.(Citedonp.31)
[289] J.H.Tu,C.W.Rowley,J.N.Kutz,andJ.K.Shang.Spectralanalysisoffluidflowsusing
sub-NyquistratePIVdata. ExperimentsinFluids,55(9):1–13,2014. (Citedonpp.5,32,
134,139,140)
[290] J.H.Tu,C.W.Rowley,D.M.Luchtenburg,S.L.Brunton,andJ.N.Kutz.Ondynamic
mode decomposition: Theory and applications. Journal of Computational Dynamics,
1(2):391–421,2014. (Citedonpp.5,7,8,22,23,32,46,47,51,100,101,105,106,109,
110,125)
[291] S.VanHuffelandJ.Vandewalle.TheTotalLeastSquaresProblem:ComputationalAspects
andAnalysis,volume9. SIAM,1991.(Citedonp.131)
[292] P.VanOverscheeandB.DeMoor.N4SID:Subspacealgorithmsfortheidentificationof
combineddeterministic-stochasticsystems. Automatica,30(1):75–93,1994. Specialissue
onstatisticalsignalprocessingandcontrol.(Citedonpp.24,101)
[293] P.VanOverscheeandB.DeMoor. SubspaceIdentificationforLinearSystems: Theory-
Implementation—Applications. Springer,1996. (Citedonpp.24,101)
[294] M.Vidyasagar. ThecompleterealizationproblemforhiddenMarkovmodels:Asurvey
andsomenewresults.MathematicsofControl,Signals,andSystems,23:1–65,2011.(Cited
onp.114)
[295] W. X. Wang, R. Yang, Y. C. Lai, V. Kovanis, and C. Grebogi. Predicting catastro-
phesinnonlineardynamicalsystemsbycompressivesensing. PhysicalReviewLetters,
106:154101–1–154101–4,2011. (Citedonpp.24,45)
[296] W.W.-S.Wei. TimeSeriesAnalysis. Addison-Wesley,1994. (Citedonp.114)
[297] G.WelchandG.Bishop. AnIntroductiontotheKalmanFilter,TechnicalReport,Uni-
versityofNorthCarolinaatChapelHill,1995.(Citedonp.110)
[298] K.Willcox. Unsteadyflowsensingandestimationviathegappyproperorthogonalde-
composition.ComputersandFluids,35:208–226,2006. (Citedonp.21)
[299] K.WillcoxandJ.Peraire. Balancedmodelreductionviatheproperorthogonaldecom-
position. AIAAJournal,40(11):2323–2330,2002.(Citedonpp.32,109)
[300] M.O.Williams,P.J.Schmid,andJ.N.Kutz. Hybridreduced-orderintegrationwith
properorthogonaldecompositionanddynamicmodedecomposition. MultiscaleModel-
ingandSimulation,11(2):522–544,2013.(Citedonpp.21,32)

Bibliography 231
[301] M.O.Williams,I.G.Kevrekidis,andC.W.Rowley. Adata-drivenapproximationof
theKoopmanoperator:Extendingdynamicmodedecomposition. JournalofNonlinear
Science,25:1307–1346,2015.(Citedonpp.46,47,166,167)
[302] M.O.Williams,C.W.Rowley,andI.G.Kevrekidis. Akernelapproachtodata-driven
Koopmanspectralanalysis. arXivpreprint, arXiv:1411.2260,2014. (Citedonpp.166,
167)
[303] M.O.Williams,I.I.Rypina,andC.W.Rowley. Identifyingfinite-timecoherentsets
fromlimitedquantitiesofLagrangiandata.Chaos,25:087408,2015.(Citedonpp.33,45)
[304] D.M.WittenandR.Tibshirani. PenalizedclassificationusingFisher’slineardiscrimi-
nant. JournaloftheRoyalStatisticalSociety: SeriesB(StatisticalMethodology),73(5):753–
772,2011. (Citedonp.21)
[305] G.WoodwardandH.Anderson.Doesbetareacttomarketconditions?Estimatesofbull
andbearbetasusinganonlinearmarketmodelwithanendogenousthresholdparameter.
QuantitativeFinance,9:913–924,2009. (Citedonp.196)
[306] A. Wynn, D. S. Pearson, B. Ganapathisubramani, and P. J. Goulart. Optimal mode
decompositionforunsteadyflows.JournalofFluidMechanics,733:473–503,2013.(Cited
onp.32)
[307] H.Ye,R.J.Beamish, S.M.Glaser,S.C.H.Grant, C.-H.Hsieh, L.J.Richards,J.T.
Schnute,andG.Sugihara. Equation-freemechanisticecosystemforecastingusingem-
piricaldynamicmodeling. ProceedingsoftheNational AcademyofSciencesoftheUSA,
112(13):E1569–E1576,2015.(Citedonpp.24,110)
[308] Y.YehandH.Z.Cummins. LocalizedfluidflowmeasurementswithanHe–Nelaser
spectrometer.AppliedPhysicsLetters,4(10):176–178,1964. (Citedonp.27)
[309] B. Yildirim, C. Chryssostomidis, and G. E. Karniadakis. Efficient sensor placement
foroceanmeasurementsusinglow-dimensionalconcepts. OceanModelling,27:160–173,
2009.(Citedonp.21)
[310] B.M.Yu,A.Afshar,G.Santhanam,S.I.Ryu,andK.V.Shenoy. Extractingdynamical
structureembeddedinneuralactivity.AdvancesinNeuralInformationProcessingSystems,
18:1545–1552,2005. (Citedonp.188)
[311] B. M.Yu, J.P. Cunningham, G.Santhanam, S. I.Ryu, K.V.Shenoy, andM. Sahani.
Gaussian-processfactoranalysisforlow-dimensionalsingle-trialanalysisofneuralpopu-
lationactivity. AdvancesinNeuralInformationProcessingSystems,21:1881–1888,2008.
(Citedonpp.187,188)
[312] A.G.Zawadowski,G.Andor,andJ.Kertész. Short-termmarketreactionafterextreme
pricechangesofliquidstocks. QuantitativeFinance,6:283–295,2006. (Citedonp.196)
[313] Z.Zebib.Stabilityofviscousflowpastacircularcylinder.JournalofEngineeringMathe-
matics,21:155–165,1987. (Citedonp.33)

Index
actionpotential,185 eigensystemrealization Koopmaneigenvalues,45,46,
| adjoint,27,28,32,40–43,45,   | algorithm(ERA),23,24,         | 48,164,166               |
| ---------------------------- | ----------------------------- | ------------------------ |
| 101                          | 101,105,109–112,139           | Koopmanmode,44–46,102,   |
| algorithmictrading,195,196   | eigenvalue,8,40,42,44         | 160,167                  |
| Arnoldialgorithm,10          | ElNiño,85–87                  | Koopmanspectra,31,39,48, |
|                              | empiricalorthogonalfunctions, | 100,101                  |
| backgroundsubtraction,58,70, | 2,22                          | Koopmantheory,6,7,39,41, |
|                              | epidemiology,9,100,178        | 43–45,47–49,51,163,      |
75,89
174
balancedproperorthogonal
|     | featurespace,160,166,167, | Krylovsubspace,10 |
| --- | ------------------------- | ----------------- |
decomposition,32,101,
169,170,172
109
|     | financialtrading,195–197,202 | manifold,20,43,51,52,101, |
| --- | ---------------------------- | ------------------------- |
|     | flowaroundacylinder,25,33,   | 159                       |
coherentstructures,1,25,26,
|                       | 35,125,127,139,148          | manifoldlearning,159          |
| --------------------- | --------------------------- | ----------------------------- |
| 126                   | fluiddynamics,1,9,25,27,31, | Moore–Penrosepseudoinverse,   |
| composition,7,44      | 32,101,133,139,179          | 5                             |
| compressedsensing,21, | fMRI,187                    | motherwavelet,73              |
| 133–136,138–142       |                             | multiresolutionanalysis,72,87 |
Fouriertransform,2,71–75,78,
computervision,1,55,56
100,119,120,140,141,
continuouswavelettransform 143,144,161,191 Navier–Stokesequation,25,27,
| (CWT),74 |     | 29,30,33 |
| -------- | --- | -------- |
control,23,32,91–93,95,96, Gábortransform,71,72 neuron,185–187
98,100,101,109,110, Galerkinprojection,29,30 neuroscience,9,19,187
| 117,184 |     | noise,9,67,80,105,120,121, |
| ------- | --- | -------------------------- |
Hankelmatrices,109–113,120,
| controltheory,3,134 |                         | 126–129,136,143–145, |
| ------------------- | ----------------------- | -------------------- |
|                     | 139                     | 187,188              |
|                     | hiddenMarkovmodels,105, | nonlinearSchrödinger |
delaycoordinates,9,24,105,
|     | 113–115,117 | equation,161,163,172 |
| --- | ----------- | -------------------- |
108,110–112,121,189
|     | Hilbertspace,6,7,39,42,43, | Nyquist,133,134,136,137, |
| --- | -------------------------- | ------------------------ |
diagnostics,2
101
| dynamicalsystem,1–4,6–8,18, |     | 139,140 |
| --------------------------- | --- | ------- |
19,21–25,29,30,37,39,
|     | independentcomponent | observables,44–50,159,160, |
| --- | -------------------- | -------------------------- |
41,43–49,51,52,56,78,
|     | analysis,11 | 162–166,169,170, |
| --- | ----------- | ---------------- |
80,87,91,97–102,128,
|     | infectiousdisease,91,92,100, | 172–174 |
| --- | ---------------------------- | ------- |
130,133,138,143,144,
177–181,184
159,160,167,174,180,
particleimagevelocimetry
| 187,188,196                  | Karhunen–Loeve,2           | (PIV),27,31,133,139,         |
| ---------------------------- | -------------------------- | ---------------------------- |
|                              | kernelmethods,160,166,167, | 140                          |
| EEG,187                      | 169,170                    | Perron–Frobeniusoperator,33, |
| eigendecomposition,4,6–8,23, | Koopmaneigenfunction,44,   | 45                           |
29,79,80,94,95,102 45,50,102,160,164,166, polynomialkernel,170,171,
| eigenfunctions,8,39 | 167 | 174 |
| ------------------- | --- | --- |
233

234 Index
powerspectrum,119–124,137, robustprincipalcomponent stockmarket,195–197,199,200
| 190,192                     | analysis,55 | supportvectormachine,160,     |
| --------------------------- | ----------- | ----------------------------- |
| principalcomponentanalysis, |             | 170                           |
| 2,11,23,29,135              |             | systemidentification,5,24,32, |
samplingrate,78,133,136,139
| principalcomponentpursuit, |     | 93,100,101 |
| -------------------------- | --- | ---------- |
Shannon–Nyquist,134,136,
56,57
137,139
| properorthogonal |     | thresholding,7,63,69,126 |
| ---------------- | --- | ------------------------ |
shift-stacking,105,108
| decomposition,2,6, |     | time-frequencyanalysis,72,74 |
| ------------------ | --- | ---------------------------- |
sigmoidkernel,171
truncation,7,15,17,24,32,48,
25–32,119,135
|     | singularvaluedecomposition, | 66,80,93–96,109,110, |
| --- | --------------------------- | -------------------- |
pseudoinverse,5,7,8,11,125,
|     | 2,7,14–17,20,26,28,29, | 119,121,126,127 |
| --- | ---------------------- | --------------- |
167–169
35,55,77–80,87–89,93,
95,96,98,119,121,126,
uncertaintyquantification,21,
| radialbasisfunctions,160,171, | 127,131,135,136,142, |     |
| ----------------------------- | -------------------- | --- |
27,33,45
| 174 | 143,148,166,167,169, |     |
| --- | -------------------- | --- |
unitary,135,139,140,142,143
| reduced-ordermodeling,5,24, | 170,197,204   |                    |
| --------------------------- | ------------- | ------------------ |
| 32,101                      | SIRmodels,179 | vaccination,92,100 |
regression,2,5,6,8,21,23,24, sparsity,24,66,124,133,134, videosurveillance,55,56,63
| 128,131 | 136–140,143,145,149 |     |
| ------- | ------------------- | --- |
volatility,195
| restrictedisometryproperty, | stateprediction,1,2,4,8, |                       |
| --------------------------- | ------------------------ | --------------------- |
| 135,140,142,143             | 19–21,32,48,166          | wavelets,73–75,78,135 |

Data-driven dynamical systems is a burgeoning field—it connects how measurements of nonlinear
dynamical systems and/or complex systems can be used with well-established methods in
dynamical systems theory. This is a critically important new direction because the governing
equations of many problems under consideration by practitioners in various scientific fields are
not typically known. Thus, using data alone to help derive, in an optimal sense, the best dynamical
system representation of a given application allows for important new insights. The recently
developed dynamic mode decomposition (DMD) is an innovative tool for integrating data with
dynamical systems theory. The DMD has deep connections with traditional dynamical systems
theory and many recent innovations in compressed sensing and machine learning.
Dynamic Mode Decomposition: Data-Driven Modeling of Complex Systems, the first book to address
the DMD algorithm,
• presents a pedagogical and comprehensive approach to all aspects of DMD currently
developed or under development;
• blends theoretical development, example codes, and applications to showcase the theory and
its many innovations and uses;
• highlights the numerous innovations around the DMD algorithm and demonstrates its
efficacy using example problems from engineering and the physical and biological sciences;
and
• provides extensive MATLAB code, data for intuitive examples of key methods, and graphical
presentations.
The core audience for this book is engineers and applied mathematicians working in the physical
and biological sciences. It can be used in courses that integrate data analysis with dynamical
systems.
J. Nathan Kutz is the Robert Bolles and Yasuko Endo Professor of Applied Mathematics, Adjunct
Professor of Physics and Electrical Engineering, and Senior Data Science Fellow with the eScience
Institute at the University of Washington, Seattle.
Steven L. Brunton is an Assistant Professor of Mechanical Engineering, Adjunct Assistant Professor
of Applied Mathematics, and a Data Science Fellow with the eScience Institute at the University of
Washington, Seattle.
Bingni W. Brunton is the Washington Research Foundation Innovation Assistant Professor of
Biology and a Data Science Fellow with the eScience Institute at the University of Washington,
Seattle.
Joshua L. Proctor is an Associate Principal Investigator with the Institute for Disease Modeling as
well as Affiliate Assistant Professor of Applied Mathematics and Mechanical Engineering at the
University of Washington, Seattle.
For more information about SIAM books, journals,
conferences, memberships, or activities, contact:
Society for Industrial and Applied Mathematics
3600 Market Street, 6th Floor
Philadelphia, PA 19104-2688 USA
+1-215-382-9800 • Fax +1-215-386-7999
siam@siam.org • www.siam.org
OT149
ISBN 978-1-611974-49-2
90000
9781611974492
OT149
Dynamic
Mode
Decomposition
Data-Driven Modeling of Complex Systems
Bingni
W.
Brunton
•
Joshua
L.
Proctor
J.
Nathan
Kutz
•
Steven
L.
Brunton
J. Nathan Kutz
Steven L. Brunton
Bingni W. Brunton
Joshua L. Proctor
Data-Driven
Modeling
of
Complex
Systems
Dynamic
Mode
Decomposition
OT149_Kutz_cover-09-28-16.indd 1 9/28/2016 11:14:18 AM