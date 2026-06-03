Advanced Textbooks in Control and Signal
Processing
Editors
M.J.Grimble
M.A.Johnson
Glasgow,UK
Forfurthervolumes:
www.springer.com/series/4045

(cid:2) (cid:2)
| Da-Wei | Gu Petko        | H. Petkov |
| ------ | --------------- | --------- |
| Mihail | M. Konstantinov |           |
| Robust | Control         |           |
| Design | with            |           |
®
MATLAB
| Second | Edition |     |
| ------ | ------- | --- |

Da-WeiGu MihailM.Konstantinov
DepartmentofEngineering CivilEngineeringandGeodesy
UniversityofLeicester UniversityofArchitecture
Leicester,UK Sofia,Bulgaria
PetkoH.Petkov
DepartmentofAutomatics
TechnicalUniversityofSofia
Sofia,Bulgaria
Additionalmaterialtothisbookcanbedownloadedfromhttp://extras.springer.com.
ISSN1439-2232 AdvancedTextbooksinControlandSignalProcessing
ISBN978-1-4471-4681-0 ISBN978-1-4471-4682-7(eBook)
DOI10.1007/978-1-4471-4682-7
SpringerLondonHeidelbergNewYorkDordrecht
LibraryofCongressControlNumber:2013938042
©Springer-VerlagLondon2005,2013
Thisworkissubjecttocopyright.AllrightsarereservedbythePublisher,whetherthewholeorpartof
thematerialisconcerned,specificallytherightsoftranslation,reprinting,reuseofillustrations,recitation,
broadcasting,reproductiononmicrofilmsorinanyotherphysicalway,andtransmissionorinformation
storageandretrieval,electronicadaptation,computersoftware,orbysimilarordissimilarmethodology
nowknownorhereafterdeveloped.Exemptedfromthislegalreservationarebriefexcerptsinconnection
with reviews or scholarly analysis or material supplied specifically for the purpose of being entered
and executed on a computer system, for exclusive use by the purchaser of the work. Duplication of
this publication or parts thereof is permitted only under the provisions of the Copyright Law of the
Publisher’slocation,initscurrentversion,andpermissionforusemustalwaysbeobtainedfromSpringer.
PermissionsforusemaybeobtainedthroughRightsLinkattheCopyrightClearanceCenter.Violations
areliabletoprosecutionundertherespectiveCopyrightLaw.
Theuseofgeneraldescriptivenames,registerednames,trademarks,servicemarks,etc.inthispublication
doesnotimply,evenintheabsenceofaspecificstatement,thatsuchnamesareexemptfromtherelevant
protectivelawsandregulationsandthereforefreeforgeneraluse.
Whiletheadviceandinformationinthisbookarebelievedtobetrueandaccurateatthedateofpub-
lication,neithertheauthorsnortheeditorsnorthepublishercanacceptanylegalresponsibilityforany
errorsoromissionsthatmaybemade.Thepublishermakesnowarranty,expressorimplied,withrespect
tothematerialcontainedherein.
Printedonacid-freepaper
SpringerispartofSpringerScience+BusinessMedia(www.springer.com)

To ourfamilies

Series Editors’ Foreword
The topics of control engineering and signal processing continue to flourish and
develop.Incommonwithgeneralscientificinvestigation,newideas,concepts,and
interpretationsemergequitespontaneouslyandthesearethendiscussed,used,dis-
cardedorsubsumedintotheprevailingsubjectparadigm.Sometimestheseinnova-
tiveconceptscoalesceintoanewsub-disciplinewithinthebroadsubjecttapestryof
controlandsignalprocessing.Thispreliminarybattlebetweenoldandnewusually
takesplaceatconferences,throughtheInternetandinthejournalsofthediscipline.
After a little more maturity has been acquired by the new concepts then archival
publicationasascientificorengineeringmonographmayoccur.
A new conceptin control and signal processing is known to havearrived when
sufficient material has evolved for the topic to be taught as a specialized tutorial
workshop or as a course to undergraduate, graduate or industrial engineers. Ad-
vancedTextbooksinControlandSignalProcessingaredesignedasavehicleforthe
systematic presentation of course material for both popular and innovative topics
inthediscipline.Itishopedthatprospectiveauthorswillwelcometheopportunity
topublishastructuredandsystematicpresentationofsomeoftheneweremerging
controlandsignalprocessingtechnologiesinthetextbookseries.
It is always interesting to look back and review how a particular control sys-
temstheorydeveloped.Intimationsofparadigmchangeoftenseemtobeassociated
with short sharp papers that make the academic community think again about the
prevailingtheoreticalorthodoxy;soitwaswithrobustcontroltheoryinwhichthe
conferencepapersofGeorgeZamesandcolleagues(circa1980)andtheshortpaper
ofDoyleontherobustnessofcontrolsystemsusingtheverypopularlinearquadratic
Gaussian design method now stand as landmark contributions that initiated a new
controldesignparadigm.Allthroughthe1980scameasteadystreamofpapersthat
begantochangetheverylanguageofcontrolitselfwithtermslikerobustness,sys-
tem uncertainty, H ∞ control design and μ synthesis entering the control lexicon.
ThisevolutionarydevelopmentwasvividlycapturedbyProfessorChristosG.Cas-
sandraswritingintheIEEEControlSystemsMagazine(Vol.32,No.3,pp.10–13,
2012) in a short informal study article on papers submitted to the premier control
theoryconference,theCDC;hewrote“Theterm“robust”appearsinzerotitlesor
vii

viii SeriesEditors’Foreword
abstracts in 1971 before showing up in 13–14 % of papers in 1991 and 2001”. In
fact in 1981, the proportion was just 3.4 %, and this was around the time that the
academiccommunitywasbeginningtotakenotethatchangewasathand.
Throughout the 1960s and 1970sthe formalism of state space and the methods
ofoptimalcontrolwereintheascendantforsystemmodelingandacademiccontrol
systemdesign.Onefeatureofthisframeworkisthatitisabletoprovidesolutions
for multivariable system problems. However, it was found that despite clever use
ofadvancedmatrixanalysisandcomputer-aideddesignpackages,classicalcontrol
frequency domain techniques did not easily generalize to multivariable systems; a
missing part of the control systems toolbox was really successful frequency do-
main design methods for multivariable systems. Thus, from the 1980s onward the
tools of robust control for multivariable systems were developed and refined, and
MATLAB®routinesweredevelopedtofacilitatetheimplementationofthenewde-
signmethods.Asbefitsa“unified”theory,onenicefeatureofthenewrobustcon-
trolmethodsisthatitsubsumestheterminologyofclassicalcontrolintothegeneral
framework. With this developmentof the robust control paradigm, the publication
ofthebookRobustControlDesignwithMATLAB®byDa-WeiGu,PetkoH.Petkov,
andMihailKonstantinovintheAdvancedTextbooksinControlandSignalProcess-
ingseriesin2005wasverytimelyandthebookwasconsideredtobeanexcellent
additiontothisseriesofadvancedcontroltextbooks.
With the benefit of hindsight, with the perspective of seven more years of con-
solidationinrobustcontroltheoryandpractice,andwithanewMATLABRobust
ControlToolbox3available,Da-WeiGu,PetkoH.Petkov,andMihailKonstantinov
have now produced this second edition of their book. The revised text has grown
from 13 chapters and 389 pages to 19 chapters and just over 460 pages. But most
significantlythetextbookhasaslightlydifferentandimprovedstructurethatmakes
the MATLAB material more accessible and focused. Part I still looks at the dif-
ferentandbasicelementsofrobustcontroldesignprocedures.However,thereisa
useful new chapter on general results that use Linear Matrix Inequalities (LMIs).
The newly introduced Part II presents chapters focusing on the use of tools and
routines from the Robust Control Toolbox Version 3. Thus, whereas in Part I the
theoryoftherobustcontrolproceduresisoutlined,inthisnewpart,theMATLAB
implementationsarepresentedanddemonstrated.Finally,inPartIIIwefindsixin-
depth design studies, two of which are entirely new. The case studies carried over
fromthefirsteditionofthetextbookarethebenchmarksystemexamples,namely,
hard-disc-drive control, the triple inverted pendulum system, a high-purity distil-
lation system, and a flexible manipulator system, which is a distributed-parameter
system.Thetwonewcasestudiesareatwinrotoraerodynamicalsystemandaself-
balancing two-wheeled robot; both systems that are often found as test rigs in the
controlengineeringteachinglaboratory;a feature of these two new designstudies
isthepresentationofexperimentalresultsfromlaboratorytest-rigstodemonstrate
andassesstheperformanceoftherobustcontroldesigns.
Wehavenowpassedthroughsome30yearsofconsolidationsincetheacademic
control community began to look again at the foundations of control system de-
sign and formulated and developed the robust control paradigm. The fact that the

SeriesEditors’Foreword ix
MATLABRobustControlToolboxhasreached“Version3”demonstrateshowro-
bust control and MATLAB remain pervasive tools for the academic and industrial
controlengineeringcommunity.ThustheEditorsareverypleasedtowelcomethis
second edition of Robust Control Design with MATLAB®. It is a valuable contri-
bution to the list of publications in the Advanced Textbooks in Control and Signal
Processing series; the authors’ new structure and material brings additional peda-
gogical value to the new edition as an advanced textbook for teaching on courses
andforself-studybythecontrolengineer.
Glasgow,Scotland,UK M.J.Grimble
July2012 M.A.Johnson

Preface to the Second Edition
It has been encouragingto receive commentsand suggestions on this book ofRo-
bust Control Design with MATLAB® since it was published in 2005. And, we are
nowverypleasedtotaketheopportunitytoofferourreadersthe2ndeditionofthe
book.
Robustnessisofcrucialimportanceincontrolsystemsdesign,becauserealengi-
neeringsystemsarevulnerabletoexternaldisturbanceandmeasurementnoise,and
there are always discrepancies between mathematical models used for design and
the actual system in practice. Typically a control engineer is required to design a
controllerwhichwillmaketheclosedloopsystemstableandachievecertainperfor-
mancelevelsinthepresenceofdisturbancesignals,noiseinterference,unmodeled
plantdynamicsandplantparametervariations.Thepurposeofthisbookistohelp
post-graduatestudentsandcontrolengineerslearnhowtousewell-developed,ad-
vanced robust control system design methods and the state-of-the-art MATLAB®
toolsinpracticaldesigncases.
A major feature of the second edition is the inclusion of an introduction to the
use of the Robust Control Toolbox®3, as a new Part II between “Basic Methods
and Theory” (Part I) and “Design Examples” (now Part III). Main function rou-
tinesavailableinRobustControlToolbox®3,rangingfrombuildingdynamicplant
models and uncertainty models, systems stability and performance analysis to de-
signofH ∞andμaswellasparameter-dependentcontrollers,areintroducedinthis
newPartII.Withrelativelysimpleexamples,suchasthemass–spring–dampersys-
tem, which is widely used in teachinglaboratories of control engineering courses,
usage of those MATLAB® routines is explained and illustrated at a level easier
to be understood by readers, which of course follows the guidance in writing this
book. In addition to this new Part II and correction of a few minor errors in the
first edition, there is also a new chapter in Part I on introduction to Linear Matrix
Inequalities(LMI).AlthoughLMIisnotdirectlyusedinthoseexamplespresented
inPartIII,itisindirectlyusedinsomecontrollersolutionprocedures.Withitsvalue
in control systems analysis and design and its popularity, a brief introduction on
LMI’sbasicpropertiesanduseincontrolengineeringwouldbewelcomedbyusers,
we hope. There are also some changes in Part III. The mass–spring–damper sys-
xi

xii PrefacetotheSecondEdition
tem case has now been moved to Part II for illustration of using Robust Control
Toolbox®3functionroutines.Therobustcontrolofarocketcasehasbeenremoved.
Instead,wenowincludetwootherdesignexamples,namelyrobustcontrolofatwin-
rotor aerodynamicsystem and robust control of self-balancingtwo-wheeled robot.
These two new examples are very popular experimental devices widely available
in control teaching laboratories. Inclusion of these examples will better help read-
ers to understand robust control design methods and to practice their own design
whichcanbetestedandverifiedintheirownexperiments.Alldesignexamplesin
PartIIIarerealisticcasestudies.TheyarepresentedinPartIIIindetail.Thesede-
signexercisesareallconductedusingRobustControlToolbox®3.Itistheauthors’
hopethatstudyingtheseexampleswithattachedprogramsusedinalldesigns,with
minimum exposure of theory and formulas in earlier parts of the book, will help
readers obtain essential ideas and useful insights of several important robust con-
trolsystemsdesignapproaches,includingH ∞andrelatedmethodsandμ-synthesis
methods,anddeveloptheirownskillstodesignreal-worldindustrial,robustcontrol
systems.
The authors are indebtedto several peopleand institutionswho helpedthemin
the preparation of the book. We are particularly grateful to The MathWorks, Inc.
for their continuous support, to Professor Sigurd Skogestad of Norwegian Uni-
versity of Science and Technology who kindly provided the nonlinear model of
theDistillationColumn,toAssociateProfessorGeorgiLehovfromTechnicalUni-
versity of Russe, Bulgaria, who developed the uncertainty model of the Flexible-
Link Manipulator and to Associate Professor Tsonyo Slavov from Technical Uni-
versityof Sofia,Bulgaria,whodevelopedtheSimulink® modelof theHydroTur-
bineGainSchedulingControl.Asalways,helpfromtheSpringerEditorsandcom-
ments from the Series Editors in preparing this second edition are highly appreci-
ated.
UsingtheDownloadableMaterial
Forreaderswhopurchasedthisbook,supportingmaterial,comprisedofsixfolders
with170M-andMDL-filesintendedfordesign,analysis,andsimulationofthesix
designexamplesinPartIII,plusfivefolderscontaining35fileswiththeexamples
fromPartII,plusaReadme.mfileandapdf,hypertextversionofthebookcanbe
downloadedfromhttp://www.springer.com/978-1-85233-938-8.
InordertousetheM-andMDL-filesthereadershouldhaveathis/herdisposi-
tionMATLAB®versionR2011aorhigher,withRobustControlToolbox®3,Control
SystemToolboxv9.1andSimulink®v7.7.Thedesignandexperimentswiththelast
two examples (Twin-Rotor Aerodynamic System and Self-Balancing Two-Wheeled
Robot) are performed with MATLAB® version R2007b in order to have compati-
bilitywiththecorrespondingthird-partysoftwareforreal-timecontrol.Pleasenote
alsothattheprogramsdownloadablearedifferentfromthosecontainedontheCD
ROMdistributedwiththefirsteditionofthebook,fortheconvenienceofreadersto

PrefacetotheSecondEdition xiii
usethelaterversionofRobustControlToolboxinsteadofusingfunctionsfromthe
obsoleteμ-toolbox.
Leicester,UK Da-WeiGu
Sofia,Bulgaria PetkoH.Petkov
Sofia,Bulgaria MihailM.Konstantinov

Preface to the First Edition
Robustnesshasbeenanimportantissueincontrol-systemsdesigneversince1769
when James Watt developed his flyball governor. A successfully designed control
systemshouldbealwaysabletomaintainastabilityandperformancelevelinspite
ofuncertaintiesinsystemdynamicsand/orintheworkingenvironmenttoacertain
degree.Designrequirementssuchasgainmarginandphasemargininusingclassi-
cal frequency-domain techniques are solely for the purpose of robustness. The ro-
bustnessissuewasnotthatprominentlyconsideredduringtheperiodof1960sand
1970s when system models could be much more accurately described and design
methods were mainly mathematical optimizations in the time domain. Due to its
importance,however,theresearchonrobustdesignhasbeengoingonallthetime.
Abreakthroughcameinthelate1970sandearly1980swiththepioneeringworkby
Zames[192]andZamesandFrancis[193]onthetheory,nowknownastheH ∞op-
timal control theory. The H ∞ optimization approach and the μ-synthesis/analysis
methodarewelldevelopedandelegant.Theyprovidesystematicdesignprocedures
ofrobustcontrollersforlinearsystems,thoughtheextensionintononlinearcasesis
beingactivelyresearched.
Many books have since been published on H ∞ and related theories and meth-
ods[34,45,73,150,155,158,195,196].Thealgorithmstoimplementthedesign
methodsarereadilyavailableinsoftwarepackagessuchasMATLAB® andSlicot
[78].However,fromourexperienceinteachingandresearchprojects,wehavefelt
thatareasonablepercentageofpeople,studentsaswellaspracticingengineers,still
have difficulties in applying the H ∞ and related theory and in using MATLAB®
routines.Themathematicsbehindthetheoryisquiteinvolved.Itisnotstraightfor-
ward to formulate a practical design problem, which is usually nonlinear, into the
H ∞ or μ designframeworkandthenapplyMATLAB® routines.Thishindersthe
applicationofsuchapowerfultheory.Italsomotivatedustopreparethisbook.
Thisbookisforpeoplewhowanttolearnhowtodealwithrobustcontrol-system
designproblemsbutmaynotwanttoresearchtherelevanttheoreticdevelopments.
Methodsandsolutionformulasareintroducedinthefirstpartofthebook,butkept
toaminimum.Themajorityofthebookisdevotedtoseveralpracticaldesigncase
studies(PartII). Thesedesignexamples,rangingfrom teachinglaboratoryexperi-
xv

xvi PrefacetotheFirstEdition
mentssuchasamass–damper–springsystemtocomplexsystemssuchasasuper-
sonic rocket autopilot and a flexible-link manipulator, are discussed with detailed
presentations. The design exercises are all conducted using the new Robust Con-
trol Toolbox v3.0 and are in a hands-on, tutorial manner. Studying these examples
with the attached MATLAB® and Simulink® programs (170 plus M- and MDL-
files)usedinalldesignswillhelpthereaderslearnhowtodealwithnonlinearities
involvedinthesystem,howtoparameterizedynamicuncertaintiesandhowtouse
MATLAB® routines in the analysis and design, etc. It is also hoped that by going
through these exercises the readers will understand the essence of robust control
systemdesignanddeveloptheirownskillstodesignreal,industrial,robustcontrol
systems.
Thereadershipofthisbookispostgraduatesandcontrolengineers,thoughsenior
undergraduatesmayuseitfortheirfinal-yearprojects.Thematerialincludedinthe
bookhasbeenadoptedinrecentyearsforM.Sc.andPh.D.engineeringstudentsat
LeicesterUniversityandattheTechnicalUniversityofSofia.Thedesignexamples
are independent of each other. They have been used extensively in the laboratory
projects on the course Robust and Optimal Control Systems taught in a masters
programmeintheTechnicalUniversityofSofia.
The authors are indebtedto several peopleand institutionswho helpedthemin
thepreparationofthebook.WeareparticularlygratefultoTheMathWorks,Inc.for
theircontinuoussupport,toProfessorSigurdSkogestadofNorwegianUniversityof
Science and Technology who kindly provided the nonlinear model of the Distilla-
tionColumnandtoAssociateProfessorGeorgiLehovfromTechnicalUniversityof
Russe,Bulgaria,whodevelopedtheuncertaintymodeloftheFlexible-LinkManip-
ulator.
UsingtheCDROM
The attached CD ROM contains six folders with M- and MDL-files intended for
design, analysis, and simulation of the six design examples, plus a pdf file with
colorhypertextversionofthebook.InordertousetheM-andMDL-filesthereader
shouldhaveathis(her)dispositionMATLAB®v7.0.2withRobustControlToolbox
v3.0,ControlSystemToolboxv6.1andSimulink®v6.1.Furtherinformationonthe
useofthefilescanbefoundinthefileReadme.monthedisc.

Contents
PartI BasicMethodsandTheory
1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 3
1.1 Control-SystemRepresentations . . . . . . . . . . . . . . . . . . 4
1.2 SystemStabilities . . . . . . . . . . . . . . . . . . . . . . . . . 5
1.3 CoprimeFactorizationandStabilizingControllers . . . . . . . . 7
1.4 SignalsandSystemNorms . . . . . . . . . . . . . . . . . . . . . 9
1.4.1 VectorNormsandSignalNorms . . . . . . . . . . . . . 9
1.4.2 SystemNorms. . . . . . . . . . . . . . . . . . . . . . . 10
2 ModelingofUncertainSystems . . . . . . . . . . . . . . . . . . . . . 13
2.1 UnstructuredUncertainties . . . . . . . . . . . . . . . . . . . . . 13
2.2 ParametricUncertainty . . . . . . . . . . . . . . . . . . . . . . . 17
2.3 LinearFractionalTransformations . . . . . . . . . . . . . . . . . 19
2.4 StructuredUncertainties . . . . . . . . . . . . . . . . . . . . . . 21
3 RobustDesignSpecifications . . . . . . . . . . . . . . . . . . . . . . 23
3.1 Small-GainTheoremandRobustStabilization . . . . . . . . . . 23
3.2 PerformanceConsiderations . . . . . . . . . . . . . . . . . . . . 26
3.3 StructuredSingularValues . . . . . . . . . . . . . . . . . . . . . 27
4 H ∞ Design . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 31
4.1 MixedSensitivityH ∞ Optimization . . . . . . . . . . . . . . . . 31
4.2 2-Degree-of-FreedomH ∞ Design . . . . . . . . . . . . . . . . . 33
4.3 H ∞ SuboptimalSolutions . . . . . . . . . . . . . . . . . . . . . 34
4.3.1 SolutionFormulasforNormalizedSystems . . . . . . . 35
4.3.2 SolutiontoS-over-KS Design . . . . . . . . . . . . . . 38
4.3.3 TheCaseofD (cid:3)=0 . . . . . . . . . . . . . . . . . . . 39
22
4.3.4 NormalizationTransformations . . . . . . . . . . . . . . 40
4.3.5 DirectFormulasforH ∞ SuboptimalCentralController . 41
4.4 FormulasforDiscrete-TimeCases . . . . . . . . . . . . . . . . . 45
xvii

| xviii |     |     |     |     |     |     |     | Contents |     |
| ----- | --- | --- | --- | --- | --- | --- | --- | -------- | --- |
H
5 ∞ Loop-ShapingDesignProcedures . . . . . . . . . . . . . . . . . 49
| 5.1 | Robust | Stabilization | Against | Normalized |     | Coprime | Factor |     |     |
| --- | ------ | ------------- | ------- | ---------- | --- | ------- | ------ | --- | --- |
Perturbations . . . . . . . . . . . . . . . . . . . . . . . . . . . . 49
5.2 Loop-ShapingDesignProcedures . . . . . . . . . . . . . . . . . 52
5.3 FormulasfortheDiscrete-TimeCase . . . . . . . . . . . . . . . 54
|     | 5.3.1 | NormalizedCoprimeFactorizationofDiscrete-TimePlant |     |     |     |     |     |     | 54  |
| --- | ----- | -------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- |
5.3.2 RobustControllerFormulas. . . . . . . . . . . . . . . . 56
5.3.3 TheStrictlyProperCase . . . . . . . . . . . . . . . . . 57
|     | 5.3.4 | OntheThreeDARESolutions |     |     |     | . . . . | . . . . . | . . . . | . 58 |
| --- | ----- | ----------------------- | --- | --- | --- | ------- | --------- | ------- | ---- |
5.4 AMixedOptimizationDesignMethodwithLSDP . . . . . . . . 60
6 μ-AnalysisandSynthesis . . . . . . . . . . . . . . . . . . . . . . . . 65
6.1 ConsiderationofRobustPerformance . . . . . . . . . . . . . . . 65
6.2 μ-Synthesis:D–K IterationMethod. . . . . . . . . . . . . . . . 68
6.3 μ-Synthesis:μ–K IterationMethod . . . . . . . . . . . . . . . . 70
7 Lower-OrderControllers . . . . . . . . . . . . . . . . . . . . . . . . 73
7.1 Absolute-ErrorApproximationMethods . . . . . . . . . . . . . 74
7.1.1 BalancedTruncationMethod . . . . . . . . . . . . . . . 75
7.1.2 SingularPerturbationApproximation. . . . . . . . . . . 76
7.1.3 Hankel-NormApproximation. . . . . . . . . . . . . . . 77
7.2 ReductionviaFractionalFactors . . . . . . . . . . . . . . . . . . 80
|     | 7.2.1 | FractionalBalancedTruncation(FBT)Method           |     |     |     |     |     | . . . . | . 82 |
| --- | ----- | ------------------------------------------------- | --- | --- | --- | --- | --- | ------- | ---- |
|     | 7.2.2 | FractionalSingularPerturbationApproximation(FSPA) |     |     |     |     |     |         |      |
Method . . . . . . . . . . . . . . . . . . . . . . . . . . 82
7.3 Relative-ErrorApproximationMethods . . . . . . . . . . . . . . 84
7.4 Frequency-WeightedApproximationMethods . . . . . . . . . . 86
|     | 7.4.1 | Frequency-WeightedBalancedTruncation(FWBT)     |     |     |          |              |           | . .     | . 88 |
| --- | ----- | ---------------------------------------------- | --- | --- | -------- | ------------ | --------- | ------- | ---- |
|     | 7.4.2 | Frequency-Weighted                             |     |     | Singular | Perturbation |           |         |      |
|     |       | Approximation(FWSPA)                           |     |     | . .      | . . . . .    | . . . . . | . . . . | . 89 |
|     | 7.4.3 | Frequency-WeightedModuliTruncationMethod(FWMT) |     |     |          |              |           |         | 89   |
8 LMIApproach . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 93
8.1 BasicsAboutLMI . . . . . . . . . . . . . . . . . . . . . . . . . 93
8.2 ControlProblemsUsingLMI . . . . . . . . . . . . . . . . . . . 94
8.2.1 LyapunovStabilityCriterion . . . . . . . . . . . . . . . 94
8.2.2 StabilizationbyStateFeedback . . . . . . . . . . . . . . 94
ComputationofL
|     | 8.2.3 |     |     | Norm | . . | . . . . . | . . . . . | . . . . | . 95 |
| --- | ----- | --- | --- | ---- | --- | --------- | --------- | ------- | ---- |
2
|     | 8.2.4 | ComputationofH |     | Norm | .   | . . . . . | . . . . . | . . . . | . 97 |
| --- | ----- | -------------- | --- | ---- | --- | --------- | --------- | ------- | ---- |
∞
|     | 8.2.5 | FormulationofLQRinLMI |     |     |     | . . . . . | . . . . . | . . . . | . 97 |
| --- | ----- | --------------------- | --- | --- | --- | --------- | --------- | ------- | ---- |
8.3 AFewMorePropertiesConcerningLMI . . . . . . . . . . . . . 99
8.3.1 CongruenceTransformation . . . . . . . . . . . . . . . 99
8.3.2 SchurComplementsforNonstrictInequalities . . . . . . 100
8.3.3 ProjectionandFinsler’sLemmas . . . . . . . . . . . . . 100
8.3.4 TheS-ProcedureforQuadraticFunctions . . . . . . . . 102
8.3.5 DualizationLemma . . . . . . . . . . . . . . . . . . . . 102

Contents xix
PartII IntroductiontoRobustControlToolboxv3
9 BuildingUncertainModels . . . . . . . . . . . . . . . . . . . . . . . 107
9.1 LTIModels . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 107
9.2 StructuredUncertaintyModels. . . . . . . . . . . . . . . . . . . 121
9.2.1 UncertainRealParameters . . . . . . . . . . . . . . . . 123
9.2.2 UncertainState-SpaceSystems . . . . . . . . . . . . . . 124
9.2.3 PropertiesofUncertainSystems . . . . . . . . . . . . . 125
9.2.4 OtherFunctionstoBuildUncertainModels . . . . . . . 130
9.2.5 DecomposingUncertainObjects . . . . . . . . . . . . . 131
9.3 BuildingUncertainModelsUsingiconnectandsysic . . . . 132
9.4 UnstructuredUncertaintyModels . . . . . . . . . . . . . . . . . 134
9.4.1 ModelswithAdditiveUncertainty . . . . . . . . . . . . 135
9.4.2 ModelswithMultiplicativeUncertainty . . . . . . . . . 138
9.4.3 UnmodeledDynamics . . . . . . . . . . . . . . . . . . 140
9.4.4 MultivariablePlantswithUnstructuredUncertainty . . . 142
9.5 Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 143
10 RobustStabilityandPerformance . . . . . . . . . . . . . . . . . . . 145
10.1 RobustStabilityAnalysis . . . . . . . . . . . . . . . . . . . . . 145
10.2 RobustPerformanceAnalysis . . . . . . . . . . . . . . . . . . . 154
10.3 Worst-CaseGain . . . . . . . . . . . . . . . . . . . . . . . . . . 165
10.4 Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 170
11 H ∞ Design . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 173
11.1 H ∞ Loop-ShapingDesign . . . . . . . . . . . . . . . . . . . . . 173
11.2 MixedSensitivityDesign . . . . . . . . . . . . . . . . . . . . . 179
11.3 OtherVersionsofH ∞ Design . . . . . . . . . . . . . . . . . . . 187
11.3.1 H ∞ ControlwithModels . . . . . . . . . . . . . . . . . 187
11.3.2 Two-Degree-of-FreedomH ∞ Control . . . . . . . . . . 194
11.4 Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 200
12 μ-Synthesis . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 203
12.1 Theμ-SynthesisProblem . . . . . . . . . . . . . . . . . . . . . 203
12.2 μ-SynthesisbyD–K Iterations . . . . . . . . . . . . . . . . . . 205
12.3 Versionsofμ-Synthesis . . . . . . . . . . . . . . . . . . . . . . 212
12.3.1 μ-SynthesiswithModel . . . . . . . . . . . . . . . . . 212
12.3.2 μ-Synthesisof2-Degree-of-FreedomController . . . . . 214
12.4 PracticalAspectsofμ-Analysisandμ-Synthesis . . . . . . . . . 216
12.5 Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 219
13 AnalysisandDesignofParameter-DependentSystems . . . . . . . . 221
13.1 RepresentationofParameter-DependentSystems . . . . . . . . . 221
13.1.1 SYSTEMMatrix . . . . . . . . . . . . . . . . . . . . . 221
13.1.2 AffineParameter-DependentModels . . . . . . . . . . . 223
13.1.3 PolytopicModels . . . . . . . . . . . . . . . . . . . . . 227
13.2 AnalysisofParameter-DependentSystems . . . . . . . . . . . . 229

xx Contents
13.3 GainSchedulingDesignforParameter-DependentSystems . . . 234
13.4 Exercises . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 246
PartIII DesignExamples
14 RobustControlofaHardDiskDrive . . . . . . . . . . . . . . . . . . 249
14.1 HardDiskDriveServoSystem. . . . . . . . . . . . . . . . . . . 249
14.2 DerivationofUncertaintyModel. . . . . . . . . . . . . . . . . . 255
14.3 Closed-LoopSystemDesignSpecifications . . . . . . . . . . . . 258
14.3.1 NominalPerformance . . . . . . . . . . . . . . . . . . . 260
14.3.2 RobustStability . . . . . . . . . . . . . . . . . . . . . . 260
14.3.3 RobustPerformance. . . . . . . . . . . . . . . . . . . . 260
14.4 SystemInterconnections . . . . . . . . . . . . . . . . . . . . . . 261
14.5 ControllerDesigninContinuous-Time . . . . . . . . . . . . . . 262
14.5.1 μ-Design . . . . . . . . . . . . . . . . . . . . . . . . . 263
14.5.2 H ∞ Design . . . . . . . . . . . . . . . . . . . . . . . . 269
14.5.3 H ∞ Loop-ShapingDesign . . . . . . . . . . . . . . . . 269
14.6 ComparisonofDesignedControllers . . . . . . . . . . . . . . . 270
14.7 Controller-OrderReduction . . . . . . . . . . . . . . . . . . . . 277
14.8 DesignofDiscrete-TimeController . . . . . . . . . . . . . . . . 279
14.9 NonlinearSystemSimulation . . . . . . . . . . . . . . . . . . . 284
14.10 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . 289
14.11 NotesandReferences . . . . . . . . . . . . . . . . . . . . . . . 289
15 ATripleInvertedPendulumControlSystemDesign . . . . . . . . . 291
15.1 SystemDescription. . . . . . . . . . . . . . . . . . . . . . . . . 292
15.2 ModelingofUncertainties . . . . . . . . . . . . . . . . . . . . . 295
15.3 DesignSpecifications . . . . . . . . . . . . . . . . . . . . . . . 302
15.3.1 RobustStability . . . . . . . . . . . . . . . . . . . . . . 304
15.3.2 NominalPerformance . . . . . . . . . . . . . . . . . . . 304
15.3.3 RobustPerformance. . . . . . . . . . . . . . . . . . . . 304
15.4 SystemInterconnections . . . . . . . . . . . . . . . . . . . . . . 306
15.5 H ∞ Design . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 308
15.6 μ-Synthesis. . . . . . . . . . . . . . . . . . . . . . . . . . . . . 313
15.7 NonlinearSystemSimulation . . . . . . . . . . . . . . . . . . . 322
15.8 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . 322
15.9 NotesandReferences . . . . . . . . . . . . . . . . . . . . . . . 325
16 RobustControlofaDistillationColumn . . . . . . . . . . . . . . . . 327
16.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . 327
16.2 DynamicModeloftheDistillationColumn . . . . . . . . . . . . 328
16.3 UncertaintyModeling . . . . . . . . . . . . . . . . . . . . . . . 332
16.4 Closed-LoopSystemPerformanceSpecifications . . . . . . . . . 334
16.5 Open-LoopandClosed-LoopSystemInterconnections . . . . . . 339
16.6 ControllerDesign . . . . . . . . . . . . . . . . . . . . . . . . . 342
16.6.1 Loop-ShapingDesign . . . . . . . . . . . . . . . . . . . 343
16.6.2 μ-Synthesis . . . . . . . . . . . . . . . . . . . . . . . . 346

Contents xxi
16.7 NonlinearSystemSimulation . . . . . . . . . . . . . . . . . . . 362
16.8 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . 364
16.9 NotesandReferences . . . . . . . . . . . . . . . . . . . . . . . 365
17 RobustControlofaFlexible-LinkManipulator . . . . . . . . . . . . 367
17.1 DynamicModeloftheFlexibleManipulator . . . . . . . . . . . 368
17.2 ALinearModeloftheUncertainSystem . . . . . . . . . . . . . 371
17.3 SystemPerformanceSpecifications . . . . . . . . . . . . . . . . 378
17.4 SystemInterconnections . . . . . . . . . . . . . . . . . . . . . . 381
17.5 ControllerDesignandAnalysis . . . . . . . . . . . . . . . . . . 383
17.6 NonlinearSystemSimulations . . . . . . . . . . . . . . . . . . . 394
17.7 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . 395
17.8 NotesandReferences . . . . . . . . . . . . . . . . . . . . . . . 399
18 RobustControlofaTwin-RotorAerodynamicSystem . . . . . . . . 401
18.1 Twin-RotorAerodynamicSystem . . . . . . . . . . . . . . . . . 401
18.2 NonlinearSystemModel . . . . . . . . . . . . . . . . . . . . . . 402
18.3 LinearizedSystemModel . . . . . . . . . . . . . . . . . . . . . 407
18.4 UncertaintyModeling . . . . . . . . . . . . . . . . . . . . . . . 410
18.5 Closed-LoopSystemPerformanceRequirements . . . . . . . . . 412
18.5.1 RobustStability . . . . . . . . . . . . . . . . . . . . . . 414
18.5.2 NominalPerformance . . . . . . . . . . . . . . . . . . . 414
18.5.3 RobustPerformance. . . . . . . . . . . . . . . . . . . . 414
18.6 SystemInterconnections . . . . . . . . . . . . . . . . . . . . . . 415
18.7 μ-Synthesis. . . . . . . . . . . . . . . . . . . . . . . . . . . . . 415
18.8 NonlinearSystemSimulation . . . . . . . . . . . . . . . . . . . 427
18.9 ExperimentalResults . . . . . . . . . . . . . . . . . . . . . . . . 428
18.10 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . 428
18.10.1 NotesandReferences . . . . . . . . . . . . . . . . . . . 433
19 RobustControlofSelf-balancingTwo-WheeledRobot . . . . . . . . 435
19.1 Introduction . . . . . . . . . . . . . . . . . . . . . . . . . . . . 435
19.2 UncertainModeloftheTwo-WheeledRobot . . . . . . . . . . . 436
19.3 DesignofRobustController . . . . . . . . . . . . . . . . . . . . 440
19.4 Closed-LoopSystemProperties . . . . . . . . . . . . . . . . . . 444
19.5 ExperimentalResults . . . . . . . . . . . . . . . . . . . . . . . . 450
19.6 Conclusions . . . . . . . . . . . . . . . . . . . . . . . . . . . . 452
19.7 NotesandReferences . . . . . . . . . . . . . . . . . . . . . . . 453
References . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 455
Index . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 465

Part I
Basic Methods and Theory

Chapter 1
Introduction
Robustnessisofcrucialimportanceincontrol-systemdesignbecauserealengineer-
ingsystemsarevulnerabletoexternaldisturbanceandmeasurementnoiseandthere
are always differences between mathematical models used for design and the ac-
tualsystem.Typically,acontrolengineerisrequiredtodesignacontrollerthatwill
stabilizeaplant,ifitisnotstableoriginally,andsatisfycertainperformancelevels
inthepresenceofdisturbancesignals,noiseinterference,unmodeledplantdynam-
icsandplant-parametervariations.Thesedesignobjectivesarebestrealizedviathe
feedback control mechanism,although it introduces in the issues of high cost (the
useofsensors),systemcomplexity(implementationandsafety)andmoreconcerns
onstability(thusinternalstabilityandstabilizingcontrollers).
Thoughalwayshavingbeenappreciated,theneedandimportanceofrobustness
in control-systems design has been particularly brought into the limelight during
the last two decades. In classical single-input single-output control, robustness is
achieved by ensuring good gain and phase margins. Designing for good stability
marginsusuallyalsoresultsingood,well-dampedtimeresponses,i.e.goodperfor-
mance.Whenmultivariabledesigntechniqueswerefirstdevelopedinthe1960s,the
emphasiswasplacedonachievinggoodperformance,andnotonrobustness.These
multivariable techniques were based on linear quadratic performance criteria and
Gaussiandisturbances,andprovedtobesuccessfulinmanyaerospaceapplications
whereaccuratemathematicalmodelscanbeobtained,anddescriptionsforexternal
disturbances/noise based on white noise are considered appropriate. However, ap-
plication of such methods, commonly referred to as the linear quadratic Gaussian
(LQG) methods, to other industrial problems made apparent the poor robustness
properties exhibited by LQG controllers. This led to a substantial research effort
to develop a theory that could explicitly address the robustness issue in feedback
design. The pioneering work in the development of the forthcoming theory, now
known as the H ∞ optimal control theory, was conducted in the early 1980s by
Zames[192]andZamesandFrancis[193].IntheH ∞ approach,thedesignerfrom
the outset specifies a model of system uncertainty, such as additive perturbation
and/oroutputdisturbance(detailsinChap.2),whichismostsuitedtotheproblem
athand.Aconstrainedoptimizationisthenperformedtomaximizetherobuststabil-
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 3
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_1,©Springer-VerlagLondon2013

4 1 Introduction
ityoftheclosed-loopsystemtothetypeofuncertaintychosen,theconstraintbeing
the internal stability of the feedback system. In most cases, it would be sufficient
to seek a feasible controller such that the closed-loop system achieves certain ro-
buststability.Performanceobjectivescanalsobeincludedintheoptimizationcost
function.Elegantsolutionformulashavebeendeveloped,whicharebasedontheso-
lutionsofcertainalgebraicRiccatiequations,andarereadilyavailableinsoftware
packagessuchasSlicot[78]andMATLAB®.
Despite the mature theory [34, 45, 73, 150, 158, 195, 196] and availability of
softwarepackages,commercialorlicensedfreeware,manypeoplehaveexperienced
difficultiesinsolvingindustrialcontrol-systemsdesignproblemswiththeseH ∞and
relatedmethods,duetothecomplexmathematicsoftheadvancedapproachesand
numerous presentations of formulas as well as adequate translations of industrial
designintorelevantconfigurations.Thisbookaimsatbridgingthegapbetweenthe
theory and applications. By sharing the experience in industrial case studies with
minimumexposuretothetheoryandformulas,theauthorshopereaderswillobtain
insightintorobustindustrialcontrol-systemdesignsusingmajorH ∞ optimization
andrelatedmethods.
Inthischapter,thebasicconceptsandrepresentationsofsystemsandsignalswill
bediscussed.
1.1 Control-System Representations
Acontrolsystemorplantorprocessisaninterconnectionofcomponentstoperform
certain tasks and to yield a desired response, i.e. to generate desired signal (the
output),whenitisdrivenbymanipulatingsignal(theinput).Acontrolsystemisa
causal,dynamicsystem,i.e.theoutputdependsnotonlythepresentinputbutalso
theinputattheprevioustime.
In general, there are two categories of control systems, the open-loop systems
andclosed-loopsystems.Anopen-loopsystemusesacontrollerorcontrolactuator
toobtainthedesignresponse.Inanopen-loopsystem,theoutputhasnoeffectonthe
input.Incontrasttoanopen-loopsystem,aclosed-loopcontrolsystemusessensors
tomeasuretheactualoutputtoadjusttheinputinordertoachievedesiredoutput.
The measure of the outputis calledthe feedbacksignal,and a closed-loopsystem
is also called a feedback system. It will be shown in this book that only feedback
configurationsareabletoachievetherobustnessofacontrolsystem.
Due to the increasing complexity of physical systems under control and rising
demandsonsystemproperties,mostindustrialcontrolsystemsarenolongersingle-
input and single-output (SISO) but multi-input and multi-output (MIMO) systems
with a high interrelationship (coupling) between these channels. The number of
(state) variables in a system could be very large as well. These systems are called
multivariablesystems.
In order to analyze and design a control system, it is advantageous if a math-
ematical representation of such a relationship (a model) is available. The system

1.2 SystemStabilities 5
dynamicsisusuallygovernedbyasetofdifferentialequationsineitheropen-loop
or closed-loop systems. In the case of linear, time-invariant systems, which is the
casethisbookconsiders,thesedifferentialequationsarelinearordinarydifferential
equations. By introducing appropriate state variables and simple manipulations, a
linear,time-invariant,continuous-timecontrolsystemcanbedescribedbythefol-
lowingmodel:
x˙(t)=Ax(t)+Bu(t)
(1.1)
y(t)=Cx(t)+Du(t)
where x(t) ∈ Rn is the state vector, u(t) ∈ Rm the input (control) vector, and
y(t)∈Rp theoutput(measurement)vector.
With the assumption of zero initial condition of the state variables and using
Laplace transform, a transfer function matrix corresponding to the system in (1.1)
canbederivedas
G(s):=C(sI −A) −1B+D (1.2)
n
andcanbefurtherdenotedinashortformby
(cid:2) (cid:3)
A B
G(s)=: (1.3)
C D
It should be noted that the H ∞ optimization approach is a frequency-domain
method,thoughitutilizesthetime-domaindescriptionsuchas(1.1)toexplorethe
advantages in numerical computation and to deal with multivariable systems. The
systemgivenin(1.1)isassumedinthisbooktobeminimal,i.e.completelycontrol-
lableandcompletelyobservable,unlessdescribedotherwise.
Inthecaseofdiscrete-timesystems,similarlythemodelisgivenby
x(k+1)=Ax(k)+Bu(k)
(1.4)
y(k)=Cx(k)+Du(k)
or
x k+1 =Ax k +Bu k
y =Cx +Du
k k k
withacorrespondingtransferfunctionmatrixas
G(z):=C(zI −A) −1B+D
(cid:2) n (cid:3)
A B
=: (1.5)
C D
1.2 System Stabilities
Anessentialissueincontrol-systemsdesignisthestability.Anunstablesystemisof
nopracticalvalue.Thisisbecauseanycontrolsystemisvulnerabletodisturbances

6 1 Introduction
Fig.1.1 Aninterconnected
systemofGandK
andnoisesinarealworkenvironment,andtheeffectduetothesesignalswouldad-
verselyaffecttheexpected,normalsystemoutputinanunstablesystem.Feedback
controltechniquesmayreducetheinfluencegeneratedbyuncertaintiesandachieve
desirableperformance.However,aninadequatefeedbackcontrollermayleadtoan
unstableclosed-loopsystemthoughtheoriginalopen-loopsystemisstable.Inthis
section,control-systemstabilitiesandstabilizingcontrollersforagivencontrolsys-
temwillbediscussed.
When a dynamic system is just described by its input/output relationship such
asatransferfunction(matrix),thesystemisstableifitgeneratesboundedoutputs
for any bounded inputs. This is called the bounded-input-bounded-output (BIBO)
stability.Foralinear,time-invariantsystemmodeledbyatransferfunctionmatrix
(G(s)in(1.2)),theBIBOstabilityisguaranteedifandonlyifallthepolesofG(s)
areintheopen-left-halfcomplexplane,i.e.withnegativerealparts.
Whenasystemisgovernedbyastate-spacemodelsuchas(1.1),astabilitycon-
ceptcalledasymptoticstabilitycanbedefined.Asystemisasymptoticallystableif,
for an identically zero input, the system state will converge to zero from any ini-
tial states. For a linear, time-invariant system described by a model of (1.1), it is
asymptoticallystableif andonlyifalltheeigenvaluesofthestatematrix A arein
theopen-left-halfcomplexplane,i.e.withpositiverealparts.
In general, the asymptotic stability of a system implies that the system is also
BIBOstable,butnotviceversa.However,forasystemin(1.1),if [A,B,C,D] is
ofminimalrealization,theBIBOstabilityofthesystemimpliesthatthesystemis
asymptoticallystable.
The above stabilities are defined for open-loop systems as well as closed-loop
systems.Foraclosed-loopsystem(interconnected,feedbacksystem),itismorein-
terestingandintuitivetolookattheasymptoticstabilityfromanotherpointofview
andthisiscalledtheinternalstability[27].Aninterconnectedsystemisinternally
stable if the subsystems of all input–output pairs are asymptotically stable (or the
correspondingtransferfunctionmatricesareBIBOstablewhenthestatespacemod-
elsareminimal,whichisassumedinthischapter).Internalstabilityisequivalentto
asymptotic stability in an interconnected, feedback system but may reveal explic-
itlytherelationshipbetweentheoriginal,open-loopsystemandthecontrollerthat
influencesthestabilityofthewholesystem.ForthesystemgiveninFig.1.1,there
aretwoinputsr andd (thedisturbanceattheoutput)andtwooutputsy andu(the
outputofthecontrollerK).

| 1.3 CoprimeFactorizationandStabilizingControllers |     |     |     |     |     |     |     | 7   |
| ------------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
Thetransferfunctionsfromtheinputstotheoutputs,respectively,are
|     |     |     | T =GK(I |     | +GK) | −1  |     |     |
| --- | --- | --- | ------- | --- | ---- | --- | --- | --- |
yr
|     |     |     | =G(I | +KG) |     | −1  |     |     |
| --- | --- | --- | ---- | ---- | --- | --- | --- | --- |
T yd
(1.6)
|     |     |     | T =K(I | +GK) |     | −1  |     |     |
| --- | --- | --- | ------ | ---- | --- | --- | --- | --- |
ur
|     |     |     | =−KG(I |     | +KG) | −1  |     |     |
| --- | --- | --- | ------ | --- | ---- | --- | --- | --- |
T ud
Hence,the system is internallystable if and onlyif all thet(cid:4)ran(cid:5)sfer(cid:4)fu(cid:5)nctionsin
(1.6)areBIBOstable,orthetransferfunctionmatrixM from r to y isBIBO
|     |     |     |     |     |     |     | d u |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
stable,where
|     |     | (cid:2) |      |     |     |      | (cid:3) |     |
| --- | --- | ------- | ---- | --- | --- | ---- | ------- | --- |
|     |     | GK(I    | +GK) | −1  | G(I | +KG) | −1      |     |
M:=
|     |     |     | +GK) | −1  | −KG(I | +KG) | −1  | (1.7) |
| --- | --- | --- | ---- | --- | ----- | ---- | --- | ----- |
K(I
Thestabilityof(1.7)isequivalenttothestabilityof
|     |      | (cid:2) |        |         |     |        | (cid:3)        |       |
| --- | ---- | ------- | ------ | ------- | --- | ------ | -------------- | ----- |
|     |      |         |        |         | −1  |        | −              |       |
|     | ˆ    | I − G   | K (I + | G K )   |     | −G ( I | + KG ) 1       |       |
|     | M := |         |        |         |     |        |                | (1.8) |
|     |      | K       | (I + G | K ) − 1 | I   | − K G  | ( I + K G ) −1 |       |
Bysimplematrixmanipulations,wehave
|     |     | (cid:2) |          |         |      |      | (cid:3) |     |
| --- | --- | ------- | -------- | ------- | ---- | ---- | ------- | --- |
|     |     |         | +GK)     | −1      | −G(I | +KG) | −1      |     |
|     |     | ˆ =     | (I       |         |      |      |         |     |
|     |     | M       |          | −1      |      |      | −1      |     |
|     |     |         | K(I +GK) |         | (I   | +KG) |         |     |
|     |     | (cid:2) |          | (cid:3) |      |      |         |     |
−1
|     |     | =   | I   | G   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
(1.9)
−K I
Hence,thefeedbacksysteminFig.1.1isinternallystableif(1.9)isstable.
Itcanbeshown[27]thatifthereis nounstablepole/zerocancellationbetween
G and K,thenanyoneofthefourtransferfunctionsbeingBIBOstablewouldbe
enoughtoguaranteethatthewholesystemisinternallystable.
| 1.3 CoprimeFactorizationand |     |     |     |     | StabilizingControllers |     |     |     |
| --------------------------- | --- | --- | --- | --- | ---------------------- | --- | --- | --- |
Considerasystemgivenintheformof(1.2)with[A,B,C,D]assumedtobemin-
imal.Matrices(M ˜ (s),N ˜ (s))∈H ((M(s),N(s))∈H ∞),whereH denotesthe
|     |     |     |     | ∞   |     |     | ∞   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
spaceoffunctionswithnopolesintheclosedright-halfcomplexplane,constitutea
left(right)coprimefactorizationofG(s)ifandonlyif
| ˜   |     |     | ˜   | )(det(M))(cid:3)=0 |     |     |     |     |
| --- | --- | --- | --- | ------------------ | --- | --- | --- | --- |
(i) M (M)issquare,anddet(M
(ii) theplantmodelisgivenby
|     |     |     |     |      | (cid:6) |     | (cid:7) |        |
| --- | --- | --- | --- | ---- | ------- | --- | ------- | ------ |
|     |     |     |     | ˜−1N | ˜       | −1  |         |        |
|     |     |     | G=M |      | =NM     |     |         | (1.10) |
˜ ˜ )((V,U))∈H
| (iii) Thereexists(V |     | ,U  |     | ∞   | suchthat |     |     |        |
| ------------------- | --- | --- | --- | --- | -------- | --- | --- | ------ |
|                     |     |     |     | ˜ ˜ | +N ˜ ˜   | =I  |     |        |
|                     |     |     |     | M V | U        |     |     | (1.11) |
(UN+VM=I)

| 8   |     |     |     |     |     | 1   | Introduction |
| --- | --- | --- | --- | --- | --- | --- | ------------ |
Transferfunctions(orrational,fractional)matricesarecoprimeiftheyshareno
common zeros in the right-half complex plane, including at the infinity. The two
equationsin(iii)abovearecalledBezoutidentities[108]andarenecessaryandsuf-
|     |     | ˜   | ˜   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
ficientconditionsfor(M,N)((M,N))beingleftcoprime(rightcoprime),respec-
tively.TheleftandrightcoprimefactorizationsofG(s)canbegroupedtogetherto
formaBezoutdoubleidentityasthefollowing:
|     |     |     | (cid:2) | (cid:3)(cid:2) | (cid:3) |     |     |
| --- | --- | --- | ------- | -------------- | ------- | --- | --- |
˜
|     |     |     | V    | U M | −U  |     |        |
| --- | --- | --- | ---- | --- | --- | --- | ------ |
|     |     |     |      |     | =I  |     | (1.12) |
|     |     |     | −N ˜ | ˜   | ˜   |     |        |
|     |     |     |      | M N | V   |     |        |
For G(s) of minimal realization (1.2) (actually G is required to be stabilizable
and detectable only), the formulas for the coprime factors can be readily derived
[109]asinthefollowingtheorem.
|            |                      |     |     |      | besuchthatA+BF | andA+HC |     |
| ---------- | -------------------- | --- | --- | ---- | -------------- | ------- | --- |
| Theorem1.1 | LetconstantmatricesF |     |     | andH |                |         |     |
|            |                      |     |     |      |                | ˜ ˜     |     |
arebothstable.Thenthetransferfunctionmatrices M and N (M and N)defined
inthefollowingconstitutealeft(right)coprimefactorizationofG(s):
|     |     |         |         | (cid:2)      |      | (cid:3) |        |
| --- | --- | ------- | ------- | ------------ | ---- | ------- | ------ |
|     |     | (cid:4) |         | (cid:5) A+HC | B+HD | −H      |        |
|     |     | ˜       | ˜       |              |      |         |        |
|     |     | N (s)   | M (s)   | =            |      |         | (1.13) |
|     |     |         |         | C            | D    | I       |        |
|     |     |         |         | ⎡            | ⎤    |         |        |
|     |     | (cid:2) | (cid:3) | A+BF         | B    |         |        |
|     |     |         | N(s)    | =⎣ C+DF      | ⎦    |         |        |
|     |     |         |         |              | D    |         | (1.14) |
M(s)
|     |     |     |     | F   | I   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     | ˜   | ˜   |     |     |     |
Furthermore,thefollowingU(s),V(s),U(s),andV(s)satisfytheBezoutdouble
identity(1.12):
|     |     |         |         | (cid:2)      |     | (cid:3) |        |
| --- | --- | ------- | ------- | ------------ | --- | ------- | ------ |
|     |     | (cid:4) |         | (cid:5)      |     |         |        |
|     |     | ˜       | ˜       | A+HC         | H   | B+HD    |        |
|     |     | U (s)   | V (s)   | =            |     |         | (1.15) |
|     |     |         |         | F            | 0   | I       |        |
|     |     |         |         | ⎡            | ⎤   |         |        |
|     |     |         | (cid:2) | (cid:3) A+BF |     |         |        |
H
|     |     |     | U(s) | =⎣  | ⎦   |     |        |
| --- | --- | --- | ---- | --- | --- | --- | ------ |
|     |     |     |      | F   | 0   |     | (1.16) |
V(s)
|                                                                 |     |     |     | C+DF | I   |     |     |
| --------------------------------------------------------------- | --- | --- | --- | ---- | --- | --- | --- |
| Itcanbeeasilyshownthatthepairs(U,V)and(U,V)arestableandcoprime. |     |     |     | ˜    | ˜   |     |     |
Using(1.9),itisstraightforwardtoshowthefollowinglemma.
Lemma1.2
|     |     |     | K:=V | ˜−1U ˜ | =UV −1 |     | (1.17) |
| --- | --- | --- | ---- | ------ | ------ | --- | ------ |
isastabilizingcontroller,i.e.theclosed-loopsysteminFig.1.6isinternallystable.
|          |         |        |             |             |     | G=M ˜−1N ˜ =NM | −1     |
| -------- | ------- | ------ | ----------- | ----------- | --- | -------------- | ------ |
| Further, | the set | of all | stabilizing | controllers | for |                | can be |
obtainedinthefollowingYoulaParameterizationTheorem[109,189,190].
| Theorem1.3 | ThesetofallstabilizingcontrollersforGis |                 |     |                 |         |          |        |
| ---------- | --------------------------------------- | --------------- | --- | --------------- | ------- | -------- | ------ |
|            |                                         | (cid:12)(cid:6) |     | (cid:7) (cid:6) | (cid:7) | (cid:13) |        |
|            |                                         | ˜               | +QN | ˜ −1 ˜ +QM      | ˜ :Q∈H  |          |        |
|            |                                         | V               |     | U               |         | ∞        | (1.18) |

| 1.4 SignalsandSystemNorms |     |     |     |     |     |     | 9   |
| ------------------------- | --- | --- | --- | --- | --- | --- | --- |
Thesetcanalsobeexpressedas
|                      |     | (cid:12) |        |      |        | (cid:13) |        |
| -------------------- | --- | -------- | ------ | ---- | ------ | -------- | ------ |
|                      |     | (U       | +MQ)(V | +NQ) | −1:Q∈H |          |        |
|                      |     |          |        |      |        | ∞        | (1.19) |
| 1.4 SignalsandSystem |     |          | Norms  |      |        |          |        |
Inthissectionthebasicconceptsconcerningsignalsandsystemswillbereviewed
inbrief.Acontrolsysteminteractswithitsenvironmentthroughcommandsignals,
disturbancesignalsandnoisesignals,etc.Trackingerrorsignalsandactuatordriv-
ingsignalsarealsoimportantincontrolsystemsdesign.Forthepurposeofanalysis
and design, appropriate measures, the norms, must be defined for describing the
“size”ofthesesignals.Fromthesignalnorms,wecanthendefineinducednormsto
measurethe“gain”oftheoperatorthatrepresentsthecontrolsystem.
1.4.1 VectorNormsandSignalNorms
LetthelinearspaceXbeFm,whereF =Rforthefieldofrealnumbers,orF =C
| forcomplexnumbers.Forx=[x |     |     |     |               | ]T ∈X,thep-normofthevectorx |     |     |
| ------------------------- | --- | --- | --- | ------------- | --------------------------- | --- | --- |
|                           |     |     |     | 1 ,x 2 ,...,x | m                           |     | is  |
definedby
(cid:14)m
|     |        |     | (cid:5)x(cid:5) := | |x |, |     | forp=1 |     |
| --- | ------ | --- | ------------------ | ----- | --- | ------ | --- |
|     | 1-norm |     | 1                  | i     |     |        |     |
i(cid:15) =1
(cid:16)
|     |        |     |                    | (cid:14)m | 1/p |          |     |
| --- | ------ | --- | ------------------ | --------- | --- | -------- | --- |
|     |        |     | (cid:5)x(cid:5) := | |x        | |p  | for1<p<∞ |     |
|     | p-norm |     | p                  | i         | ,   |          |     |
i=1
|     | ∞-norm |     | (cid:5)x(cid:5) := | max |x | |,  | forp=∞ |     |
| --- | ------ | --- | ------------------ | ------ | --- | ------ | --- |
|     |        |     | ∞                  |        | i   |        |     |
1≤i≤m
Whenp=2,(cid:5)x(cid:5)
isthefamiliarEuclideannorm.
2
When X is a linear space of continuous or piecewise continuous time scalar-
valuedsignalsx(t),t∈R,thep-normofasignalx(t)isdefinedby
(cid:17)
|     |        |                 |     | ∞(cid:18) (cid:18)         |     |        |     |
| --- | ------ | --------------- | --- | -------------------------- | --- | ------ | --- |
|     | 1-norm | (cid:5)x(cid:5) | :=  | (cid:18) x(t) (cid:18) dt, |     | forp=1 |     |
1
−∞
|     |        |                 | (cid:19)(cid:17) |           | (cid:20)     |          |     |
| --- | ------ | --------------- | ---------------- | --------- | ------------ | -------- | --- |
|     |        |                 |                  | ∞(cid:18) | (cid:18) 1/p |          |     |
|     |        | (cid:5)x(cid:5) | :=               | (cid:18)  | (cid:18)p    | for1<p<∞ |     |
|     | p-norm |                 |                  | x(t)      | dt           | ,        |     |
p
−∞
|     |        |                 |       | (cid:18) (cid:18) |     |        |     |
| --- | ------ | --------------- | ----- | ----------------- | --- | ------ | --- |
|     | ∞-norm | (cid:5)x(cid:5) | :=sup | (cid:18) (cid:18) |     | forp=∞ |     |
|     |        |                 | ∞     | x(t) ,            |     |        |     |
t∈R
Thenormedspaces,consistingofsignalswithfinitenormasdefinedcorrespond-
|        | L1(R),     |     | Lp(R), | ∞ (R), |               |               |          |
| ------ | ---------- | --- | ------ | ------ | ------------- | ------------- | -------- |
| ingly, | are called |     |        | and L  | respectively. | From a signal | point of |
view, the 1-norm, (cid:5)x(cid:5) of the signal x(t) is the integral of its absolute value. The
1
(cid:5)x(cid:5)2,isoftencalledtheenergyofthesignal
| squareofthe2-norm, |     |     |     |     |     | x(t) | sincethat |
| ------------------ | --- | --- | --- | --- | --- | ---- | --------- |
2

| 10  |     |     |     |     | 1   | Introduction |
| --- | --- | --- | --- | --- | --- | ------------ |
iswhatitiswhenx(t)isthecurrentthrougha1(cid:2)resistor.The∞-norm,(cid:5)x(cid:5)
∞,is
theamplitudeorpeakvalueofthesignal,andthesignalisboundedinmagnitudeif
x(t)∈L ∞ (R).
When X is a linear space of continuous or piecewise continuous vector-valued
functionsoftheformx(t)=[x (t),x (t),...,x (t)]T,t∈R,wemayhave
|     |          | 1        | 2           |          | m        |          |
| --- | -------- | -------- | ----------- | -------- | -------- | -------- |
|     | (cid:21) | (cid:15) |             |          | (cid:16) | (cid:22) |
|     |          |          | (cid:17)    |          | 1/p      |          |
|     |          |          | ∞ (cid:14)m | (cid:18) | (cid:18) |          |
p (R):= x(t):(cid:5)x(cid:5) = (cid:18) (cid:18)p <∞,for1≤p<∞
| L       |                      |      |          | x (t)       | dt       |     |
| ------- | -------------------- | ---- | -------- | ----------- | -------- | --- |
| m       |                      | p    |          | i           |          |     |
|         |                      |      | −∞ i=1   |             |          |     |
|         | (cid:23)             |      |          |             | (cid:25) |     |
|         |                      |      | (cid:24) | (cid:24)    |          |     |
| ∞ (R):= | x(t):(cid:5)x(cid:5) | =sup | (cid:24) | (cid:24) <∞ |          |     |
| L       |                      | ∞    | x(t)     |             |          |     |
| m       |                      |      |          | ∞           |          |     |
t∈R
Some signals are useful for control systems analysis and design, for example,
thesinusoidalsignal,x(t)=Asin(ωt+φ),t ∈R.Itisunfortunatelynota2-norm
signalbecauseoftheinfiniteenergycontained.However,theaveragepowerofx(t)
(cid:17)
T
1
|     |     |     | lim | x2(t)dt |     |     |
| --- | --- | --- | --- | ------- | --- | --- |
T→∞2T
−T
exists. The signal x(t) will be called a power signal if the above limit exists. The
squarerootofthelimitisthewell-knownr.m.s.(root-mean-square)valueofx(t).It
shouldbenoticedthattheaveragepowerdoesnotintroduceanorm,sinceanonzero
signalmayhavezeroaveragepower.
1.4.2 SystemNorms
Systemnormsareactuallytheinput–outputgainsofthesystem.SupposethatG
is
alinearandboundedsystemthatmapstheinputsignal u(t) intotheoutputsignal
y(t),whereu∈(U,(cid:5)·(cid:5) ),y∈(Y,(cid:5)·(cid:5) ).U andY arethesignalspaces,endowed
|     |                 | U               |     | Y   |     |     |
| --- | --------------- | --------------- | --- | --- | --- | --- |
|     | (cid:5)·(cid:5) | (cid:5)·(cid:5) |     |     |     |     |
with the norms U and Y , respectively. Then the norm, maximum system
gain,ofG isdefinedas
(cid:5)Gu(cid:5)
|     |     |     | (cid:5)G(cid:5):=sup |     | Y   |     |
| --- | --- | --- | -------------------- | --- | --- | --- |
(1.20)
(cid:5)u(cid:5)
|     |     |     |     | u(cid:3)=0 | U   |     |
| --- | --- | --- | --- | ---------- | --- | --- |
or
|     |     | (cid:5)G(cid:5)= sup | (cid:5)Gu(cid:5) | =               | sup (cid:5)Gu(cid:5) |     |
| --- | --- | -------------------- | ---------------- | --------------- | -------------------- | --- |
|     |     |                      |                  | Y               | Y                    |     |
|     |     | (cid:5)u(cid:5)      | =1               | (cid:5)u(cid:5) | ≤1                   |     |
|     |     |                      | U                |                 | U                    |     |
Obviously,wehave
|     |     | (cid:5)Gu(cid:5) | ≤(cid:5)G(cid:5)·(cid:5)u(cid:5) |     |     |     |
| --- | --- | ---------------- | -------------------------------- | --- | --- | --- |
|     |     |                  | Y                                |     | U   |     |
IfG andG aretwolinear,boundedandcompatiblesystems,then
1 2
|                 |     | (cid:5)G | G (cid:5)≤(cid:5)G | (cid:5)·(cid:5)G | (cid:5) |                 |
| --------------- | --- | -------- | ------------------ | ---------------- | ------- | --------------- |
|                 |     |          | 1 2                | 1                | 2       |                 |
| (cid:5)G(cid:5) |     |          |                    | G                |         | (cid:5)·(cid:5) |
is called the induced norm of with regard to the signal norms U
| (cid:5)·(cid:5) |     |     |     |     |     | ∞-norm |
| --------------- | --- | --- | --- | --- | --- | ------ |
and . In this book, we are particularly interested in the so-called
Y

| 1.4 SignalsandSystemNorms |     |     |     |              | 11  |
| ------------------------- | --- | --- | --- | ------------ | --- |
|                           |     |     | G:  | L2(R)→L2(R), |     |
of a system. For a linear, time-invariant, stable system m p the
| ∞-norm,ortheinduced2-norm,ofG |                 | isgivenby |                   |     |        |
| ----------------------------- | --------------- | --------- | ----------------- | --- | ------ |
|                               |                 |           | (cid:24) (cid:24) |     |        |
|                               |                 |           | (cid:24) (cid:24) |     |        |
|                               | (cid:5)G(cid:5) | ∞ = sup   | G(jω)             |     | (1.21) |
2
ω∈R
| (cid:5)G(jω)(cid:5) |                 |         | ×m           |       |             |
| ------------------- | --------------- | ------- | ------------ | ----- | ----------- |
| where               | is the spectral | norm of | the p matrix | G(jω) | and G(s) is |
2
the transfer function matrix of G. Hence, the ∞-norm of a system describes the
maximumenergygainofthesystemandisdecidedbythepeakvalueofthelargest
singularvalueofthefrequencyresponsematrixoverthewholefrequencyaxis.This
normiscalledtheH ∞-norm,sincewedenotebyH thelinearspaceofallstable
∞
linearsystems.

Chapter 2
Modeling of Uncertain Systems
As discussed in Chap. 1, it is well understood that uncertainties are unavoidable
inarealcontrolsystem.Theuncertaintycanbeclassifiedintotwocategories:dis-
turbancesignalsanddynamicperturbations.Theformerincludesinputandoutput
disturbance (such as a gust on an aircraft), sensor noise and actuator noise, etc.
Thelatterrepresents thediscrepancybetweenthemathematicalmodelandtheac-
tualdynamicsofthesysteminoperation.Amathematicalmodelofanyrealsystem
is always just an approximation of the true, physical reality of the system dynam-
ics.Typicalsourcesofthediscrepancyincludeunmodeled(usuallyhigh-frequency)
dynamics, neglected nonlinearities in the modeling, effects of deliberate reduced-
order models, and system-parameter variations due to environmental changes and
torn-and-wornfactors.Thesemodelingerrorsmayadverselyaffectthestabilityand
performanceofacontrolsystem.Inthischapter,wewilldiscussindetailhowdy-
namicperturbationsareusuallydescribedsothattheycanbeaccountedforinsys-
temrobustnessanalysisanddesign.
2.1 Unstructured Uncertainties
Manydynamicperturbationsthatmayoccurindifferentpartsofasystemcan,how-
ever,belumpedintoonesingleperturbationblockΔ,forinstance,someunmodeled,
high-frequencydynamics.Thisuncertaintyrepresentationisreferredtoas“unstruc-
tured” uncertainty. In the case of linear, time-invariant systems, the block Δ may
berepresentedbyanunknowntransferfunctionmatrix.Theunstructureddynamics
uncertaintyinacontrolsystemcanbedescribedindifferentways,suchasislisted
in the following, where G (s) denotes the actual, perturbed system dynamics and
p
G (s)anominalmodeldescriptionofthephysicalsystem.
o
1. Additiveperturbation(seeFig.2.1):
G (s)=G (s)+Δ(s) (2.1)
p o
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 13
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_2,©Springer-VerlagLondon2013

14 2 ModelingofUncertainSystems
Fig.2.1 Additive
perturbationconfiguration
Fig.2.2 Inverseadditive
perturbationconfiguration
Fig.2.3 Inputmultiplicative
perturbationconfiguration
Fig.2.4 Output
multiplicativeperturbation
configuration
Fig.2.5 Inverseinput
multiplicativeperturbation
configuration
2. Inverseadditiveperturbation(seeFig.2.2):
| (cid:6) | (cid:7) (cid:6) | (cid:7) |         |       |
| ------- | --------------- | ------- | ------- | ----- |
|         | −1=             |         | −1+Δ(s) |       |
| G (s)   |                 | G (s)   |         | (2.2) |
| p       |                 | o       |         |       |
3. Inputmultiplicativeperturbation(seeFig.2.3):
|       |     | (cid:4) | (cid:5) |       |
| ----- | --- | ------- | ------- | ----- |
| (s)=G |     | +Δ(s)   |         |       |
| G p   | o   | (s) I   |         | (2.3) |
4. Outputmultiplicativeperturbation(seeFig.2.4):
|      | (cid:4) |       | (cid:5) |       |
| ---- | ------- | ----- | ------- | ----- |
| (s)= |         | +Δ(s) |         |       |
| G    | I       |       | G (s)   | (2.4) |
| p    |         |       | o       |       |
5. Inverseinputmultiplicativeperturbation(seeFig.2.5):
| (cid:6) (cid:7) | (cid:4) |       | (cid:5)(cid:6) (cid:7) |       |
| --------------- | ------- | ----- | ---------------------- | ----- |
| −1=             |         | +Δ(s) | −1                     |       |
| G p (s)         | I       |       | G o (s)                | (2.5) |

2.1 UnstructuredUncertainties 15
Fig.2.6 Inverseoutput
multiplicativeperturbation
configuration
Fig.2.7 Leftcoprimefactor
perturbationsconfiguration
Fig.2.8 Rightcoprime
factorperturbations
configuration
6. Inverseoutputmultiplicativeperturbation(seeFig.2.6):
| (cid:6) (cid:7) | (cid:6) (cid:7) | (cid:4) | (cid:5) |       |
| --------------- | --------------- | ------- | ------- | ----- |
|                 | −1= −1          | +Δ(s)   |         |       |
| G (s)           | G (s)           | I       |         | (2.6) |
| p               | o               |         |         |       |
7. Leftcoprimefactorperturbations(seeFig.2.7):
|          | ˜ −1(N | ˜     |     |       |
| -------- | ------ | ----- | --- | ----- |
| G (s)=(M | +Δ ˜)  | +Δ ˜) |     | (2.7) |
| p        | M      | N     |     |       |
8. Rightcoprimefactorperturbations(seeFig.2.8):
| (s)=(N+Δ | )(M+Δ | −1  |     |       |
| -------- | ----- | --- | --- | ----- |
| G p      | N     | M ) |     | (2.8) |
The additive uncertainty representations give an account of absolute error be-
tween the actual dynamics and the nominal model, while the multiplicative repre-
sentationsshowrelativeerrors.
Inthelasttworepresentations,(M,N)/(M,N)areleft/rightcoprimefactoriza- ˜ ˜
tionsofthenominalsystemmodelG (s),respectively;and(Δ ˜,Δ ˜)/(Δ ,Δ )
|     | o   |     | M N | M N |
| --- | --- | --- | --- | --- |
aretheperturbationsonthecorrespondingfactors[111].
The block Δ (or, (Δ ˜,Δ ˜)/(Δ M ,Δ N ) in the coprime factor perturbations
M N
cases) is uncertain, but usually is norm-bounded. It may be bounded by a known
transferfunction,sayσ[Δ(jω)]≤δ(jω),forallfrequenciesω,whereδisaknown
σ[·]
scalar function and denotes the largest singular value of a matrix. The uncer-
tainty can thus be represented by a unit, norm-bounded block Δ cascaded with a
scalartransferfunctionδ(s).
Itshouldbenotedthatasuccessfulrobustcontrol-systemdesignwoulddepend
on, to a certain extent, an appropriate description of the perturbation considered,
thoughtheoreticallymostrepresentationsareinterchangeable.

16 2 ModelingofUncertainSystems
Fig.2.9 AbsoluteandrelativeerrorsinExample2.1
Example2.1 Thedynamicsofmanycontrolsystemsmayincludea“slow”partand
a“fast”part,forinstanceinadcmotor.Theactualdynamicsofascalarplantmay
be
|     | G   | (s)=g | G (s)G    | (s)  |     |
| --- | --- | ----- | --------- | ---- | --- |
|     |     | p     | gain slow | fast |     |
whereg isconstant,and
gain
|        |      | 1   |        | 1     |           |
| ------ | ---- | --- | ------ | ----- | --------- |
| (s)=   |      | ;   | (s)=   |       | α(cid:8)1 |
| G slow |      |     | G fast |       | ,         |
|        | 1+sT |     |        | 1+αsT |           |
Inthedesign,itmaybereasonabletoconcentrateontheslowresponsepartwhile
treating the fast response dynamics as a perturbation. Let Δ and Δ denote the
|     |     |     |     |     | a m |
| --- | --- | --- | --- | --- | --- |
additive and multiplicative perturbations, respectively. It can easily be worked out
that
| (s)=G |     | −g   | =g          |           | −1)  |
| ----- | --- | ---- | ----------- | --------- | ---- |
| Δ a   | p   | gain | G slow gain | G slow (G | fast |
−αsT
=g
gain
(1+sT)(1+αsT)
|        |     | −g   |        |     | −αsT  |
| ------ | --- | ---- | ------ | --- | ----- |
|        | G p | gain | G slow |     |       |
| Δ (s)= |     |      | =G     | −1= |       |
| m      |     |      | fast   |     | 1+αsT |
g gain G slow
The magnitude Bode plots of Δ a and Δ m can be seen in Fig. 2.9, where g gain
isassumedtobe1.Thedifferencebetweenthetwoperturbationrepresentationsis
obvious:thoughthemagnitudeoftheabsoluteerrormaybesmall,therelativeerror
canbelargeinthehigh-frequencyrangeincomparisontothatofthenominalplant.

| 2.2 ParametricUncertainty |     |     |     |     |     |     |     | 17  |
| ------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
2.2 ParametricUncertainty
The unstructured uncertainty representations discussed in Sect. 2.1 are useful in
describingunmodeledorneglectedsystemdynamics.Thesecomplexuncertainties
usually occur in the high-frequency range and may include unmodeled lags (time
delay), parasitic coupling, hysteresis, and other nonlinearities. However, dynamic
perturbationsinmanyindustrialcontrolsystemsmayalsobecausedbyinaccurate
description of component characteristics, torn-and-worn effects on plant compo-
nents,orshiftingofoperatingpoints,etc.Suchperturbationsmayberepresentedby
variationsofcertainsystemparametersoversomepossiblevalueranges(complexor
real).Theyaffectthelow-frequencyrangeperformanceandarecalled“parametric
uncertainties”.
Example2.2 Amass–spring–dampersystemcanbedescribedbythefollowingsec-
ondorder,ordinarydifferentialequation:
|     |     |     | d2x(t) | dx(t) |             |     |     |     |
| --- | --- | --- | ------ | ----- | ----------- | --- | --- | --- |
|     |     |     |        | +c    | +kx(t)=f(t) |     |     |     |
m
|     |     |     | dt2 | dt  |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
where m is the mass, c the damping constant, k the spring stiffness, x(t) the dis-
placementandf(t)theexternalforce.Forimpreciselyknownparametervalues,the
dynamicbehaviorofsuchasystemisactuallydescribedby
|     |     | d2x(t) |     |      | dx(t) |               |     |       |
| --- | --- | ------ | --- | ---- | ----- | ------------- | --- | ----- |
|     | (m  | +δ )   | +(c | +δ ) | +(k   | +δ )x(t)=f(t) |     | (2.9) |
|     |     | o m    |     | o c  |       | o k           |     |       |
|     |     | dt2    |     |      | dt    |               |     |       |
wherem ,c ,andk denotethenominalparametervaluesandδ ,δ andδ possible
|     | o o | o   |     |     |     |     | m c | k   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
variationsovercertainranges.
By defining the state variables x 1 and x 2 as the displacement variable and its
firstorderderivative(velocity),thesecondorderdifferentialequation(2.9)maybe
rewrittenintoastandardstate-spaceform
x˙ =x
|     |     | 1 2 |         |     |     |     |         |     |
| --- | --- | --- | ------- | --- | --- | --- | ------- | --- |
|     |     |     | (cid:4) |     |     |     | (cid:5) |     |
1
|     |     | x˙ = |     | −(k +δ | )x −(c | +δ )x +f |     |     |
| --- | --- | ---- | --- | ------ | ------ | -------- | --- | --- |
|     |     | 2 m  | +δ  | o      | k 1    | o c 2    |     |     |
|     |     | o    | m   |        |        |          |     |     |
y=x
1
Further,thesystemcanberepresentedbyananalogblockdiagramasinFig.2.10.
Noticethat 1 canberearrangedasafeedbackintermsof 1 andδ .Fig-
|     |     | mo +δm |     |     |     |     | mo  | m   |
| --- | --- | ------ | --- | --- | --- | --- | --- | --- |
ure2.10canberedrawnasinFig.2.11,bypullingoutalltheuncertainvariations.
Letz ,z ,andz bex˙ ,x ,andx ,respectively,consideredasanother,fictitious
|     | 1 2 | 3   | 2 2 | 1   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
outputvector;and, d , d ,and d bethesignalscomingoutfromtheperturbation
|     |     | 1 2 |     | 3   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
blocksδ m ,δ c ,andδ k ,asshowninFig.2.11.Theperturbedsystemcanbearranged
inthefollowingstate-spacemodelandrepresentedasinFig.2.12:
|     |     |     |     |     |     | ⎡ ⎤ |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
(cid:2) (cid:3) (cid:2) (cid:3)(cid:2) (cid:3) (cid:2) (cid:3) (cid:2) (cid:3)
d 1
| x˙  |     | 0 1     | x   | 0   | 0     | 0 ⎣ ⎦+ | 0   |     |
| --- | --- | ------- | --- | --- | ----- | ------ | --- | --- |
| 1   | =   |         | 1   | +   |       | d      | f   |     |
| x˙  |     | −ko −co | x   | −1  | −1 −1 | 2      | 1   |     |
| 2   |     | mo mo   | 2   |     |       |        | mo  |     |
d 3

| 18  |     |     |     |     | 2 ModelingofUncertainSystems |     |
| --- | --- | --- | --- | --- | ---------------------------- | --- |
Fig.2.10 AnalogblockdiagramofExample2.2
Fig.2.11 StructureduncertaintiesblockdiagramofExample2.2
| ⎡ ⎤   | ⎡       |                 | ⎤               | ⎡     | ⎤⎡ ⎤    | ⎡ ⎤        |
| ----- | ------- | --------------- | --------------- | ----- | ------- | ---------- |
|       | −ko     | −co             | (cid:2) (cid:3) | −1 −1 | −1      | 1          |
| z 1   |         |                 |                 |       | d 1     |            |
| ⎣ ⎦=⎣ | mo      | mo⎦             | x +⎣            |       | ⎦⎣ ⎦+⎣m | o⎦         |
| z     | 0       | 1               | 1               | 0 0   | 0 d     | 0 f (2.10) |
| 2     |         |                 | x               |       | 2       |            |
| z     |         |                 | 2               |       | d       |            |
| 3     | 1       | 0               |                 | 0 0   | 0 3     | 0          |
|       |         | (cid:2) (cid:3) |                 |       |         |            |
|       | (cid:4) | (cid:5)         |                 |       |         |            |
x
| y=  | 1 0 | 1   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
x
2
Thestate-spacemodelof(2.10)describestheaugmented,interconnectionsystem
M of Fig. 2.12. The perturbation block Δ in Fig. 2.12 corresponds to parameter
variations and is called “parametric uncertainty”. The uncertain block Δ is not a
full matrix but a diagonal one. It has certain structure, hence the terminology of
“structureduncertainty”.MoregeneralcaseswillbediscussedshortlyinSect.2.4.

2.3 LinearFractionalTransformations 19
Fig.2.12 Standard
configurationofExample2.2
Fig.2.13 StandardM–Δ
configuration
2.3 LinearFractionalTransformations
The block diagram in Fig. 2.12 can be generalized to be a standard configuration
torepresenthowtheuncertaintyaffectstheinput/outputrelationshipofthecontrol
systemunderstudy.Thiskindofrepresentationfirstappearedinthecircuitanalysis
backinthe1950s[140,141].Itwaslateradoptedintherobustcontrolstudy[145]
foruncertaintymodeling.ThegeneralframeworkisdepictedinFig.2.13.
TheinterconnectiontransferfunctionmatrixM inFig.2.13ispartitionedas
|     | (cid:2)      | (cid:3) |
| --- | ------------ | ------- |
|     | M= M 11 M 12 |         |
M M
|     | 21 22 |     |
| --- | ----- | --- |
wherethedimensionsofM conformwiththoseofΔ.Byroutinemanipulations,
11
itcanbederivedthat
| (cid:4) |           | (cid:5) |
| ------- | --------- | ------- |
| z= M    | +M Δ(I −M | Δ) −1M  |
| 22      | 21        | 11 12   |
−M
if(I 11 Δ)isinvertible.Whentheinverseexists,wemaydefine
−1M
| F(M,Δ)=M | +M Δ(I −M | Δ)    |
| -------- | --------- | ----- |
|          | 22 21     | 11 12 |
F(M,Δ) is called a linear fractional transformation (LFT) of M and Δ. Be-
causethe“upper”loopofM isclosedbytheblockΔ,thiskindoflinearfractional
transformationisalsocalledanupperlinearfractionaltransformation(ULFT),and
denotedwithasubscriptu,i.e.F (M,Δ),toshowthewayofconnection.Similarly,
u

20 2 ModelingofUncertainSystems
Fig.2.14 LowerLFT
configuration
therearealsolowerlinearfractionaltransformations(LLFT)thatareusuallyused
toindicatetheincorporationofacontrollerK intoasystem.SuchalowerLFTcan
bedepictedasinFig.2.14anddefinedby
| F(M,K)=M |     | +M    | −M  | −1M      |     |
| -------- | --- | ----- | --- | -------- | --- |
| l        |     | 11 12 | K(I | 22 K) 21 |     |
With the introduction of linear fractional transformations, the unstructured un-
certainty representations discussed in Sect. 2.1 may be uniformly described by
Fig.2.13,withappropriatelydefinedinterconnectionmatricesMsaslistedbelow.
1. Additiveperturbation:
|     |     | (cid:2) | (cid:3) |     |        |
| --- | --- | ------- | ------- | --- | ------ |
|     |     | 0       | I       |     |        |
|     |     | M=      |         |     | (2.11) |
|     |     | I       | G       |     |        |
o
2. Inverseadditiveperturbation:
|     |     | (cid:2) | (cid:3) |     |        |
| --- | --- | ------- | ------- | --- | ------ |
|     |     | −G      | G       |     |        |
|     |     | M=      | o o     |     |        |
|     |     | −G      |         |     | (2.12) |
|     |     |         | o G o   |     |        |
3. Inputmultiplicativeperturbation:
|     |     | (cid:2) | (cid:3) |     |        |
| --- | --- | ------- | ------- | --- | ------ |
|     |     | 0       | I       |     |        |
|     |     | M=      |         |     | (2.13) |
|     |     | G       | G       |     |        |
|     |     |         | o o     |     |        |
4. Outputmultiplicativeperturbation:
|     |     | (cid:2) | (cid:3) |     |        |
| --- | --- | ------- | ------- | --- | ------ |
|     |     | 0       | G       |     |        |
|     |     | M=      | o       |     | (2.14) |
|     |     | I       | G o     |     |        |
5. Inverseinputmultiplicativeperturbation:
|     |     | (cid:2) | (cid:3) |     |     |
| --- | --- | ------- | ------- | --- | --- |
−I
|     |     | M=  | I   |     |     |
| --- | --- | --- | --- | --- | --- |
(2.15)
|     |     | −G  | G   |     |     |
| --- | --- | --- | --- | --- | --- |
|     |     |     | o o |     |     |
6. Inverseoutputmultiplicativeperturbation:
|     |     | (cid:2) | (cid:3) |     |        |
| --- | --- | ------- | ------- | --- | ------ |
|     |     | −I      | G       |     |        |
|     |     | M=      | o       |     | (2.16) |
|     |     | −I      | G       |     |        |
o
7. Leftcoprimefactorperturbations:
|     |     | ⎡(cid:2) | (cid:3) (cid:2) | (cid:3)⎤ |     |
| --- | --- | -------- | --------------- | -------- | --- |
|     |     | −M ˜ −1  | − G             |          |     |
o
|     | M=⎣ | G   |     | ⎦   |        |
| --- | --- | --- | --- | --- | ------ |
|     |     | 0   | I   |     | (2.17) |
˜−1
|     |     | M   | G   | o   |     |
| --- | --- | --- | --- | --- | --- |
G

2.4 StructuredUncertainties 21
=M ˜−1N ˜
whereG o G ,aleftcoprimefactorizationofthenominalplant;and,the
|                   | G ˜ | ˜          |        |     |
| ----------------- | --- | ---------- | ------ | --- |
| perturbedplantisG | =(M | +Δ ˜) −1(N | +Δ ˜). |     |
|                   | p G | M G        | N      |     |
8. Rightcoprimefactorperturbations:
|     |     | (cid:2)(cid:4)   | (cid:5) (cid:3) |        |
| --- | --- | ---------------- | --------------- | ------ |
|     |     | −M −1            | −1              |        |
|     | M=  | (cid:4) 0(cid:5) | M               |        |
|     |     | G                | G               | (2.18) |
|     |     | −G I             | G               |        |
|     |     | o                | o               |        |
−1,arightcoprimefactorizationofthenominalplant;and,
| whereG =N            | M   |        |          |     |
| -------------------- | --- | ------ | -------- | --- |
| o                    | G G |        |          |     |
| theperturbedplantisG | =(N | +Δ )(M | +Δ ) −1. |     |
|                      | p   | G N G  | M        |     |
Intheabove,itisassumedthat[I −M Δ]isinvertible.Theperturbedsystem
11
isthus
G (s)=F (M,Δ)
p u
=
In the coprime(cid:4)facto(cid:5)r perturbation representations, (2.17) and (2.18), Δ
[Δ Δ ] and Δ= Δ M , respectively. The block Δ in (2.11)–(2.18) is supposed
| M˜ N˜ | Δ   |     |     |     |
| ----- | --- | --- | --- | --- |
N
tobea“full”matrix,i.e.ithasnospecificstructure.
| 2.4 Structured | Uncertainties |     |     |     |
| -------------- | ------------- | --- | --- | --- |
Inmanyrobustdesignproblems,itismorelikelythattheuncertaintyscenarioisa
mixed case of those described in Sects. 2.1 and 2.2. The uncertainties under con-
siderationwouldincludeunstructureduncertainties,suchasunmodeleddynamics,
aswellasparametervariations.Alltheseuncertainpartsstillcanbetakenoutfrom
the dynamics and the whole system can be rearranged in a standard configuration
of(upper)linearfractionaltransformationF(M,Δ).TheuncertainblockΔwould
thenhavethefollowinggeneralform:
| Δ=diag[δ | I ,...,δ I | ,Δ ,...,Δ | ], δ ∈C,Δ ∈Cmj | ×mj (2.19) |
| -------- | ---------- | --------- | -------------- | ---------- |
|          | 1 r1 s     | rs 1 f    | i j            |            |
| (cid:26) | (cid:26)   |           |                |            |
where s r + f m =n with n is the dimension of the block Δ. We may
| i=1 i | j=1 j |     |     |     |
| ----- | ----- | --- | --- | --- |
define the set of such Δ as (cid:2). The total block Δ thus has two types of uncertain
block:s repeatedscalarblocksandf fullblocks.Theparametersδ oftherepeated
i
scalarblockscanberealnumbersonly,iffurtherinformationoftheuncertaintiesis
available. However, in the case of real numbers, the analysis and design would be
evenharder.Thefullblocksin(2.19)neednotbesquare,butbyrestrictingthemas
suchmakesthenotationmuchsimpler.
When a perturbed system is described by an LFT with the uncertain block of
(2.19), the Δ considered has a certain structure. It is thus called “structured un-
certainty”.Apparently,usingalumped,fullblocktomodeltheuncertaintyinsuch
cases,forinstanceinExample2.2,wouldleadtopessimisticanalysisofthesystem
behaviorandproduceconservativedesigns.

Chapter 3
Robust Design Specifications
Acontrolsystemisrobustifitremainsstableandobeyscertainperformancecriteria
inthepresenceofpossibleuncertaintiesasdiscussedinChap.2.Therobustdesign
istofindacontroller,foragivensystem,suchthattheclosed-loopsystemisrobust.
TheH ∞ optimizationapproachanditsrelatedapproaches,beingdevelopedinthe
last two decades and still an active research area, have been shown to be effective
and efficient robust design methods for linear, time-invariant control systems. We
willfirstintroduceinthischaptertheSmall-GainTheorem,whichplaysanimpor-
tant role in the H ∞ optimization methods, and then discuss the stabilization and
performancerequirementsinrobustdesignsusingtheH ∞ optimizationandrelated
ideas.
3.1 Small-GainTheoremand RobustStabilization
TheSmall-GainTheoremisofcentralimportanceinthederivationofmanystability
tests.Ingeneral,itprovidesonlyasufficientconditionforstabilityandistherefore
potentially conservative. The Small-Gain Theorem is applicable to general opera-
tors.Whatwillbeincludedhereis,however,aversionthatissuitableforthe H ∞
optimizationdesigns,andinthiscase,itisasufficientandnecessaryresult.
ConsiderthefeedbackconfigurationinFig.3.1,whereG (s)andG (s)arethe
1 2
transferfunctionmatricesofcorrespondinglinear,time-invariantsystems.Wethen
havethefollowingtheorem.
Theorem 3.1 [28] If G
1
(s) and G
2
(s) are stable, i.e. G
1
∈H ∞, G
2
∈H ∞, then
theclosed-loopsystemisinternallystableifandonlyif
(cid:5)G
1
G
2
(cid:5) ∞<1 and (cid:5)G
2
G
1
(cid:5) ∞<1
A closed-loop system of the plant G and controller K is robustly stable if it
remainsstableforallpossible,undercertaindefinition,perturbationsontheplant.
This implies, of course, that K is a stabilizing controller for the nominal plant G,
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 23
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_3,©Springer-VerlagLondon2013

| 24  |     |     | 3 RobustDesignSpecifications |     |     |
| --- | --- | --- | ---------------------------- | --- | --- |
Fig.3.1 Afeedback
configuration
Fig.3.2 Additive
perturbationconfiguration
since we always assume that the perturbation set includes zero (no perturbation).
LetusconsiderthecaseofadditiveperturbationasdepictedinFig.3.2,whereΔ(s)
istheperturbation,a“full”matrixunknownbutstable.
It is easy to work out that the transfer function from the signal v to u is
−1.Asmentionedearlier,thecontrollerK
| T =−K(I | +GK) |     |     | shouldstabilizethe |     |
| ------- | ---- | --- | --- | ------------------ | --- |
uv
nominalplantG.Hence,fromtheSmall-GainTheorem,wehavethefollowingthe-
orem.
Theorem3.2[17,121] ForstableΔ(s),theclosed-loopsystemisrobustlystableif
K(s)stabilizesthenominalplantandthefollowingholds:
|     |     | (cid:24)  | (cid:24)   |     |     |
| --- | --- | --------- | ---------- | --- | --- |
|     |     | (cid:24)  | −1(cid:24) |     |     |
|     |     | ΔK(I +GK) | <1         |     |     |
∞
and
|     |     | (cid:24)      | (cid:24)     |     |     |
| --- | --- | ------------- | ------------ | --- | --- |
|     |     | (cid:24) +GK) | −1Δ (cid:24) |     |     |
|     |     | K(I           | ∞ <1         |     |     |
or,inastrengthenedform,
|     |     | (cid:24) | (cid:24)     |     |       |
| --- | --- | -------- | ------------ | --- | ----- |
|     |     | (cid:24) | −1(cid:24) 1 |     |       |
|     |     | K(I +GK) | <            |     | (3.1) |
∞ (cid:5)Δ(cid:5)
∞
Thesecondconditionbecomesnecessary,whentheunknownΔmayhaveallphases.
If required to find a controller to robustly stabilize the largest possible set of
∞-norm,
perturbations, in the sense of it is then clear that we need to solve the
followingminimizationproblem:
(cid:24) (cid:24)
|     |     | (cid:24) | −1(cid:24) |     |       |
| --- | --- | -------- | ---------- | --- | ----- |
|     |     | min      | K(I +GK)   |     | (3.2) |
∞
K stabilizing
Inmanycases,wemayhaveaprioriknowledgeoftheperturbation,say,

3.1 Small-GainTheoremandRobustStabilization 25
| (cid:6) (cid:7) (cid:6) | (cid:7)   |     |
| ----------------------- | --------- | --- |
| ≤σ                      | forallω∈R |     |
| σ Δ(jω) W 2 (jω)        |           |     |
Then,wemayrewritetheperturbationblockas
| Δ(s)=Δ (cid:27) |     |     |
| --------------- | --- | --- |
(s)W 2 (s)
(cid:27)
whereΔ(s)istheunitnormperturbationset.Correspondingly,therobuststabiliza-
tionconditionbecomes
| (cid:24)   | (cid:24)   |     |
| ---------- | ---------- | --- |
| (cid:24)   | −1(cid:24) |     |
| W K(I +GK) | <1         |     |
| 2          | ∞          |     |
andtheoptimizationproblem
| (cid:24)    | (cid:24)        |       |
| ----------- | --------------- | ----- |
| (cid:24)    | +GK) −1(cid:24) |       |
| min W 2 K(I | ∞               | (3.3) |
K stabilizing
Robust stabilization conditions can be derived similarly for other perturbation
representationsdiscussedinChap.2andarelistedbelow(G isreplacedbyGfor
o
thesakeofsimplicity).
1. Inverseadditiveperturbation:
| (cid:24)            | (cid:24) |       |
| ------------------- | -------- | ----- |
| (cid:24) −1(cid:24) | 1        |       |
| G(I +KG)            | <        | (3.4) |
∞ (cid:5)Δ(cid:5)
∞
2. Inputmultiplicativeperturbation:
| (cid:24)  | (cid:24)     |       |
| --------- | ------------ | ----- |
| (cid:24)  | −1(cid:24) 1 |       |
| KG(I +KG) | <            | (3.5) |
∞ (cid:5)Δ(cid:5)
∞
3. Outputmultiplicativeperturbation:
| (cid:24)      | (cid:24)     |       |
| ------------- | ------------ | ----- |
| (cid:24) +GK) | −1(cid:24) 1 |       |
| GK(I          | <            | (3.6) |
∞ (cid:5)Δ(cid:5)
∞
4. Inverseinputmultiplicativeperturbation:
| (cid:24)                 | (cid:24) |       |
| ------------------------ | -------- | ----- |
| (cid:24) +KG) −1(cid:24) | 1        |       |
| (I                       | <        | (3.7) |
∞ (cid:5)Δ(cid:5)
∞
5. Inverseoutputmultiplicativeperturbation:
| (cid:24)                 | (cid:24) |       |
| ------------------------ | -------- | ----- |
| (cid:24) +GK) −1(cid:24) | 1        |       |
| (I                       | <        | (3.8) |
∞ (cid:5)Δ(cid:5)
∞
ThecasesofperturbationoncoprimefactorswillbediscussedinChap.5.
Remark Intheabovediscussion,thestabilityoftheperturbationblockhasbeenas-
sumed.Actually,theconclusionsarealsotrueiftheperturbedsystemshavethesame
numberofclosedright-halfplanepolesasthenominalsystemdoes(see[107]).If
even this is not satisfied, then we will have to use the coprime factor perturbation
models,aswillbediscussedinChap.5.
Robuststabilizationisanimportantissuenotjustasadesignrequirement.Asa
matteroffact,theH ∞ designandrelatedapproachesfirstformulatethestabilityas
wellasperformancedesignspecificationsasarobuststabilizationproblemandthen
solvetherobuststabilizationproblemtofindacontroller.

26 3 RobustDesignSpecifications
Fig.3.3 Aclosed-loop
configurationofGandK
3.2 PerformanceConsiderations
Figure3.3depictsatypicalclosed-loopsystemconfiguration,whereGistheplant
andK thecontrollertobedesigned.r,y,u,e,d,nare,respectively,thereference
input,output,controlsignal,errorsignal,disturbance,andmeasurementnoise.With
alittleabuseofnotations,wedonotdistinguishthenotationsofsignalsinthetime
orfrequencydomains.Thefollowingrelationshipsareimmediatelyavailable:
y=(I +GK) −1GKr+(I +GK) −1d−(I +GK) −1GKn
u=K(I +GK) −1r−K(I +GK) −1d−K(I +GK) −1n
e=(I +GK) −1r−(I +GK) −1d−(I +GK) −1n
Assumethatthesignals r, d, n are energyboundedandhavebeennormalized,
i.e.lyingintheunitballofL space.We,however,donotknowwhatexactlythese
2
signalsare.Itisrequiredthattheusualperformancespecifications,suchastracking,
disturbanceattenuationandnoiserejection,shouldbeasgoodaspossibleforanyr,
d ornwhoseenergydoesnotexceed1.FromthediscussionsinChap.1onsignal
and system norms, it is clear that we should minimize the ∞-norm, the gain, of
corresponding transfer function matrices. Hence, the design problem is that over
thesetofallstabilizingcontrollerKs,(i.e.thoseKsmaketheclosed-loopsystem
internallystable),findtheoptimalonethatminimizes
• forgoodtracking,
(cid:5)(I +GK) −1(cid:5)
∞
• forgooddisturbanceattenuation,
(cid:5)(I +GK) −1(cid:5)
∞
• forgoodnoiserejection,
(cid:5)−(I +GK) −1GK(cid:5)
∞
• forlesscontrolenergy,
(cid:5)K(I +GK) −1(cid:5)
∞
ItisconventionaltodenoteS:=(I+GK) −1,thesensitivityfunction,andT :=
(I +GK) −1GK,thecomplementarysensitivityfunction.
Ingeneral,weightingfunctionswouldbeusedintheaboveminimizationtomeet
thedesignspecifications.Forinstance,insteadofminimizingthesensitivityfunction
alone,wewouldaimatsolving
min (cid:5)W 1 SW d (cid:5) ∞
K stabilizing

3.3 StructuredSingularValues 27
where W 1 is chosen to tailor the tracking requirement and is usually a high-gain
low-passfiltertype,W canberegardedasageneratorthatcharacterizesallrelevant
d
disturbancesinthecaseconsidered.Usually,theweightingfunctionsarestableand
ofminimumphase.
| 3.3 Structured | SingularValues |     |     |     |
| -------------- | -------------- | --- | --- | --- |
SystemswithuncertaindynamicscanallbeputinthestandardM–Δconfiguration
of Fig. 2.13. The robust stabilization conditions derived in Sect. 3.1 are sufficient
and necessary conditions for unstructured uncertainties, i.e. Δ is a full block and
will have all phases. In the case of structured uncertainty (Sect. 2.4), these robust
stabilization results could be very conservative. To deal with structured uncertain-
ties,weneedtointroducetheso-calledstructuredsingularvalues(SSV).
In fact, these robust stabilization results, such as that in Theorem 3.2, can be
equivalentlywrittenas[17,121]
|     | (cid:4)     | (cid:5)    |         |     |
| --- | ----------- | ---------- | ------- | --- |
|     | −M(jω)Δ(jω) | (cid:3)=0, | ∀ω∈R,∀Δ |     |
det I (3.9)
wherethenominal(closed-loop)systemM(s)isassumedtobestableasusual.
Thisconditionforrobuststabilityissufficientandnecessaryevenforstructured
uncertaintyΔ.Roughlyspeaking,inordertohavetheclosed-loopsystemrobustly
stable,all theuncertaintiesof a known structure of (2.19) should be small enough
−M(jω)Δ(jω)
not to violate the condition (i.e. not make I singular at any fre-
quencyω).Ontheotherhand,foragivenM withafixedcontrollerK andaknown
structure of the uncertainties, the smallest “size” of the uncertainty that makes
−M(jω)Δ(jω)singularatsomefrequencyω
| I   |     |     | describeshowrobustlystablethe |     |
| --- | --- | --- | ----------------------------- | --- |
controller K is in dealing with such structured uncertainties. This measurement is
theso-calledstructuredsingularvalues(SSV)introducedbelow.
First,asinSect.2.4,wedefinethestructureofuncertaintyof(2.19)andrepeat
hereforconvenience,
|     | (cid:12) |     |     | (cid:13) |
| --- | -------- | --- | --- | -------- |
(cid:2)= diag[δ I ,...,δ I ,Δ ,...,Δ ]:δ ∈C,Δ ∈Cmj ×mj (3.10)
|          | 1 r1     | s rs 1 | f i | j   |
| -------- | -------- | ------ | --- | --- |
| (cid:26) | (cid:26) |        |     |     |
where s r + f m =n with n is the dimension of the block Δ. We also
| i=1 | i j=1 j |     |     |     |
| --- | ------- | --- | --- | --- |
assumethesetof(cid:2)isbounded.And,wemaythusdefineanormalizedsetofstruc-
tureduncertaintyby
|     |            | (cid:12)           | (cid:13) |        |
| --- | ---------- | ------------------ | -------- | ------ |
|     | B(cid:2):= | Δ:σ(Δ)<1,Δ∈(cid:2) |          | (3.11) |
∈Cn×n,thestructuredsingularvalueμ
| Definition3.3 | ForM |     |       | (M)ofM withre- |
| ------------- | ---- | --- | ----- | -------------- |
|               |      |     | −1(M) | Δ              |
spect to (cid:2) is the number defined such that μ is equal to the smallest σ(Δ)
Δ
−MΔ)singular(rankdeficiency).Thatis
neededtomake(I
|     |            | (cid:12)   |        | (cid:13) |
| --- | ---------- | ---------- | ------ | -------- |
|     | −1(M):=min | σ(Δ):det(I | −MΔ)=0 |          |
μ (3.12)
|                                   | Δ Δ∈(cid:2) |              |     |         |
| --------------------------------- | ----------- | ------------ | --- | ------- |
| IfthereisnoΔ∈(cid:2)suchthatdet(I |             | −MΔ)=0,thenμ |     | (M):=0. |
Δ

28 3 RobustDesignSpecifications
WhenM isaninterconnectedtransfermatrixasinFig.2.13,thestructuredsin-
gularvalue,withrespectto(cid:2),isdefinedby
(cid:6) (cid:7) (cid:6) (cid:7)
μ M(s) := sup μ M(jω) (3.13)
Δ Δ
ω∈R
Correspondingly,theuncertaintysetmaybedefinedas
(cid:12) (cid:13)
M((cid:2)):= Δ(·)∈RH ∞ :Δ(jω)∈(cid:2)forallω∈R (3.14)
Whentheuncertaintystructureisfixed,wemayomitthesubscriptΔofμ (M)
Δ
forbrevity.
The reciprocal of the structured singular value denotes a frequency-dependent
stability margin [24, 145]. The robust stability result with regard to structured un-
certaintyisnowgiveninthefollowingtheorem.
Theorem3.4[31,161] Letthenominalfeedbacksystem(M(s)) bestableandlet
β>0beanuncertaintybound,i.e.(cid:5)Δ(cid:5) ∞<β,∀Δ(·)∈M((cid:2)).Theperturbedsys-
temofFig.2.13isrobustlystable,withrespectto(cid:2),ifandonlyifμ (M(s))≤ 1.
Δ β
It is obvious that if the uncertainty lies in the unit ball B(cid:2), the robust stability
conditionisthenμ (M(s))≤1.
Δ
μ (M(s)) isfrequencydependentandiscalculatedat“each”frequencyovera
Δ
reasonablerangeinpracticalapplications.
In the literature, μ (M(s)) is sometimes redefined as (cid:5)M(cid:5) for an intercon-
Δ μ
nected transfer function matrix M(s). This notation is convenient; however, it
should be clear that it is not a norm. It does not satisfy the three basic properties
ofanorm.Also,itdependsonM(s)aswellastheuncertaintystructureofΔ.
The structured singular value plays an important role in robust design. As be-
cameclearintheearlypartsofthischapter,theH ∞optimizationapproachcandeal
withrobuststabilizationproblemswithregardtounstructureduncertaintiesandcan
achieve nominal performance requirements. In the case of structured uncertainty,
Theorem3.4givesasufficientandnecessaryconditionforrobuststabilization.Fur-
thermore,therobustperformancedesigncanalsobetransformedintoarobuststa-
bilization problem with regard to structured uncertainties, as will be described in
Chap. 6. However, the computation of the structured singular value is not an easy
task.Itisstillanopentopicandrequiresfurtherresearch.
A few properties of the structured singular value and its computation are
listed below. Interested readers are referred to [31, 41, 42, 132–134, 196] for de-
tails. Coded routines for the μ computation are available in software packages
MATLAB®[11]andSlicot[78].
Let ρ(·) denotethespectralradiusofasquarematrix.Bydirectmanipulations,
wehavethefollowinglemma.
Lemma3.5 Forasquare,constantmatrixM,
μ(M)= max ρ(MΔ)
Δ∈B(cid:2)

| 3.3 StructuredSingularValues |     |     |     |     |     |     |     | 29  |
| ---------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
Thefollowingpropertiesofμcanalsoeasilybederived:
• μ(αM)=|α|·μ(M),∀α∈C
• −MΔ)(cid:3)=0,∀Δ∈B(cid:2)⇐⇒μ(M)≤1
det(I
| • if(cid:2)={δI  |     | :δ∈C}(s=1,f |      | =0;r =n)(cid:12)⇒μ(M)=ρ(M) |     |     |     |     |
| ---------------- | --- | ----------- | ---- | -------------------------- | --- | --- | --- | --- |
|                  | n   |             |      | 1                          |     |     |     |     |
| • if(cid:2)=Cn×n |     | (s=0,f      | =1;m | =n)(cid:12)⇒μ(M)=σ(M)      |     |     |     |     |
1
In the above, s, f, and n are dimensions of the uncertainty set (cid:2) as defined in
(3.10).
Further,wehavethefollowinglemma.
Lemma3.6
ρ(M)≤μ(M)≤σ(M)
Lemma 3.6 gives upper and lower bounds for μ(M). They are, however, not
particularly useful for the computation of μ(M), because the gap between ρ(M)
and σ(M) could be arbitrarily large. More accurate bounds are needed and these
canbeobtainedbyusingsometransformationsonM thatmaychangethevaluesof
ρ(M)andσ(M)butnotchangeμ(M).Thefollowingtwoconstantmatrixsetsare
introducedforthispurpose.
Define
|     |     |     |     | (cid:12)    |     | (cid:13) |     |     |
| --- | --- | --- | --- | ----------- | --- | -------- | --- | --- |
|     |     |     | U=  | ∈(cid:2):UU |     | ∗=I      |     |     |
|     |     |     |     | U           |     | n        |     |     |
and
(cid:12)
|     |     | D= D=diag[D |     | ,...,D | ,d  | I ,...,d | I ]: |     |
| --- | --- | ----------- | --- | ------ | --- | -------- | ---- | --- |
|     |     |             |     | 1      | s   | 1 m1     | f mf |     |
(cid:13)
|     |     |     | ∈Cri | ×ri,D =D | ∗    |      |     |     |
| --- | --- | --- | ---- | -------- | ---- | ---- | --- | --- |
|     |     | D   | i    | i        | >0,d | j >0 |     |     |
i
The matrix sets U and D match the structure of (cid:2). U is of a (block-) diagonal
|                                     |            |          |                              |         | D∈D              | Δ∈(cid:2), | −1)  |          |
| ----------------------------------- | ---------- | -------- | ---------------------------- | ------- | ---------------- | ---------- | ---- | -------- |
| structure                           | of unitary | matrices | and                          | for any |                  | and        | D (D | commutes |
| withΔ.Furthermore,foranyΔ∈(cid:2),U |            |          |                              |         | ∈U,andD∈D,wehave |            |      |          |
| • ∗∈U,UΔ∈(cid:2),ΔU                 |            |          | ∈(cid:2),andσ(UΔ)=σ(ΔU)=σ(Δ) |         |                  |            |      |          |
U
| • DΔD | −1=Δ,DΔD |     | −1∈Δ,andσ(DΔD |     | −1)=σ(Δ) |     |     |     |
| ----- | -------- | --- | ------------- | --- | -------- | --- | --- | --- |
Moreimportantly,wehave
|     |                    |       |      |     | (cid:6) | (cid:7) | (cid:6) (cid:7) |        |
| --- | ------------------ | ----- | ---- | --- | ------- | ------- | --------------- | ------ |
|     |                    |       |      |     |         | −1      | −1              |        |
|     | ρ(MU)≤μ(MU)=μ(M)=μ |       |      |     | DMD     | ≤σ      | DMD             | (3.15) |
|     |                    |       | =    |     |         |         | −               | = −    |
| In  | the above,         | μ(MU) | μ(M) | is  | derived | from    | det(I MΔ)       | det(I  |
MUU ∗ Δ) and U ∗ Δ∈(cid:2), σ(U ∗ Δ)=σ(Δ). Also, μ(M)=μ(DMD −1) can be
|     |     | −DMD | −1Δ)=det(I | −DMΔD |     | −1)=det(I | −MΔ). |     |
| --- | --- | ---- | ---------- | ----- | --- | --------- | ----- | --- |
seenfromdet(I
Therelationsin(3.15)directlyleadtothefollowingtheorem.
Theorem3.7
|     |     |                |     |     |     | (cid:6) | (cid:7) |     |
| --- | --- | -------------- | --- | --- | --- | ------- | ------- | --- |
|     |     | maxρ(MU)≤μ(M)≤ |     |     |     |         | −1      |     |
|     |     |                |     |     | inf | σ DMD   |         |     |
|     |     | U∈U            |     |     | D∈D |         |         |     |

30 3 RobustDesignSpecifications
Theorem3.7providestighterupperandlowerboundsonμ(M).In[31],itwas
shownthattheabovelowerboundisactuallyanequality,
maxρ(MU)=μ(M)
U∈U
Unfortunately,thisoptimizationproblemisnotconvex.ρ(MU)mayhavemultiple
localmaxima.Directcomputationofmax U∈U ρ(MU)maynotfindaglobalmaxi-
mum.Ontheotherhand,theupperboundofμ(M)inTheorem3.7iseasiertofind,
since σ(DMD
−1)
is convex in lnD [33, 153]. However, this upper bound is not
alwaysequaltoμ(M).Forthecasesof2s+f ≤3,itcanbeshownthat
(cid:6) (cid:7)
μ(M)= inf σ DMD −1
D∈D
Theproblemofcalculatingμ(M)isthereforereducedtoanoptimaldiagonalscal-
ing problem. Most algorithms proposed so far for the structured singular values
computethisupperbound.

Chapter 4
H
∞ Design
Acontrolsystemisrobustifitremainsstableandobeyscertainperformancecriteria
inthepresenceofpossibleuncertaintiesasdiscussedinChap.2.Therobustdesign
istofindacontroller,foragivensystem,suchthattheclosed-loopsystemisrobust.
TheH ∞ optimizationapproach,havingbeendevelopedinthelasttwodecadesand
stillanactiveresearcharea,hasbeenshowntobeaneffectiveandefficientrobust
design method for linear, time-invariant control systems. In the previous chapter,
variousrobuststabilityconsiderationsandnominalperformancerequirementswere
formulatedasaminimizationproblemoftheinfinitivenormofaclosed-looptrans-
fer function matrix. Hence, in this chapter, we shall discuss how to formulate a
robust design problem into such a minimization problem and how to find the so-
lutions. The H ∞ optimizationapproach solves, in general, the robust stabilization
problemsandnominalperformancedesigns.
4.1 MixedSensitivity H ∞ Optimization
Everypracticingcontrolengineerknowsverywellthatitwillneverbeappropriate
inanyindustrialdesigntousejustasinglecostfunction,suchasthoseformulated
in Chap. 3. A reasonable design would use a combination of these functions. For
instance, it makes sense to require a good tracking as well as to limit the control
signal energy, as depicted in Fig. 4.1. We may then want to solve the following
mixedsensitivity(orso-calledSoverKS)problem:
(cid:24) (cid:24)
(cid:24) (cid:24) (I +GK) −1 (cid:24) (cid:24)
K st m ab i i n lizing (cid:24) K(I +GK) −1 (cid:24) ∞ (4.1)
This cost function can also be interpreted as the design objectives of nominal
performance,goodtrackingordisturbanceattenuation,androbuststabilization,with
regardtoadditiveperturbation.
Inordertoadoptaunifiedsolutionprocedure,theabovecostfunction(4.1)canbe
recastintoastandardconfigurationasinFig.4.2.Thiscanbeobtainedbyusingthe
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 31
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_4,©Springer-VerlagLondon2013

32 4 H∞Design
Fig.4.1 Amixedsensitivity
consideration
Fig.4.2 ThestandardH∞
configuration
LFTtechniqueintroducedinChap.2andbyspecifying/groupingsignalsintosetsof
externalinputs,outputs,inputtothecontrollerandoutputfromthecontroller,which
ofcourseisthecontrolsignal.NotethatinFig.4.2alltheexternalinputsaredenoted
by w; z denotes the output signals to be minimized/penalized that includes both
performanceandrobustnessmeasures,y isthevectorofmeasurementsavailableto
thecontrollerK,anduthevectorofcontrolsignals.P(s)iscalledthegeneralized
plantorinterconnectedsystem.TheobjectiveistofindastabilizingcontrollerK to
minimize the output z, in the sense of energy, over all w with energy less than or
equalto1.Thus,itisequivalenttominimizingtheH ∞-normofthetransferfunction
fromwtoz.
PartitioningtheinterconnectedsystemP as
(cid:2) (cid:3)
P (s) P (s)
P(s)= 11 12
P (s) P (s)
21 22
wedirectlyfind
(cid:4) (cid:5)
z= P +P K(I −P K) −1P w
11 12 22 21
=:F(P,K)w
l
where F(P,K) is the lower linear fractional transformation of P and K. The
l
designobjectivenowbecomes
(cid:24) (cid:24)
min
(cid:24)F(P,K) (cid:24)
(4.2)
l ∞
K stabilizing
andisreferredtoastheH ∞ optimizationproblem.

| 4.2 2-Degree-of-FreedomH∞Design |     |     |     |     | 33  |
| ------------------------------- | --- | --- | --- | --- | --- |
Referring(cid:4)to(cid:5)thep(cid:4)ro(cid:5)blemin(4.1),itiseasytoderiveitsstandardformbydefining
z1 e
| w=r,z= | =   | ,y=e andu=u.Consequently,theinterconnectedsystem |     |     |     |
| ------ | --- | ------------------------------------------------ | --- | --- | --- |
z2 u
is
⎡ ⎤
−G
I
|     |     |     | =⎣ ⎦ |     |       |
| --- | --- | --- | ---- | --- | ----- |
|     |     | P   | 0 I  |     | (4.3) |
I −G
wherewemayset
|     |     | (cid:2) | (cid:3) | (cid:2) (cid:3) |     |
| --- | --- | ------- | ------- | --------------- | --- |
−G
|     |     | = I  | =      |     |     |
| --- | --- | ---- | ------ | --- | --- |
|     |     | P 11 | , P 12 |     |     |
|     |     | 0    |        | I   |     |
|     |     | =I,  | =−G    |     |     |
|     |     | P 21 | P 22   |     |     |
OthermixedcasesofcosttransferfunctionmatricessuchasSoverT,SoverT
overKS,etc.,canbedealtwithsimilarlytoformulateintothestandardconfigura-
tion.Inpracticaldesigns,itisoftennecessarytoinclude(closed-loop)weightswith
these cost functions. For instance, instead of (4.1), we may have to consider with
| =W          | =W  |                  |            |            |       |
| ----------- | --- | ---------------- | ---------- | ---------- | ----- |
| z 1 1 eandz | 2 2 | u,               |            |            |       |
|             |     |                  | (cid:24)   | (cid:24)   |       |
|             |     |                  | (cid:24)   | (cid:24)   |       |
|             |     |                  | W (I + G K | ) − 1      |       |
|             |     |                  | (cid:24) 1 | (cid:24)   |       |
|             |     | m i n            | (cid:24) + | − (cid:24) | (4.4) |
|             |     | K st ab i lizing | W K (I G   | K ) 1      |       |
|             |     |                  | 2          | ∞          |       |
Theseweightingfunctionscanbeeasilyabsorbedintotheinterconnectedsystem
P(s),asinthiscase,
|     |     |     | ⎡      | ⎤   |     |
| --- | --- | --- | ------ | --- | --- |
|     |     |     | W −W G |     |     |
1 1
|     |     | =⎣  |       | ⎦   |       |
| --- | --- | --- | ----- | --- | ----- |
|     |     | P   | 0 W 2 |     | (4.5) |
I −G
| 4.2 2-Degree-of-Freedom |     | H   | Design |     |     |
| ----------------------- | --- | --- | ------ | --- | --- |
∞
Among control-system design specifications, reference-signal tracking is often a
requirement. The output of a designed control system is required to follow a pre-
selected signal, or in a more general sense, the system is forced to track, for in-
stance,thestepresponseofaspecifiedmodel(infinite-timemodelfollowingtask).
A 2-degree-of-freedom (2DOF) control scheme naturally suits this situation. The
idea of a 2DOF scheme is to use a feedback controller (K ) to achieve the inter-
2
nalandrobuststability,disturbancerejection,etc.,andtodesignanothercontroller
(K ) on the feedforward path to meet the tracking requirement, which minimizes
1
the difference between the output of the overall system and that of the reference
model.2DOFcontrolschemesweresuccessfullyappliedinsomepracticaldesigns
[75,98,125].
Figure 4.3 shows one structure of these 2DOF control schemes. In this config-
uration,inadditiontotheinternalstabilityrequirement,twosignalse anduareto
beminimized.Thesignaleshowsthedifferencebetweenthesystemoutputandthe
referencemodeloutput.uisthecontrolsignalandalsoisrelatedtorobuststability

| 34  |     |     |     | 4 H∞Design |
| --- | --- | --- | --- | ---------- |
Fig.4.3 A2DOFdesignconfiguration
intheadditiveperturbationcase.InFig.4.3,twoweightingfunctionsareincluded
toreflectthetrade-offbetweenand/orcharacteristicsofthesetwopenalizedsignals.
TheconfigurationofFig.4.3(cid:4)can(cid:5)be(cid:4)rearr(cid:5)anged(cid:4)as(cid:5)thestandardconfigurationof
| Fig.4.2bydefiningw=r,z= |     | z1 = W1e | ,y= r andu=u.Notethatinthis |     |
| ----------------------- | --- | -------- | --------------------------- | --- |
|                         |     | z2 W 2 u | y                           |     |
configuration,K=[K −K ].Co nseque n tl y,theinte rconnectedsystemis
|     | 1   | 2   |     |     |
| --- | --- | --- | --- | --- |
|     |     | ⎡   | ⎤   |     |
−W
|     |     | 1 M o | W 1 G |     |
| --- | --- | ----- | ----- | --- |
|     |     | ⎢     | ⎥     |     |
|     |     | =⎢ 0  | W ⎥   |     |
|     |     | P     | 2     |     |
|     |     | ⎣ I   | 0 ⎦   |     |
|     |     | 0     | G     |     |
wherewemayset
|     |     | (cid:2) (cid:3) | (cid:2) (cid:3)  |     |
| --- | --- | --------------- | ---------------- | --- |
|     |     | −W M            | W G              |     |
|     | P = | 1 o ,           | P = 1            |     |
|     | 11  | 0               | 12 W             |     |
|     |     | (cid:2) (cid:3) | (cid:2) (cid:3)2 |     |
|     |     | I               | 0                |     |
|     | P = | ,               | P =              |     |
|     | 21  |                 | 22               |     |
|     |     | 0               | G                |     |
H
| 4.3 ∞ | Suboptimal Solutions |     |     |     |
| ----- | -------------------- | --- | --- | --- |
Thesolutiontotheoptimizationproblem(4.2)isnotuniqueexceptinthescalarcase
[64, 196]. Generally speaking, there are no analytic formulas for the solutions. In
practicaldesign,itisusuallysufficienttofindastabilizingcontrollerKsuchthatthe
H
∞-normoftheclosed-looptransferfunctionislessthanagivenpositivenumber,
i.e.,
(cid:24) (cid:24)
(cid:24)F(P,K) (cid:24)
<γ (4.6)
|     |       | l ∞                   |     |     |
| --- | ----- | --------------------- | --- | --- |
|     | :=min | (cid:5)F (P,K)(cid:5) |     | H   |
where γ >γ o K stabilizing l ∞. This is called the ∞ suboptimal
problem.Whencertainconditionsaresatisfied,thereareformulastoconstructaset
ofcontrollersthatsolvetheproblem(4.6).Thesolutionsetischaracterizedbyafree
parameterQ(s),whichisstableandof∞-normlessthanγ.

4.3 H∞SuboptimalSolutions 35
Itisimaginablethatifwesuccessivelyreducethevalueofγ,startingfromarela-
tivelylargenumbertoensuretheexistenceofasuboptimalsolution,wemayobtain
anoptimalsolution.Itshould,however,bepointedoutherethatwhenγ isapproach-
ingitsminimumvalueγ theproblemwouldbecomemoreandmoreill-conditioned
o
numerically.Hence,the“solution”thusobtainedmightbeveryunreliable.
4.3.1 SolutionFormulasforNormalizedSystems
Let the state-space description of the generalized (interconnected) system P in
Fig.4.2begivenby
x˙(t)=Ax(t)+B w(t)+B u(t)
1 2
z(t)=C x(t)+D w(t)+D u(t)
1 11 12
y(t)=C x(t)+D w(t)
2 21
where x(t) ∈ Rn is the state vector, w(t) ∈ Rm1 the exogenous input vector,
u(t)∈Rm2 the control input vector, z(t) ∈ Rp1 the error (output) vector, and
y(t)∈Rp2 themeasurementvector,withp
1
≥m
2
andp
2
≤m
1
.P(s)maybefur-
therdenotedas
(cid:2) (cid:3)
P (s) P (s)
P(s)= 11 12
P (s) P (s)
⎡ 21 22 ⎤
A B B
1 2
= ⎣ C D D ⎦
1 11 12
C D 0
(cid:2) 2 (cid:3)21
A B
=: (4.7)
C D
Note that in the above definition it is assumed that there is no direct link between
thecontrolinputandthemeasurementoutput,i.e.D =0.Thisassumptionisrea-
22
sonable because most industrial control systems are strictly proper and the corre-
spondingP(s)wouldhaveazeroD inasensibledesignconfiguration.Thecase
22
ofanonzerodirecttermbetweenu(t)andy(t)willbe,however,consideredinthe
nextsubsectionforthesakeofcompleteness.
The H ∞ solution formulas use solutions of two algebraic Riccati equations
(ARE).AnalgebraicRiccatiequation
ETX+XE−XWX+Q=0
whereW =WT andQ=QT uniquelycorrespondstoaHamiltonianmatrix
(cid:2) (cid:3)
E −W
−Q −ET
The stabilizing solution X, if it exists, is a symmetric matrix that solves the ARE
andissuchthatE−WXisastablematrix.Thestabilizingsolutionisdenotedas

36 4 H∞Design
(cid:2) (cid:3)
E −W
X:=Ric
−Q −ET
Define
(cid:2) (cid:3)
γ2I 0
R n :=D 1 T ∗ D 1∗ − 0 m1 0
and
(cid:2) (cid:3)
R ˜
n
:=D∗1 D
∗
T
1
− γ2
0
I p1 0
0
where
(cid:2) (cid:3)
(cid:4) (cid:5)
D
D 1∗ = D 11 D 12 and D∗1 = D 11
21
˜
AssumethatR andR arenonsingular.WedefinetwoHamiltonianmatricesH
n n
andJas
(cid:2) (cid:3) (cid:2) (cid:3)
(cid:4) (cid:5)
H:= A 0 − B R −1 DT C BT
(cid:2)
−C
1
TC
1
−AT
(cid:3) (cid:2)
−C
1
TD
1(cid:3) ∗
n 1∗ 1
J:=
−B
AT
BT −
0
A
−
−B
CT
DT
R ˜
n
−1 (cid:4) D∗1 B
1
T C (cid:5)
1 1 1 ∗1
Let
X:=Ric(H)
Y :=Ric(J)
BasedonXandY,astatefeedbackmatrixF andanobservergainmatrixLcan
beconstructed,whichwillbeusedinthesolutionformulas,
⎡ ⎤
(cid:2) (cid:3)
F :=−R n −1 (cid:6) D 1∗ TC 1 +BTX (cid:7) =: F F 1 =:⎣ F F 1 1 1 2 ⎦
2 F
2
(cid:6) (cid:7) (cid:4) (cid:5) (cid:4) (cid:5)
L:=− B
1
D∗1 T +YCT R ˜
n
−1=: L
1
L
2
=: L
11
L
12
L
2
whereF , F , F ,andF havem ,m ,m −p ,andp rows,respectively,and
1 2 11 12 1 2 1 2 2
L ,L ,L andL havep ,p ,p −m ,andm columns,respectively.
1 2 11 12 1 2 1 2 2
Gloverand Doyle[57] derivednecessary andsufficient conditionsfor theexis-
tenceofanH ∞ suboptimalsolutionandfurtherparameterizedallsuchcontrollers.
Theresultsareobtainedunderthefollowingassumptions:
(A1) (A,B )isstabilizableand(C ,A)detectable;
2(cid:2) (cid:3) 2
(cid:4) (cid:5)
0
(A2) D = and D = 0 I ;
12 I 21 p2
(cid:2) m2 (cid:3)
A−jωI B
(A3) 2 hasfullcolumnrankforallω;
C D
(cid:2) 1 12(cid:3)
A−jωI B
(A4) 1 hasfullrowrankforallω.
C D
2 21

4.3 H∞SuboptimalSolutions 37
Togetherwithappropriatepartitionof
(cid:2) (cid:3)
D D
D = 1111 1112 ,
11 D D
1121 1122
where D has m rows and p columns, the solution formulas are given in the
1122 2 2
followingtheorem.
Theorem4.1[196] SupposeP(s)satisfiestheassumptions(A1)–(A4).
(a) ThereexistsaninternallystabilizingcontrollerK(s)suchthat(cid:5)F
l
(P,K)(cid:5) ∞<
γ ifandonlyif
(i)
(cid:6) (cid:4) (cid:5)(cid:7)
γ >max σ[D ,D ],σ D T,D T
1111 1112 1111 1121
and
(ii) there exist stabilizing solutions X≥0 and Y ≥0 satisfying the two AREs
correspondingtotheHamiltonianmatricesHandJ,respectively,andsuch
that
ρ(XY)<γ2
whereρ(·)denotesthespectralradius.
(b) Given that the conditions of part (a) are satisfied, then all rational, internally
stabilizingcontrollers,K(s),satisfying(cid:5)F
l
(P,K)(cid:5) ∞<γ aregivenby
K(s)=F(M,Φ)
l
foranyrationalΦ(s)∈H ∞suchthat(cid:5)Φ(s)(cid:5) ∞<γ,whereM(s)hasthereal-
ization
⎡ ⎤
ˆ ˆ ˆ
A B B
⎢ 1 2 ⎥
M(s)=⎣C ˆ D ˆ D ˆ ⎦
1 11 12
ˆ ˆ
C D 0
2 21
and
(cid:6) (cid:7)
D ˆ =−D D T γ2I −D D T −1 D −D
11 1121 1111 1111 1111 1112 1122
D ˆ
12
∈Rm2 ×m2 andD ˆ
21
∈Rp2 ×p2 areanymatrices(e.g.Choleskyfactors)sat-
isfying
(cid:6) (cid:7)
D ˆ D ˆT =I −D γ2I −D TD −1 D T
12 12 1121 1111 1111 1121
(cid:6) (cid:7)
D ˆT D ˆ =I −D T γ2I −D D T −1 D
21 21 1112 1111 1111 1112
and

38 4 H∞Design
|     |     | ˆ   | =Z(B  | +L      | ˆ      |     |
| --- | --- | --- | ----- | ------- | ------ | --- |
|     |     | B 2 |       | 2 12    | )D 12  |     |
|     |     | ˆ   | =−D ˆ | +F      |        |     |
|     |     | C 2 |       | 21 (C 2 | 12 )   |     |
|     |     | ˆ   |       | ˆ       | ˆ−1D ˆ |     |
|     |     | B   | =−ZL  | +B      | D      |     |
|     |     | 1   |       | 2       | 2 12   | 11  |
ˆ
|     |     |     | =−ZL | +Z(B        | +L  | )D    |
| --- | --- | --- | ---- | ----------- | --- | ----- |
|     |     |     |      | 2           | 2   | 12 11 |
|     |     | C ˆ | =F   | +D ˆ D ˆ−1C | ˆ   |       |
|     |     | 1   | 2    | 11          | 2   |       |
21
|     |     |        | =F    | −D ˆ | +F      |     |
| --- | --- | ------ | ----- | ---- | ------- | --- |
|     |     |        |       | (C   |         | )   |
|     |     |        | 2     | 11   | 2 12    |     |
|     |     | ˆ=A+BF |       |      | ˆ ˆ−1C  | ˆ   |
|     |     | A      |       | +B   | D       |     |
|     |     |        |       |      | 1 21    | 2   |
|     |     |        | =A+BF | −B   | ˆ (C +F | )   |
|     |     |        |       |      | 1 2     | 12  |
where
|     |     |     |     | (cid:6) | (cid:7) |     |
| --- | --- | --- | --- | ------- | ------- | --- |
|     |     |     | Z=  | −γ −2YX | −1      |     |
I
WhenΦ(s)=0ischosen,thecorrespondingsuboptimalcontrolleriscalledthe
H
central controller that is widely used in the ∞ optimal design and has the state-
spaceform
|     |     |     |        | (cid:30) | (cid:31) |     |
| --- | --- | --- | ------ | -------- | -------- | --- |
|     |     |     |        | ˆ        | ˆ        |     |
|     |     |     |        | A        | B        |     |
|     |     |     | K (s)= |          | 1        |     |
|     |     |     | o      | ˆ        | ˆ        |     |
|     |     |     |        | C        | D        |     |
|     |     |     |        | 1        | 11       |     |
In the assumptions made earlier, (A2) assumes that the matrices D and D
12 21
areinnormalizedformsandthesystemP(s)isthusaso-callednormalizedsystem.
Whenthesetwomatricesareoffullrankbutnotnecessarilyinthenormalizedforms
willbediscussedlater.
| 4.3.2 Solutionto |     | S-over-KS |     | Design |     |     |
| ---------------- | --- | --------- | --- | ------ | --- | --- |
ThemixedsensitivityoptimizationS-over-KSisacommondesignprobleminprac-
tice.Theproblemisformulatedasin(4.1)or(4.4),andtheinterconnectedsystem
isin(4.3)or(4.5).Inthiscase,thesecondalgebraicRiccatiequationisofaspecial
form, i.e. the constant term is zero. We list the solution formulas for this special
designproblemhere.
Forsimplicity,weconsiderthesuboptimaldesignof(4.1).Thatis,foragivenγ,
wewanttofindastabilizingcontrollerK(s)suchthat
|     |     | (cid:24) |          |     | (cid:24)    |     |
| --- | --- | -------- | -------- | --- | ----------- | --- |
|     |     | (cid:24) | +GK)     | −1  | (cid:24)    |     |
|     |     | (cid:24) | (I       |     | (cid:24)    |     |
|     |     | (cid:24) |          |     | (cid:24) <γ |     |
|     |     |          | K(I +GK) | −1  |             |     |
∞
Theinterconnectedsysteminthestandardconfigurationis
|     |     |     |     | ⎡               |         | ⎤               |
| --- | --- | --- | --- | --------------- | ------- | --------------- |
|     |     | ⎡   | ⎤   | (cid:2)A(cid:3) | 0       | −B(cid:3)       |
|     |     |     | −G  |                 | (cid:2) | (cid:3) (cid:2) |
|     |     | I p |     | ⎢               |         | ⎥               |
|     |     | =⎣  | ⎦=⎢ | C               | I p     | 0 ⎥             |
|     | P   | 0   | I   | ⎣               |         | ⎦               |
|     |     |     | m   | 0               | 0       | I               |
|     |     | I   | −G  |                 |         | m               |
p
|     |     |     |     | C   | I p | 0   |
| --- | --- | --- | --- | --- | --- | --- |

4.3 H∞SuboptimalSolutions 39
whereweassumethatG(s)hasminputsandpoutputs,and
(cid:2) (cid:3)
A B
G(s)=
C 0
Itisclearthatγ mustbelargerthan1fromtheassumption(a)(i)ofTheorem4.1,
becausethe2-normoftheconstantmatrixD oftheaboveP(s)is1.Inthiscase,
11
thetwoalgebraicRiccatiequationsare
(cid:6) (cid:7)
ATX+XA−XBBTX+ 1−γ −2 −1 CTC=0
AY +YAT −YCTCY =0
Theformulaofthecentralcontrolleris
(cid:30) (cid:31)
A−BBTX−(1−γ −2) −1ZYCTC ZYCT
K =
o BTX 0
whereZ=(I −γ −2YX) −1.
Theformulasforallsuboptimalcontrollersare
K(s)=F(M,Φ)
l
withM(s)havingthestate-spacerealization
⎡ ⎤
A−BBTX−(1−γ −2) −1ZYCTC ZYCT −ZB
M(s)=⎣
BTX 0 I
⎦
m
−(1−γ −2) −1C I 0
p
andΦ(s)∈H ∞,suchthat(cid:5)Φ(cid:5) ∞<γ.
4.3.3 TheCase of D (cid:3)=0
22
Whenthereisadirectlinkbetweenthecontrolinputandthemeasurementoutput,
the matrix D will not disappear in (4.7). The controller formulas for the case
22
D (cid:3)=0arediscussedhere.
22
As a matter of fact, the D term can be easily separated from the rest of the
22
systemasdepictedinFig.4.4.AcontrollerK(s)forthesystemwithzeroD will
22
(cid:27)
be synthesized first, and then the controller K(s) for the original system can be
recoveredfromK(s)andD by
22
(cid:6) (cid:7)
K (cid:27) (s)=K(s) I +D K(s) −1
22
˜
Thestate-spacemodelofK(s)canbederivedas
(cid:30) (cid:31)
A −B D (I +D D ) −1C B (I +D D ) −1
K ˜ (s)= K K 22 K 22 K K 22 K
(I +D D ) −1C D (I +D D ) −1
K 22 K K 22 K
whereweassumethat
(cid:2) (cid:3)
A B
K(s)= K K
C D
K K

| 40  |     |     |     |     |     |     |     | 4   | H∞Design |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | -------- |
Fig.4.4 Thecaseof
nonzeroD22
4.3.4 NormalizationTransformations
In general, the system data given would not be in the normalization form as dis-
cussed in Sect. 4.3.1, though D will be of full column rank and D of full row
|     |     |     |     | 12  |     |     |     | 21  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
rank,respectively,foranyrealisticcontrolsystems.Inordertoapplytheresultsin
Theorem 4.1, certain transformations must be used first. Using the singular value
decomposition (SVD) or otherwise, we may find orthonormal matrices U 12 , V 12 ,
| U   | ,andV | ,suchthat |     |     |     |     |     |     |     |
| --- | ----- | --------- | --- | --- | --- | --- | --- | --- | --- |
|     | 21    | 21        |     |     |     |     |     |     |     |
(cid:2) (cid:3)
0
VT =
|        |     |       |        | U 12 D 12 |                                     |                 |         |     | (4.8) |
| ------ | --- | ----- | ------ | --------- | ----------------------------------- | --------------- | ------- | --- | ----- |
|        |     |       |        |           | 12                                  | Σ 12            |         |     |       |
|        |     |       |        |           |                                     | (cid:4)         | (cid:5) |     |       |
|        |     |       |        |           | VT =                                | Σ               |         |     |       |
|        |     |       |        | U 21 D 21 | 21                                  | 0 21            |         |     | (4.9) |
|        |     | :m ×m |        | :p ×p     |                                     |                 |         |     |       |
| whereΣ | 12  | 2     | 2 andΣ | 21 2      | 2 arenonsingular.Furthermore,wehave |                 |         |     |       |
|        |     |       |        |           |                                     | (cid:2) (cid:3) |         |     |       |
0
|     |     |     |     | U D   | VTΣ −1= |         |         |     | (4.10) |
| --- | --- | --- | --- | ----- | ------- | ------- | ------- | --- | ------ |
|     |     |     |     | 12 12 | 12      |         |         |     |        |
|     |     |     |     |       | 12      | I       |         |     |        |
|     |     |     |     |       |         | (cid:4) | (cid:5) |     |        |
|     |     |     |     | Σ −1U | D VT    | = 0     | I       |     | (4.11) |
|     |     |     |     | 21 21 | 21      | 21      |         |     |        |
Theright-handsidesoftheaboveequationsarenowinthenormalizedform.
|     | Whenp | >m andp | <m  | ,thematricesU |         | andV    | canbepartitionedas |     |        |
| --- | ----- | ------- | --- | ------------- | ------- | ------- | ------------------ | --- | ------ |
|     |       | 1 2     | 2   | 1             |         | 12      | 21                 |     |        |
|     |       |         |     |               | (cid:2) | (cid:3) |                    |     |        |
|     |       |         |     |               | =       | U 121   |                    |     |        |
|     |       |         |     | U             |         |         |                    |     | (4.12) |
|     |       |         |     |               | 12      | U       |                    |     |        |
122
|     |     |     |     |     | (cid:2) | (cid:3) |     |     |        |
| --- | --- | --- | --- | --- | ------- | ------- | --- | --- | ------ |
|     |     |     |     |     | =       | V 211   |     |     |        |
|     |     |     |     | V   | 21      |         |     |     | (4.13) |
V
212
| withU |     | :(p −m | )×p ,U | :m    | ×p ,V | :(m   | −p )×m | andV  | :p ×m . |
| ----- | --- | ------ | ------ | ----- | ----- | ----- | ------ | ----- | ------- |
|       | 121 | 1 2    | 1      | 122 2 | 1     | 211 1 | 2      | 1 212 | 2 1     |
ThenormalizationofP(s)intoP(s)isbasedontheabovetransformationsand
showninFig.4.5.

4.3 H∞SuboptimalSolutions 41
Fig.4.5 Normalization
configuration
GivenP(s),thestate-spaceformofP(s)isobtainedasfollows:
=B VT
B 1 1
21
−1
B =B VTΣ
| 2 2  | 12 12 |     |     |
| ---- | ----- | --- | --- |
| C =U | C     |     |     |
| 1 12 | 1     |     |     |
=Σ −1U
| C 2     | 21 C 2   |            |            |
| ------- | -------- | ---------- | ---------- |
| 21      |          | (cid:30)   | (cid:31)   |
|         |          | U D VT     | U D VT     |
| D =U    | D VT =   | 121 11 211 | 121 11 212 |
| 11 12   | 11 21    |            |            |
|         |          | U D VT     | U D VT     |
| (cid:2) | (cid:3)  | 122 11 211 | 122 11 212 |
| = 0     | =U       | VTΣ −1     |            |
| D 12    | 12 D     | 12         |            |
| I       |          | 12 12      |            |
| (cid:4) | (cid:5)  |            |            |
| D = 0   | I =Σ −1U | D VT       |            |
| 21      | 21       | 21 21 21   |            |
Since V and U are orthonormal, the infinitive norms of the transfer function
21 12
matrices from w to z and from w to z are the same, i.e. (cid:5)T (cid:5) =(cid:5)T (cid:5) ∞, with
zw ∞ zw
obviouslyK(s)=VTΣ −1K(s)Σ −1U
|       |     | 21 ,whereK(s)isasuboptimalsolutionwith |     |
| ----- | --- | -------------------------------------- | --- |
| 12 12 | 21  |                                        |     |
regardtoP(s).
H
| 4.3.5 DirectFormulasfor |     | ∞ SuboptimalCentralController |     |
| ----------------------- | --- | ----------------------------- | --- |
Based on the transformations discussed in the last subsection and by further ma-
nipulations,directsolutionformulascanbederivedforthegeneral,non-normalized
systemdata(4.7)[67].
WefirstdiscussthetwoalgebraicRiccatiequationsthatareessentialinthecom-
putations of H suboptimal controllers. The conclusion is a little surprising: the
∞
twoAREsremainthesameasthematricesinthenormalizedsystemdata(matrices

42 4 H∞Design
withbars)replacedbycorrespondingmatricesinthegeneralform(matriceswithout
bars)ofP(s).Thisisobtainedbythefollowingroutinematrixmanipulations:
C T C =CTUTU C =CTC
(cid:30) 1 (cid:31)1 (cid:2) 1 12 12 1 1 1 (cid:3)
B B VT B VTΣ −1
= 1 21 2 12 12
−C T 1 D 1∗ −C 1 TU 1 T 2 U 12 D 11 V 2 T 1 −C 1 TU 1 T 2 U 12 D 12 V 1 T 2 Σ 1 − 2 1
(cid:2) (cid:3)(cid:2) (cid:3)
B VT 0
= 21
(cid:2)
−C
1
TD 1∗ 0
(cid:3)
V
1
T
2
Σ
1
−
2
1
D T 1∗ D 1∗ = Σ − V T 21 V D 1 T D 1 U T 1 T U 2 T (cid:4) U 12 D 11 V 2 T 1 U 12 D 12 V 1 T 2 Σ 1 − 2 1 (cid:5)
(cid:2) 12 12 12 1(cid:3)2 (cid:2) (cid:3)
V 0 VT 0
= 0 21 Σ −TV D 1 T ∗ D 1∗ 0 21 VTΣ −1
12 12 12 12
where
(cid:4) (cid:5)
D 1∗ := D 11 D 12 (4.14)
Thus,
(cid:2) (cid:3) (cid:2) (cid:3)
V 0 VT 0
R n = 0 21 Σ −TV R 0 21 VTΣ −1
12 12 12 12
with
(cid:2) (cid:3)
γ2I 0
R:=D 1 T ∗ D 1∗ − 0 m1 0 (4.15)
Consequently,theHamiltonianHdefinedfornormalizedsystemdataisgivenby
(cid:2) (cid:3) (cid:2) (cid:3)
(cid:4) (cid:5)
H= A 0 − B R −1 DT C BT (4.16)
−C
1
TC
1
−AT −C
1
TD
1∗
1∗ 1
Similarly,theHamiltonianJisgivenby
(cid:2) (cid:3) (cid:2) (cid:3)
J=
−B
AT
BT −
0
A
−
−B
CT
DT
R ˜−1 (cid:4) D∗1 B
1
T C (cid:5) (4.17)
1 1 1 ∗1
where
(cid:2) (cid:3)
D
D∗1 :=
D
11 (4.18)
21
and
(cid:2) (cid:3)
R ˜ :=D∗1 D∗1 T − γ2
0
I p1 0
0
(4.19)
with
(cid:2) (cid:3) (cid:2) (cid:3)
R ˜ n = U 0 12 Σ − 0 1U R ˜ U 0 1 T 2 UTΣ 0 −T
21 21 21 21

| 4.3 | H∞SuboptimalSolutions |     |     |     |     |     | 43  |
| --- | --------------------- | --- | --- | --- | --- | --- | --- |
Hence,wehaveshownthatthetwoAREsareexactlythesameandsowemay,in
thefollowing,letXandY bethestabilizingsolutionsofthetwoAREscorrespond-
ingtothegeneralsystemdata.
Another pair of matrices used in Theorem 4.1 may also be defined from the
solutionsXandY,
|       |         |      |         |         |           | (cid:2) (cid:3)      |        |
| ----- | ------- | ---- | ------- | ------- | --------- | -------------------- | ------ |
|       |         |      |         | (cid:6) | (cid:7)   |                      |        |
|       |         |      | −1      | DT      | +BTX      | F 1                  |        |
|       |         | F    | :=−R    | C       |           | =:                   | (4.20) |
|       |         |      |         | 1∗      | 1         | F                    |        |
|       |         |      | (cid:6) |         | (cid:7)   | (cid:4) 2 (cid:5)    |        |
|       |         | L:=− | B       | DT +YCT | R ˜−1=:   | L L                  |        |
|       |         |      | 1       | ∗1      |           | 1 2                  | (4.21) |
| withF | :m ×n,F | :m   | ×n,L    | :n×p    | andL :n×p | .Itiseasytocheckthat |        |
|       | 1 1     | 2    | 2       | 1       | 1 2       | 2                    |        |
|       |         |      |         | (cid:2) |           | (cid:3)              |        |
|       |         |      |         | V 21    | 0         |                      |        |
|       |         |      | F       | =       |           | F                    |        |
|       |         |      |         | 0       | Σ V       |                      |        |
|       |         |      |         |         | 12 12     |                      |        |
and
=V
|     |     |     |     | F 11 | 211 F 1 |     |     |
| --- | --- | --- | --- | ---- | ------- | --- | --- |
=V
|     |     |     |     | F    | F     |     |     |
| --- | --- | --- | --- | ---- | ----- | --- | --- |
|     |     |     |     | 12   | 212 1 |     |     |
|     |     |     |     | F =Σ | V F   |     |     |
|     |     |     |     | 2    | 12 12 | 2   |     |
Similarly,wehave
|     |     |     |     | (cid:2) |     | (cid:3) |     |
| --- | --- | --- | --- | ------- | --- | ------- | --- |
|     |     |     |     | UT      | 0   |         |     |
|     |     |     | L=L |         | 12  |         |     |
0 UTΣ
21 21
and
|     |     |     |     | L =L | UT    |     |     |
| --- | --- | --- | --- | ---- | ----- | --- | --- |
|     |     |     |     | 11   | 1 121 |     |     |
=L UT
|     |     |     |     | L 12 | 1   |     |     |
| --- | --- | --- | --- | ---- | --- | --- | --- |
122
=L UTΣ
|     |     |     |     | L 2 | 2 21 |     |     |
| --- | --- | --- | --- | --- | ---- | --- | --- |
21
UsingtheaboveresultsandTheorem4.1,withfurthermanipulations,wecanget
thefollowingcorollary.Notethattheassumption(A2)isrelaxedtothegeneralcase:
|     | (A2) | D   | isoffullcolumnrankandD |     |     | offullrowrank |     |
| --- | ---- | --- | ---------------------- | --- | --- | ------------- | --- |
|     |      | 12  |                        |     |     | 21            |     |
Also,notethatforthesakeofsimplicity,onlytheformulasforthecentralsub-
optimalcontrollerisgiven.Formulasforallsuboptimalcontrollerscanbederived
accordingly.
| Corollary4.2 |     | SupposeP(s)satisfiestheassumptions(A1)–(A4). |     |     |     |     |     |
| ------------ | --- | -------------------------------------------- | --- | --- | --- | --- | --- |
(a) ThereexistsaninternallystabilizingcontrollerK(s)suchthat(cid:5)F (P,K)(cid:5) ∞<
l
γ
ifandonlyif
(i)
|     |        |      |                                   | (cid:12) |        | (cid:6) (cid:7)(cid:13) |        |
| --- | ------ | ---- | --------------------------------- | -------- | ------ | ----------------------- | ------ |
|     |        |      | γ >max                            | σ(U      | D ),σ  | D VT                    | (4.22) |
|     |        |      |                                   |          | 121 11 | 11 211                  |        |
|     | whereU | andV | areasdefinedin(4.12)and(4.13),and |          |        |                         |        |
121 211

44 4 H∞Design
(ii) thereexistsolutionsX≥0andY ≥0satisfyingthetwoAREscorrespond-
ingto(4.16)and(4.17),respectively,andsuchthat
ρ(XY)<γ2 (4.23)
whereρ(•)denotesthespectralradius.
(b) Giventhattheconditionsofpart(a)aresatisfied,thenthecentralH ∞ subopti-
malcontrollerforP(s)isgivenby
(cid:2) (cid:3)
A B
K(s)= K K
C D
K K
where
(cid:6) (cid:7)
D =−γ2(U D ) −1U γ2I −D VT V DT UT U −1
K 122 12 122 11 211 211 11 121 121
(cid:6) (cid:7)
×D VT D VT −1 (4.24)
(cid:4)11 212 21 212 (cid:5)
B =−Z L −(B +L D )D (4.25)
K 2 2 1 12 K
C =F −D (C +D F ) (4.26)
K 2 K 2 21 1
A =A+BF −B (C +D F ) (4.27)
K K 2 21 1
where
(cid:6) (cid:7)
Z= I −γ −2YX −1 (4.28)
and U ,V ,F, and L are as defined in (4.8) and (4.12), (4.9) and (4.13),
12 21
(4.20),and(4.21),respectively.
Remark Theabovecorollaryaddressesthegeneralcaseofp >m andp <m .
1 2 2 1
Therearethreespecialcasesofthedimensionsinwhichthesolutionformulaswould
besimpler.
Case1: p =m andp <m .
1 2 2 1
Inthiscase,theorthogonaltransformationonD isnotneeded.Thecondition
12
(a)(i)inCorollary4.2isreducedtoγ >σ(D VT ),and
11 211
(cid:6) (cid:7)
D =−D −1D VT D VT −1
K 12 11 212 21 212
Case2: p >m andp =m .
1 2 2 1
Inthiscase,theorthogonaltransformationonD isnotneeded.Thecondition
21
(a)(i)inCorollary4.2isreducedtoγ >σ(U D ),and
121 11
D =−(U D ) −1U D D −1
K 122 12 122 11 21
Case3: p =m andp =m .
1 2 2 1
Inthiscase,bothorthogonaltransformationsarenotneeded.Thecondition(a)(i)
inCorollary4.2isreducedtoanypositiveγ,and
D =−D −1D D −1
K 12 11 21

| 4.4 FormulasforDiscrete-TimeCases |     |     |     |     |     | 45  |
| --------------------------------- | --- | --- | --- | --- | --- | --- |
=0,inwhichthecentralcontrollerissimply
| AnotherspecialcaseiswhenD |     | 11  |     |     |     |     |
| ------------------------- | --- | --- | --- | --- | --- | --- |
givenby
|     |       | (cid:2)  |        |          | (cid:3) |     |
| --- | ----- | -------- | ------ | -------- | ------- | --- |
|     |       | A+BF +ZL |        | +D −ZL   |         |     |
|     | K(s)= |          | 2 (C 2 | 21 F 1 ) | 2       |     |
|     |       |          | F      |          | 0       |     |
2
| 4.4 Formulasfor | Discrete-TimeCases |     |     |     |     |     |
| --------------- | ------------------ | --- | --- | --- | --- | --- |
In this section, formulas for H solutions in discrete-time cases [62, 63] will be
∞
given.Considerageneralized,linear,discrete-timesystem,describedbytheequa-
tions
|     |     | =Ax    | +B   | +B     |     |        |
| --- | --- | ------ | ---- | ------ | --- | ------ |
|     |     | x k+1  | w    | u      |     |        |
|     |     | k      | 1 k  | 2 k    |     |        |
|     |     | z =C x | +D w | +D u   |     | (4.29) |
|     |     | k 1    | k 11 | k 12 k |     |        |
|     |     | y =C x | +D w | +D u   |     |        |
|     |     | k 2    | k 21 | k 22 k |     |        |
| ∈Rn |     |        | ∈Rm1 |        |     |        |
where x k is the state vector, w k is the exogenous input vector (the
disturbance), u ∈Rm2 is the control input vector, z ∈Rp1 is the error vector,
|      | k   |     |     | k   |     |     |
| ---- | --- | --- | --- | --- | --- | --- |
| ∈Rp2 |     |     |     | ≥m  | ≤m  |     |
andy k isthemeasurementvector,withp 1 2 andp 2 1 .Thetransfer
functionmatrixofthesystemwillbedenotedby
|     |     | (cid:2) |          | (cid:3)  |     |     |
| --- | --- | ------- | -------- | -------- | --- | --- |
|     |     | =       | P 11 (z) | P 12 (z) |     |     |
P(z)
|     |     |     | P (z) | P (z) |     |     |
| --- | --- | --- | ----- | ----- | --- | --- |
|     |     | ⎡   | 21    | 22 ⎤  |     |     |
A B B
1 2
|     |     | = ⎣ |     | ⎦   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
C 1 D 11 D 12
C D D
|     |     | (cid:2) | 2 (cid:3)21 | 22  |     |        |
| --- | --- | ------- | ----------- | --- | --- | ------ |
|     |     |         | A B         |     |     |        |
|     |     | =:      |             |     |     | (4.30) |
|     |     |         | C D         |     |     |        |
Similar to the continuous-time case, the H ∞ suboptimal discrete-time control
problemistofindaninternallystabilizingcontrollerK(z)suchthat,foraprespeci-
fiedpositivevalueγ,
|     |     | (cid:24)         | (cid:24) |     |     |        |
| --- | --- | ---------------- | -------- | --- | --- | ------ |
|     |     | (cid:24)         | (cid:24) |     |     |        |
|     |     | F (cid:14) (P,K) |          | <γ  |     | (4.31) |
∞
Weneedthefollowingassumptions.
| (A1) | (A,B )isstabilizableand(C |                                      | ,A)isdetectable; |     |     |     |
| ---- | ------------------------- | ------------------------------------ | ---------------- | --- | --- | --- |
|      | (cid:2) 2                 | (cid:3)                              | 2                |     |     |     |
|      | A−ejΘI                    | B                                    |                  |     |     |     |
| (A2) |                           | n 2 hasfullcolumnrankforallΘ∈[0,2π); |                  |     |     |     |
|      | C                         | D                                    |                  |     |     |     |
|      | 1                         | 12(cid:3)                            |                  |     |     |     |
(cid:2)
A−ejΘI
|     |     | n B 1 hasfullrowrankforallΘ∈[0,2π). |     |     |     |     |
| --- | --- | ----------------------------------- | --- | --- | --- | --- |
(A3)
|     | C   | D   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
|     | 2   | 21  |     |     |     |     |
We shall also assume that a loop-shifting transformation that enables us to set
=0hasbeencarriedout.Thegeneralcase(D (cid:3)=0)willbedealtwithatthe
D
| 22  |     |     |     | 22  |     |     |
| --- | --- | --- | --- | --- | --- | --- |
endofthissection.

46 4 H∞Design
Notethatthemethodunderconsiderationdoesnotinvolvereductionofthema-
trices D and D to some special form, as is usually required in the design of
12 21
continuous-timeH ∞ controllers.
Let
(cid:2) (cid:3) (cid:2) (cid:3)
C D D
C= 1 , D= 11 12
0 I 0
m1
anddefine
(cid:2) (cid:3) (cid:2) (cid:3) (cid:2) (cid:3)
J = I p1 0 , J ˆ= I m1 0 , J ˜= I m1 0
0 −γ2I 0 −γ2I 0 −γ2I
m1 m2 p1
LetX∞ bethesolutiontothediscrete-timeRiccatiequation
X∞ =C T JC+ATX∞A−LTR −1L (4.32)
where
(cid:2) (cid:3)
R=D T JD+BTX∞B=: R 1 R 2 T
R R
(cid:2) 2(cid:3) 3
L=D T JC+BTX∞A=: L 1
L
2
Assumethatthereexistsanm ×m matrixV suchthat
2 2 12
VTV =R
12 12 3
andanm ×m matrixV suchthat
1 1 21
VTV =−γ −2∇, ∇=R −RTR −1R <0
21 21 1 2 3 2
Definethematrices
⎡ ⎤
(cid:2) (cid:3) A B ˜ B ˜
A B ˜ ⎢ t t1 t2 ⎥
t t =:⎣ ˜ ˜ ⎦
C
t
D ˜
t
C t1 D
˜
t11 D
˜
t12
C D D
⎡
t2 t21 t22
⎤
⎢
A−B
1
∇−1L∇ B
1
V
2
−
1
1 0
⎥
= ⎣ V
12
R
3
−1(L
2
−R
2
∇−1L∇) V
12
R
3
−1R
2
V
2
−
1
1 I ⎦
C
2
−D
21
∇−1L∇ D
21
V
2
−
1
1 0
where
L∇ =L
1
−R
2
TR
3
−1L
2
LetZ∞ bethesolutiontothediscrete-timeRiccatiequation
Z∞ =B ˜
t
J ˆ B ˜
t
T +A
t
Z∞AT
t
−M
t
S
t
−1M
t
T (4.33)
inwhich
(cid:30) (cid:31)
S S
S
t
=D ˜
t
J ˆ D ˜
t
T +C
t
Z∞C
t
T =:
S
t
T
1
S
t2
t2 t3
M
t
=B ˜
t
J ˆ D ˜
t
T +A
t
Z∞C
t
T =:[M
t1
M
t2
]

4.4 FormulasforDiscrete-TimeCases 47
Equations(4.32)and(4.33)arereferredtoastheX-RiccatiequationandZ-Riccati
equation,respectively.
Astabilizingcontrollerthatsatisfies
(cid:24) (cid:24)
(cid:24) (cid:24)
F (P,K) <γ
(cid:14) ∞
existsifandonlyif[62]
(1) thereexistsasolutiontotheRiccatiequation(4.32)satisfying
X∞ ≥0
∇<0
suchthatA−BR −1Lisasymptoticallystable;
(2) thereexistsasolutiontotheRiccatiequation(4.33)suchthat
Z∞ ≥0
S −S S −1ST <0
t1 t2 t3 t2
withA −M S −1C asymptoticallystable.
t t t t
Inthiscase,acontrollerthatachievestheobjectivemaybegivenby[62]
xˆ k+1 =A t xˆ k +B 2 u k +M t2 S t − 3 1(y k −C t2 xˆ k )
V u =−C xˆ −S S −1(y −C xˆ )
12 k t1 k t2 t3 k t2 k
whichyields
(cid:30) (cid:31)
A −B V −1(C −S S −1C )−M S −1C −B V −1S S −1+M S −1
K = t 2 12 t1 t2 t3 t2 t2 t3 t2 2 12 t2 t3 t2 t3
0 −V −1(C −S S −1C ) −V −1S S −1
12 t1 t2 t3 t2 12 t2 t3
(4.34)
Thisistheso-calledcentralcontroller,whichiswidelyusedinpractice.
ConsidernowthegeneralcaseofD (cid:3)=0.Suppose
22
(cid:30) (cid:31)
ˆ ˆ
K ˆ = A k B k
ˆ ˆ
C D
k k
isastabilizingcontrollerforD settozero,andsatisfies
(cid:24) (cid:19) 22 (cid:2) (cid:3) (cid:20)(cid:24)
(cid:24) (cid:24)
(cid:24) (cid:24)F (cid:14) P − 0 0 D 0 ,K ˆ (cid:24) (cid:24) <γ
22 ∞
Then
(cid:6) (cid:6) (cid:7) (cid:7) (cid:6) (cid:7)
F P,K ˆ I +D K ˆ −1 =P +P K ˆ I +D K ˆ −P K ˆ −1 P
(cid:14) 22 11(cid:19) 12(cid:2) (cid:3)22 (cid:20) 22 21
=F P − 0 0 ,K ˆ
(cid:14) 0 D
22
ˆ
Inthisway,acontrollerK for
(cid:2) (cid:3)
0 0
P −
0 D
22

48 4 H∞Design
yieldsacontrollerK=K ˆ (I +D K ˆ ) −1 forP.Itmaybeshownthat
22
(cid:30) (cid:31)
A ˆ −B ˆ D (I +D ˆ D ) −1C ˆ B ˆ −B ˆ D (I +D ˆ D ) −1D ˆ
K= k k 22 m2 k 22 k k k 22 m2 k 22 k
(I +D ˆ D ) −1C ˆ (I +D ˆ D ) −1D ˆ
m2 k 22 k m2 k 22 k
ˆ
InordertofindK fromK wemustexcludethepossibilityofthefeedbacksystem
becomingill-posed,i.e.det(I +K ˆ (∞)D )=0.
22

Chapter 5
H
∞ Loop-Shaping Design Procedures
Inthepreviouschapterthe H ∞ optimizationapproachwasintroduced,whichfor-
mulated robust stabilization and nominal performance requirements as (sub)opti-
mizationproblemsoftheH ∞ normofcertaincostfunctions.Severalformulations
of cost function are applicable in the robust controller design, for instance, the
weightedS/KS and S/T designmethods.Theoptimizationof S/KS,where S is
thesensitivityfunctionandK thecontrollertobedesigned,couldachievethenom-
inal performance in terms of tracking or output disturbance rejection and robustly
stabilize the system against additive model perturbations. On the other hand, the
mixed sensitivity optimization of S/T, where T is the complementary sensitivity
function, could achieve robust stability against multiplicative model perturbations
in addition to the nominal performance. Both of them are useful robust controller
designmethods,butthemodelperturbationrepresentationsarelimitedbythecon-
ditiononthenumberofright-halfcomplexplanepoles.Also,theremayexistunde-
sirablepole-zerocancellationsbetweenthenominalmodelandtheH ∞ controllers
[151]. In this chapter, an alternative way to represent the model uncertainty is in-
troduced.Theuncertaintyisdescribedbytheperturbationsdirectlyonthecoprime
factorsofthenominalmodel[171,172].TheH ∞ robuststabilizationagainstsuch
perturbationsandtheconsequentlydevelopeddesignmethod,theH ∞loop-shaping
designprocedure(LSDP)[111,112],couldrelaxtherestrictionsonthenumberof
right-halfplanepolesandproducenopole-zerocancellationsbetweenthenominal
modelandcontrollerdesigned.Thismethoddoesnotrequireaniterativeprocedure
toobtainanoptimalsolutionandthusraisesthecomputationalefficiency.Further-
more,theH ∞ LSDPinheritsclassicalloop-shapingdesignideassothatpracticing
controlengineerswouldfeelmorecomfortabletouseit.
5.1 Robust StabilizationAgainst NormalizedCoprimeFactor
Perturbations
Matrices (M ˜ ,N ˜ )∈H ∞ + , where H ∞ + denotes the space of functions with no poles
in the closed right-half complex plane, constitute a left coprime factorization of a
givenplantmodelGifandonlyif
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 49
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_5,©Springer-VerlagLondon2013

50 5 H∞Loop-ShapingDesignProcedures
| ˜   |     | ˜ )(cid:3)=0 |     |     |     |     |     |
| --- | --- | ------------ | --- | --- | --- | --- | --- |
(i) M issquare,anddet(M
(ii) theplantmodelisgivenby
|                     |         |     |          | ˜−1N ˜ |     |     |       |
| ------------------- | ------- | --- | -------- | ------ | --- | --- | ----- |
|                     |         |     | G=M      |        |     |     | (5.1) |
|                     | ˜ ˜ )∈H | +   |          |        |     |     |       |
| (iii) thereexists(V | ,U      | ∞   | suchthat |        |     |     |       |
|                     |         |     | ˜ ˜      | ˜ ˜    |     |     |       |
|                     |         |     | M V +N   | U =I   |     |     | (5.2) |
AleftcoprimefactorizationofaplantmodelGasdefinedin(5.1)isnormalized
ifandonlyif
|     |     | ˜   | ˜−+M ˜ ˜−=I, |     |     |     |       |
| --- | --- | --- | ------------ | --- | --- | --- | ----- |
|     |     | N N | M            |     | ∀s  |     | (5.3) |
whereN ˜− (s)=N ˜T(−s),etc.
ForaminimalrealizationofG(s),
−1B
|     |     | G(s)=D+C(sI |         | −A)     |     |     |       |
| --- | --- | ----------- | ------- | ------- | --- | --- | ----- |
|     |     |             | (cid:2) | (cid:3) |     |     |       |
|     |     |             | A B     |         |     |     |       |
|     |     |             | =:      |         |     |     | (5.4) |
|     |     |             | C D     |         |     |     |       |
Astate-spaceconstructionforthenormalizedleftcoprimefactorizationcanbeob-
tainedintermsofthesolutiontothegeneralizedfilteralgebraicRiccatiequation
| (cid:6) |         | (cid:7) | (cid:6) |     | (cid:7)     |      |       |
| ------- | ------- | ------- | ------- | --- | ----------- | ---- | ----- |
| A−BDTR  |         | −1C Z+Z | A−BDTR  |     | −1C T −ZCTR | −1CZ |       |
|         | (cid:6) |         | (cid:7) |     |             |      |       |
| +B      | I −DTR  | −1D     | BT =0   |     |             |      | (5.5) |
where R := I + DDT and Z ≥ 0 is the unique stabilizing solution. If H =
−(ZCT +BDT)R −1,then
|     |         |         | (cid:2) |         |        | (cid:3) |       |
| --- | ------- | ------- | ------- | ------- | ------ | ------- | ----- |
|     | (cid:4) | (cid:5) | A+HC    | B+HD    |        |         |       |
|     | ˜       | ˜       |         |         | H      |         |       |
|     | N       | M :=    |         |         |        |         | (5.6) |
|     |         |         | R −1/2C | R −1/2D | R −1/2 |         |       |
|     |         |         |         |         |        | ˜−1N ˜  |       |
isanormalizedleftcoprimefactorizationofGsuchthatG=M .
Thenormalizedrightcoprimefactorizationcanbedefinedsimilarlyandastate-
spacerepresentationcanbesimilarlyobtainedintermsofthesolutiontothegener-
alizedcontrolalgebraicRiccatiequation[111],
| (cid:6) |         | (cid:7) | (cid:6) |       | (cid:7) |       |       |
| ------- | ------- | ------- | ------- | ----- | ------- | ----- | ----- |
|         | −1DTC   | T       |         | −1DTC |         | −1BTX |       |
| A−BS    |         | X+X     | A−BS    |       | −XBS    |       |       |
|         | (cid:6) |         | (cid:7) |       |         |       |       |
| +CT     |         | −1DT    |         |       |         |       |       |
|         | I −DS   |         | C=0     |       |         |       | (5.7) |
whereS:=I +DTDandX≥0istheuniquestabilizingsolution.
Aperturbedplanttransferfunctioncanbedescribedby
|     |     |            | (cid:6)     | (cid:7) (cid:6) | (cid:7)   |     |     |
| --- | --- | ---------- | ----------- | --------------- | --------- | --- | --- |
|     |     | =          | ˜ +(cid:17) | −1 ˜            | +(cid:17) |     |     |
|     |     | G (cid:17) | M ˜         | N               | ˜         |     |     |
|     |     |            | M           |                 | N         |     |     |

5.1 RobustStabilizationAgainstNormalizedCoprimeFactorPerturbations 51
Fig.5.1 Robuststabilizationwithregardtocoprimefactoruncertainty
where ((cid:17) ˜,(cid:17)˜) are unknown but stable transfer functions that represent the un-
M N
certainty(perturbation)inthenominalplantmodel.Thedesignobjectiveofrobust
stabilizationistostabilizenotonlythenominalmodelG,butthefamilyofperturbed
plantsdefinedby
(cid:12)(cid:6) (cid:7) (cid:6) (cid:7) (cid:24) (cid:24) (cid:13)
G (cid:18) = M ˜ +(cid:17) M ˜ −1 N ˜ +(cid:17) N ˜ :(cid:24)[(cid:17) M ˜,(cid:17) N ˜ ](cid:24) ∞ <(cid:18)
where (cid:18) > 0 is the stability margin. Using a feedback controller K as shown
schematically in Fig. 5.1 and the Small-Gain Theorem, the feedback system
˜ ˜
(M,N,K,(cid:18))isrobustlystableifandonlyif(G,K)isinternallystableand
(cid:24)(cid:2) (cid:3)(cid:24)
(cid:24) (cid:24)
(cid:24)
K
(I
(I
−
−
G
G
K
K
) −
) −
1
1
M ˜
M ˜
−
−
1
1 (cid:24) (cid:24)
(cid:24)
≤(cid:18) −1
∞
Tomaximizetherobuststabilityoftheclosed-loopsystemgiveninFig.5.1,one
mustminimize
(cid:24)(cid:2) (cid:3) (cid:24)
(cid:24) (cid:24)
γ :=(cid:24) (cid:24) K (I −GK) −1M ˜−1(cid:24) (cid:24)
I
∞
Thelowestachievablevalueofγ forallstabilizingcontrollersK is
(cid:24)(cid:2) (cid:3) (cid:24)
(cid:24) (cid:24)
γ o = K sta i b n i f lizing (cid:24) (cid:24) K I (I −GK) −1M ˜−1(cid:24) (cid:24) ∞ (5.8)
andisgivenin[111]by
(cid:6) (cid:24)(cid:4) (cid:5)(cid:24) (cid:7)
γ = 1−(cid:24) N ˜ M ˜ (cid:24)2 −1/2 (5.9)
o H
where(cid:5)·(cid:5) denotestheHankelnorm.From[111]
H
(cid:24)(cid:4) (cid:5)(cid:24) (cid:6) (cid:7)
(cid:24) N ˜ M ˜ (cid:24)2 =λ ZX(I +ZX) −1 (5.10)
H max

| 52  |     |     | 5   | H∞Loop-ShapingDesignProcedures |     |
| --- | --- | --- | --- | ------------------------------ | --- |
(·)representsthemaximumeigenvalue,hencefrom(5.9),
whereλ max
|     |     | (cid:6) |     | (cid:7) |     |
| --- | --- | ------- | --- | ------- | --- |
1/2
|     |     | γ = 1+λ | (ZX)           |     | (5.11)    |
| --- | --- | ------- | -------------- | --- | --------- |
|     |     | o       | max            |     |           |
|     |     |         | aregivenbyK=UV |     | −1,whereU |
From[111],allcontrollersoptimizingγ and
V arestableandarerightcoprimefactorizationsofK,andwhere
|     | (cid:24)(cid:2) | (cid:3) | (cid:2) (cid:3)(cid:24)     |                 |     |
| --- | --------------- | ------- | --------------------------- | --------------- | --- |
|     | (cid:24)        | − N ˜ ∗ | U (cid:24) (cid:24) (cid:4) | (cid:5)(cid:24) |     |
|     | (cid:24)        | +       | (cid:24) = (cid:24)         | ˜ ˜ (cid:24)    |     |
|     | (cid:24)        | ˜ ∗     | (cid:24)                    | N M             |     |
|     |                 | M       | V                           | H               |     |
∞
ThisisaHankelapproximationproblemandcanbesolvedusinganalgorithmde-
velopedbyGlover[55].
| Acontrollerthatachievesaγ |     | >γ  | isgivenin[111]by |     |     |
| ------------------------- | --- | --- | ---------------- | --- | --- |
0
|            | (cid:30)                |         |             |              | (cid:31) |
| ---------- | ----------------------- | ------- | ----------- | ------------ | -------- |
|            | A+BF                    | +γ2(LT) | −1ZCT(C+DF) | γ2(LT) −1ZCT |          |
| K:=        |                         |         |             |              | (5.12)   |
|            |                         | BTX     |             | −DT          |          |
| whereF =−S | −1(DTC+BTX)andL=(1−γ2)I |         |             | +XZ.         |          |
|            | =γ                      | L=XZ−λ  |             |              |          |
However, if γ o , then max (XZ)I, which is singular, and thus
(5.12) cannot be implemented. This problem can be resolved using the descriptor
system[147,148].Acontrollerthatachievesγ ≥γ canbegiveninthedescriptor
o
formby
|     | (cid:30)                  |     |     |       | (cid:31) |
| --- | ------------------------- | --- | --- | ----- | -------- |
|     | −LTs+LT(A+BF)+γ2ZCT(C+DF) |     |     | γ2ZCT |          |
K:=
(5.13)
|                  |     |                  | BTX |     | −DT |
| ---------------- | --- | ---------------- | --- | --- | --- |
| 5.2 Loop-Shaping |     | DesignProcedures |     |     |     |
Intheclassicalcontrolsystemsdesignwithsingle-input–single-output(SISO)sys-
tems,itisawell-knownandpracticallyeffectivetechniquetouseacompensatorto
alterthefrequencyresponse(theBodediagram)oftheopen-looptransferfunction
sothattheunityfeedbacksystemwillachievestability,goodperformanceandcer-
tain robustness. Indeed, these performance requirements discussed in Chap. 3 can
beconvertedintocorrespondingfrequencyrequirementsontheopen-loopsystem.
Forinstance,inordertoachievegoodtracking,itisrequiredthat(cid:5)(I +GK) −1(cid:5)
∞
|           |             | +GK)    | −1(jω))(cid:8)1, |            |                 |
| --------- | ----------- | ------- | ---------------- | ---------- | --------------- |
| should be | small. That | is σ((I |                  | for ω over | a low-frequency |
range,sincethesignalstobetrackedareusuallyoflowfrequency.Thisinturnim-
pliesthatσ(GK(jω))(cid:16)1,forωoverthatfrequencyrange.Similardeductionscan
beappliedtootherdesign-performancespecifications.
However, a direct extension of the above method into multivariable systems is
difficult not only because multi-input and multi-output (MIMO) are involved but
alsoduetothelackofphaseinformationinMIMOcasesthatmakesitimpossibleto
predictthestabilityoftheclosed-loopsystemformedbytheunityfeedback.How-
ever,basedontherobuststabilizationagainstperturbationsonnormalizedcoprime

5.2 Loop-ShapingDesignProcedures 53
Fig.5.2 One-degree-of-freedomLSDPconfiguration
factorizations,a design method,known as the H ∞ loop-shapingdesign procedure
(LSDP),hasbeendeveloped[112].TheLSDPmethodaugmentstheplantwithap-
propriatelychosenweightssothatthefrequencyresponseoftheopen-loopsystem
(the weighted plant) is reshaped in order to meet the closed-loop performance re-
quirements.Thenarobustcontrollerissynthesizedtomeetthestability.
Thisloop-shapingdesignprocedurecanbecarriedoutinthefollowingsteps.
(i) Using a precompensator, W , and/or a postcompensator, W , as depicted in
1 2
Fig. 5.2, the singular values of the nominal system G are modified to give a
desired loop shape. Usually, the least singular value of the weighted system
should be made large over the low-frequency range to achieve good perfor-
mance such as the tracking, the largest singular value is small over the high-
frequencyrangetodealwithunmodeleddynamics,andthebandwidthaffects
thesystemresponsespeed,whiletheslopeofthesingularvaluesneartheband-
width frequency should not be too steep. The nominal system and weighting
functions W and W are combined to form the shaped system, G , where
1 2 s
G =W GW . It is assumed that W and W are such that G contains no
s 2 1 1 2 s
hiddenunstablemodes.
(ii) A feedback controller, K , is synthesized that robustly stabilizes the normal-
s
izedleftcoprimefactorizationofG ,withastabilitymargin(cid:18).Itcanbeshown
s
[112]thatif (cid:18) isnotlessthan0.2,thefrequencyresponseof K W GW will
s 2 1
be similar to that of W GW . On the other hand, if the achievable (cid:18) is too
2 1
large, this would probably indicate an overdesigned case with respect to the
robustness,whichmeansthattheperformanceofthesystemmaypossiblybe
improvedbyusingalargerγ incomputingK .
s
(iii) Thefinalfeedbackcontroller,K final ,isthenconstructedbycombiningtheH ∞
controllerK ,withtheweightingfunctionsW andW suchthat
s 1 2
K =W K W
final 1 s 2
For a tracking problem, the reference signal generally comes between K and
s
W .Inordertoreducethesteady-statetrackingerror,aconstantgain K (0)W (0)
1 s 2
isplacedonthefeedforwardpath,where
K (0)W (0)= limK (s)W (s)
s 2 s 2
s→0

54 5 H∞Loop-ShapingDesignProcedures
Fig.5.3 Two-degree-of-freedomLSDP
The closed-loop transfer function between the reference r and the plant output y
thenbecomes
(cid:4) (cid:5)
Y(s)= I −G(s)K (s)
−1
G(s)W (s)K (0)W (0)R(s)
final 1 s 2
The above design procedure can be developed further into a two-degree-of-
freedom(2DOF)schemeasshowninFig.5.3.
Thephilosophyofthe2DOFschemeistousethefeedbackcontroller K (s) to
2
meet the requirements of internal and robust stability, disturbance rejection, mea-
surement noise attenuation, and sensitivity minimization. The precompensator K
1
isappliedtothereferencesignal,whichoptimizestheresponseoftheoverallsys-
tem to the command input such that the output of the system would be “near” to
that of a chosen ideal system M . The feedforward compensator K depends on
o 1
designobjectivesandcanbesynthesizedtogetherwiththefeedbackcontrollerina
singlestepviatheH ∞ LSDP[75].Inthe2DOFLSDP,thepostcompensatorW 2 is
usuallychosenasanidentitymatrix.Theconstantρ isascalingparameterusedto
emphasizethemodel-matchingpartinthedesign.
5.3 Formulasfor theDiscrete-TimeCase
Inthissection,theformulasforthe(1-block)H ∞ LSDPcontrollerinthediscrete-
timecasewillbeintroduced[68].
5.3.1 NormalizedCoprimeFactorizationof Discrete-TimePlant
LetG(z)beaminimalrealization,discrete-timemodelofaplant,
G(z) = D+C(zI −A) −1B
(cid:2) (cid:3)
A B
:=
C D
withA:n×n,B:n×m,C:p×n,andD:p×m.

5.3 FormulasfortheDiscrete-TimeCase 55
Matrices (M ˜ (z), N ˜ (z))∈H ∞ + , where H ∞ + denotes the space of functions with
allpolesintheopenunitdiscofthecomplexplane,constitutealeftcoprimefactor-
izationofG(z)ifandonlyif
(i) M ˜ issquare,anddet(M ˜ )(cid:3)=0
(ii) theplantmodelisgivenby
G=M ˜−1N ˜ (5.14)
(iii) Thereexists(V ˜ ,U ˜ )∈H ∞ + suchthat
M ˜ V ˜ +N ˜ U ˜ =I (5.15)
p
AleftcoprimefactorizationofGasdefinedin(5.14)isnormalizedifandonlyif
(cid:19) (cid:20) (cid:19) (cid:20)
N ˜ (z)N ˜T 1 +M ˜ (z)M ˜T 1 =I (5.16)
p
z z
Theconceptofrightcoprimefactorizationandnormalizedrightcoprimefactor-
ization can be introduced similarly. However, the work presented here will follow
the(normalized)leftcoprimefactorization,althoughallresultsconcerningthe(nor-
malized)rightcoprimefactorizationcanbederivedsimilarly.
State-space constructions for the normalized coprime factorizations can be ob-
tainedintermsofthesolutionstothefollowingtwodiscretealgebraicRiccatiequa-
tions(DARE):
ΦTPΦ−P −ΦTPBZ ZTBTPΦ+CTR −1C=0 (5.17)
1 1 1
and
ΦQΦT −Q−ΦQCTZTZ CQΦT +BR −1BT =0 (5.18)
2 2 2
where R =I +DDT, R =I +DTD, Φ =A−BR −1DTC, Z ZT =(R +
1 p 2 m 2 1 1 2
BTPB) −1,ZTZ =(R +CQCT) −1.And,P ≥0andQ≥0aretheuniquesta-
2 2 1
bilizingsolutions,respectively.
Withoutlossofgenerality,wemayassumethatbothZ andZ aresquarema-
1 2
trices,andZ =ZT,Z =ZT.
1 1 2 2
Further,bydefiningH =−(AQCT +BDT)ZTZ andF =−Z ZT(BTPA+
2 2 1 1
DTC),then
(cid:2) (cid:3)
(cid:4) N ˜ M ˜ (cid:5) := A+HC B+HD H (5.19)
Z C Z D Z
2 2 2
and
⎡ ⎤
(cid:2) (cid:3) A+BF BZ
N :=⎣ C+DF DZ 1 ⎦ (5.20)
M 1
F Z
1
arethenormalizedleftandrightcoprimefactorizationsofG,respectively.

56 5 H∞Loop-ShapingDesignProcedures
5.3.2 RobustControllerFormulas
As in the continuous-time case, the discrete-time H ∞ loop-shaping design proce-
dure is based on the constructionof a robust stabilizing controller against the per-
turbationsonthecoprimefactors.Thesameformofcostfunctionforrobuststabi-
lizationwillbederived,andtheoptimalachievableγ isgivenby
(cid:6) (cid:7)
γ = 1+λ (QP) 1/2 (5.21)
o max
whereQandP arethesolutionsto(5.17)and(5.18),respectively.
For a given γ >γ o , a suboptimal H ∞ LSDP controller K in the discrete-time
casecanberecastasastandardH ∞ suboptimalcontrolproblemaswasdiscussed
inSect.4.4.Thegeneralized(interconnected)systeminthiscaseis
(cid:2) (cid:3)
P (z) P (z)
P(z)= 11 12
P (z) P (z)
21 22
⎡ ⎤
0 I
m
=⎣M ˜−1 G⎦
M
˜−1
G
⎡ ⎤
A −HZ −1 B
2
⎢ ⎥
=⎢
⎣
C
0
Z
0
−1
I
D
m⎥
⎦ (5.22)
2
C Z
−1
D
2
Following the solution procedure given in Sect. 4.4, one more DARE needs to
be solved in order to compute the required controller. In general H ∞ suboptimal
problems, two more algebraic Riccati equations are to be solved. Here, however,
duetothestructureofP(z)in(5.22),itcanbeshownthatthesolutiontooneofthe
DAREisalwayszero.ThethirdDAREisthefollowing:
(cid:19) (cid:2) (cid:3) (cid:20)
ATX∞A−X∞ −F ˜T R+ − R Z − 2 1 − / 1 2 H BT T X∞ (cid:4) −HZ 2 −1 BR 2 −1/2 (cid:5) F ˜
2
+CTC=0 (5.23)
where
(cid:19) (cid:2) (cid:3) (cid:20)
F ˜ =− R+ − R Z − 2 1 − / 1 2 H BT T X∞ (cid:4) −HZ 2 −1 BR 2 −1/2 (cid:5) −1
2
(cid:19)(cid:2) (cid:3) (cid:2) (cid:3) (cid:20)
−Z −1C −Z −1HT
×
DTR
2
−1/2C
+
R −
2
1/2BT
X∞A
1 2
and
(cid:2) (cid:3)
Z
−2−γ2I
Z
−1R −1/2D
R=
DT
2
R −1/2Z
p
−1
2
I
1
1 2 m

5.3 FormulasfortheDiscrete-TimeCase 57
(cid:4) (cid:5)
Further, by defining F ˜ = F1 , where F : p×n and F : m×n, a suboptimal
H ∞ discrete-timeLSDP(DLS F D 2 P)controlle 1 rK canbecons 2 tructedas
(cid:2) (cid:3)
A B
K(z)= K K
C D
K K
where
A =A ˆ −B ˆ D(I +D ˆ D) −1C ˆ
K K K K K
B =B ˆ (I +DD ˆ ) −1
K K K
(5.24)
C =(I +D ˆ D) −1C ˆ
K K K
D =D ˆ (I +DD ˆ ) −1
K K K
with
(cid:6) (cid:7) (cid:6) (cid:7)
D ˆ
K
=− R
2
+BTX∞B −1 DT −BTX∞H
B ˆ =−H +BD ˆ
K K
(cid:6) (cid:7) (5.25)
C ˆ =R −1/2 F −D ˆ C+Z −1F
K 2 2 K 2 1
A ˆ =A+HC+BC ˆ
K K
5.3.3 TheStrictlyProperCase
It may be appropriate to say that most (formulated) plants considered in the prac-
tical, discrete-time control-systems design are, in using the H ∞ optimization ap-
proachinparticular,strictlyproper,i.e.D=0.Thisisnotonlybecausemostphys-
ical plants in industrial studies are strictly proper, as in the continuous-time case,
but also because the H ∞ controllers designed tend to be proper due to the “flat-
ness”oftheoptimalitysoughtinthesynthesis.Hence,whenthe(formulated)plant
is just proper, it is possible to encounter the problem of an algebraic loop in the
implementationoftheresultantcontroller.
When the plant under consideration is strictly proper, all the computations and
formulas described in Sect. 5.3.2 will be significantly simpler. The two DAREs
(5.17)and(5.18)become
ATPA−P −ATPBZ Z TBTPA+CTC=0 (5.26)
1 1
and
AQAT −Q−AQCTZTZ CQAT +BBT =0 (5.27)
2 2
whereZ Z T =(I +BTPB) −1,Z TZ =(I +CQCT) −1.
1 1 m 2 2 p

| 58  |     |     |     |     |     | 5 H∞Loop-ShapingDesignProcedures |     |     |
| --- | --- | --- | --- | --- | --- | -------------------------------- | --- | --- |
ThethirdDARE(5.23)isnowthefollowing:
|          |        |     | (cid:19) | (cid:2) |     | (cid:3) |         | (cid:20) |
| -------- | ------ | --- | -------- | ------- | --- | ------- | ------- | -------- |
|          |        |     |          |         | −   |         | (cid:4) | (cid:5)  |
|          |        |     | ˜T       | −Z      | 1HT |         |         | ˜        |
| ATX∞A−X∞ |        | −F  | R+       |         | 2   | X∞      | −HZ −1  | B F      |
|          |        |     |          |         | B T |         | 2       |          |
|          | +CTC=0 |     |          |         |     |         |         | (5.28)   |
where
|     |     | (cid:19) | (cid:2) |     | (cid:3) |     | (cid:20) |     |
| --- | --- | -------- | ------- | --- | ------- | --- | -------- | --- |
−1
|     |     |       | −Z  | − 1HT |     | (cid:4) | (cid:5) |     |
| --- | --- | ----- | --- | ----- | --- | ------- | ------- | --- |
|     | ˜   | =− R+ |     | 2     |     | −HZ     | −1      |     |
|     | F   |       |     | T     | X∞  |         | 2 B     |     |
B
|     |     | (cid:19)(cid:2) |        | (cid:3) | (cid:2) | (cid:3) | (cid:20) |     |
| --- | --- | --------------- | ------ | ------- | ------- | ------- | -------- | --- |
|     |     |                 | −Z −1C |         | −Z −1HT |         |          |     |
|     |     | ×               | 2      | +       | 2       |         |          |     |
X∞A
|     |     |     | 0   |     | BT  |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
and
|     |     |     |     | (cid:2)  |     | (cid:3) |     |     |
| --- | --- | --- | --- | -------- | --- | ------- | --- | --- |
|     |     |     |     | Z −2−γ2I |     | 0       |     |     |
|     |     |     | R=  | 2        | p   |         |     |     |
|     |     |     |     |          | 0   | I       |     |     |
m
|     |     |     | =−AQCTZ |     | TZ  |     |     |     |
| --- | --- | --- | ------- | --- | --- | --- | --- | --- |
H
|     |     |     |     |     | 2   | 2   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
(cid:4) (cid:5)
˜
| Further,bydefiningF |     |     | = F1 | ,whereF | :p×nandF |     | :m×n,thesuboptimal |     |
| ------------------- | --- | --- | ---- | ------- | -------- | --- | ------------------ | --- |
|                     |     |     | F    |         | 1        |     | 2                  |     |
| H                   |     |     | 2    |         |          |     |                    |     |
∞ DLSDPcontrollerK inth e caseofast rictlyproperG canbeconstructedas
|     |     |     |     |     | (cid:2) | (cid:3) |     |     |
| --- | --- | --- | --- | --- | ------- | ------- | --- | --- |
A B
|     |     |     | K(z)= |     | K   | K   |     |     |
| --- | --- | --- | ----- | --- | --- | --- | --- | --- |
C D
|     |     |     |     |     | K   | K   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
where
|     |     |     | (cid:6) |     | (cid:7) |     |     |     |
| --- | --- | --- | ------- | --- | ------- | --- | --- | --- |
−1
|     |     | D   | = I | +BTX∞B |     | BTX∞H |     |     |
| --- | --- | --- | --- | ------ | --- | ----- | --- | --- |
|     |     |     | K m |        |     |       |     |     |
|     |     |     | =−H | +BD    |     |       |     |     |
|     |     | B   | K   |        | K   |       |     |     |
(5.29)
|     |     |     |          |     | (cid:6) | (cid:7) |     |     |
| --- | --- | --- | -------- | --- | ------- | ------- | --- | --- |
|     |     |     | =F       | −D  | C+Z     | −1F     |     |     |
|     |     | C   | K 2      | K   | 2       | 1       |     |     |
|     |     | A   | =A+HC+BC |     |         |         |     |     |
|     |     |     | K        |     | K       |         |     |     |
5.3.4 OntheThreeDARESolutions
As discussed above, the discrete-time H LSDP suboptimal controller formulae
∞
require the solutions to the three discrete-time algebraic Riccati equations, (5.17),
(5.18),and(5.23),or(5.26),(5.27),and(5.28)inthestrictlypropercase.Inthissub-
section,wewillshowthatthereisarelationbetweenthesethreesolutions,namely
the solution X∞ to the third DARE can be calculated directly from the first two
solutions P and Q. This fact is important and useful, especially in the numerical
implementationoftheDLSDProutines.

| 5.3 | FormulasfortheDiscrete-TimeCase |     |     |     |     |     |     | 59  |
| --- | ------------------------------- | --- | --- | --- | --- | --- | --- | --- |
WestartwithageneralDARE,hencethenotationsarenotrelatedtothosedefined
earlierinthechapter.Wehave
|     |     |     | (cid:6) |     | (cid:7) |     |     |     |
| --- | --- | --- | ------- | --- | ------- | --- | --- | --- |
−1
|                   | FTXF −X−FTXG |         | G   | +GTXG      |     | GTXF | +CTC=0          | (5.30) |
| ----------------- | ------------ | ------- | --- | ---------- | --- | ---- | --------------- | ------ |
|                   |              |         | 1 2 | 1          | 1   | 1    |                 |        |
| whereF,H,X∈Rn×n,G |              | ∈Rn×m,G |     | ∈Rm×m,andG |     |      |                 |        |
|                   |              |         |     |            |     |      | =GT >0.Weassume |        |
|                   |              | 1       |     | 2          |     | 2    | 2               |        |
that(F, G 1 )isastabilizablepairandthat(F,C)isadetectablepair.Wealsodefine
−1GT.
G=G G
|     | 1 2 1 |     |     |     |     |     |     |     |
| --- | ----- | --- | --- | --- | --- | --- | --- | --- |
It is well known [136] that solutions to DARE (5.30) are closely linked with a
| matrixpencilpair(M, |     | L),where |     |         |         |         |     |        |
| ------------------- | --- | -------- | --- | ------- | ------- | ------- | --- | ------ |
|                     |     | (cid:2)  |     | (cid:3) | (cid:2) | (cid:3) |     |        |
|                     |     |          | F   |         |         | I G     |     |        |
|                     |     | M=       | 0   |         | L=      |         |     |        |
|                     |     |          | −H  | ,       |         |         |     | (5.31) |
|                     |     |          | I   |         |         | 0 FT    |     |        |
n×n
It also can be shown that if there exist matrices S, U 1 and U 2 , with U 1
invertible,suchthat
|     |     |     | (cid:2) | (cid:3) | (cid:2) (cid:3) |     |     |        |
| --- | --- | --- | ------- | ------- | --------------- | --- | --- | ------ |
|     |     |     | U       | 1 =L    | U 1             |     |     |        |
|     |     |     | M       |         | S               |     |     | (5.32) |
|     |     |     | U       |         | U               |     |     |        |
|     |     |     |         | 2       | 2               |     |     |        |
then, X = U U −1 is a solution to (5.30). Further, the matrix F − G (G +
|     | 2 1 |     |     |     |     |     |     | 1 2 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
−1GTXF
GTXG ) sharesthesamespectrumasS.Hence,ifS isstable,i.e.allthe
| 1                                     | 1 1 |     |     |     |      |       |        |        |
| ------------------------------------- | --- | --- | --- | --- | ---- | ----- | ------ | ------ |
|                                       |     |     |     |     | −G   | +GTXG | −1GTXF |        |
| eigenvaluesarewithintheopenunitdisc,F |     |     |     |     | 1 (G | 2     | 1 )    | isalso |
|                                       |     |     |     |     |      | 1     |        | 1      |
stable.Suchan X isnon-negativedefiniteandunique,andiscalledthestabilizing
solutionto(5.30).
Under the above assumptions on (5.30), it was shown in [136] that none of the
generalizedeigenvaluesofthepair(M,L) liesontheunitcircle,andif λ(cid:3)=0 isa
generalizedeigenvalueofthepair,then1/λisalsoageneralizedeigenvalueofthe
samemultiplicity.Inotherwords,thestablespectrum,consistingof n generalized
eigenvalueslyingintheopenunitdisc,isunique.Therefore,ifthereexistsanother
triple(V ,V ,T)satisfying(5.32),withV beinginvertibleandT stable,thenthere
|     | 1 2 |     |     | 1   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
=R −1SR.Consequently,
mustexistaninvertibleRsuchthatT
|                                           |     |     | (cid:2) (cid:3) | (cid:2) | (cid:3) |     |        |        |
| ----------------------------------------- | --- | --- | --------------- | ------- | ------- | --- | ------ | ------ |
|                                           |     |     | U               | V       |         |     |        |        |
|                                           |     |     | 1               | =       | 1 R −1  |     |        | (5.33) |
|                                           |     |     | U 2             | V       | 2       |     |        |        |
|                                           |     |     |                 |         | X=V     |     | −1=(U  | −1=    |
| Thesolution,ofcourse,remainsthesame,since |     |     |                 |         |         | 2 V | 2 R)(U | 1 R)   |
1
U U −1.
2
1
Inthepresentcase,wecanaccordinglydefinethethreematrixpencilsas
|     | (cid:2) | (cid:3) |     |     |     |     |     |     |
| --- | ------- | ------- | --- | --- | --- | --- | --- | --- |
|     | = Φ     | 0       |     |     |     |     |     |     |
| M   | −1C     |         |     |     |     |     |     |     |
|     | P −CTR  | I       |     |     |     |     |     |     |
1
|     | (cid:2) | (cid:3) |     |     |     |     |     | (5.34) |
| --- | ------- | ------- | --- | --- | --- | --- | --- | ------ |
−1BT
I BR
|     | L = 2 |     |     |     |     |     |     |     |
| --- | ----- | --- | --- | --- | --- | --- | --- | --- |
|     | P ΦT  |     |     |     |     |     |     |     |
0

60 5 H∞Loop-ShapingDesignProcedures
(cid:2) (cid:3)
ΦT 0
M Q = −BR −1BT I
2
(cid:2) (cid:3) (5.35)
I CTR −1C
L = 1
Q
0 Φ
⎡ (cid:30) (cid:31) ⎤
⎢ ⎢ A− −HZ 2 −1 BR 2 −1/2 ! R −1 DT Z R 2 − − 1 1 C /2 C 0⎥ ⎥
M X =⎢ ⎢ ⎣ −CTC+ CTZ 2 −1 CTR 1 −1/2 D ! R −1 (cid:30) D 1 T Z R 2 − − 1 1 C /2 C (cid:31) I ⎥ ⎥ ⎦
1
⎡ (cid:30) (cid:31) ⎤ (5.36)
! −Z −1HT
⎢I −HZ −1 BR −1/2 R −1 2 ⎥
L X = ⎢ ⎢ ⎢ ⎣ 2 2 ! R 2 − (cid:30) 1 − /2 Z B − T 1HT (cid:31) ⎥ ⎥ ⎥ ⎦
0 AT − CTZ −1 CTR −1/2 D R −1 2
2 1 R −1/2 BT
2
With all the above properties of the DAREs and the notations, the following
theoremmaybeproved[68].
Theorem5.1 Let P, Q and X∞ bethestabilizingsolutionstotheDAREs(5.17),
(5.18)and(5.23),(or,(5.26),(5.27)and(5.28)when G isstrictlyproper),respec-
tively,thefollowingidentityholds:
(cid:4)(cid:6) (cid:7) (cid:5)
X∞ =P 1−γ −2 I
n
−γ −2QP −1
(cid:4) (cid:5)
=γ2P γ2I −(I +QP)
−1
(5.37)
n n
Asimilarresultcanbefoundin[173]fortherelationshipbetweenthreediscrete-
timealgebraicRiccatiequationsarisinginthegeneralH ∞ suboptimaldesign.The
results concerning the discrete-time loop-shaping design procedure are with three
differentDAREsandtheconclusionisofaslightlydifferentform.
5.4 AMixedOptimizationDesignMethod withLSDP
Itiswellknownthatcontrol-systemdesignproblemscanbenaturallyformulatedas
constrainedoptimizationproblems,thesolutionsofwhichwillcharacterizeaccept-
abledesigns.Thenumericaloptimizationapproachtocontrollerdesigncandirectly
tackle design specifications in both the frequency domain and the time domain.
The optimization problems derived, however, are usually very complicated with
manyunknowns,manynonlinearities,manyconstraints,andinmostcasestheyare
multiobjectivewith several conflictingdesign aims that need to be simultaneously
achieved. It is also known that a direct parameterization of the controller will in-
creasethecomplexityoftheoptimizationproblem.

5.4 AMixedOptimizationDesignMethodwithLSDP 61
On the other hand, the H ∞ loop-shaping design procedure (LSDP) discussed
inthischapterisanefficient,robustdesignmethodthatjustdependsonappropriate
choiceofweightingfunctionstoshapetheopen-loopsystem.Ingeneral,theweight-
ingfunctionsareofloworders.Thisindicatesifwetaketheweightingfunctionsas
designparametersitmaywellcombinetheadvantagesofboththenumericalopti-
mizationapproachandtheH ∞LSDPintermsofflexibleformulationofdesignob-
jectives,maturenumericalalgorithms,tractableoptimizationproblems,guaranteed
stability and a certain degree of robustness. Such a design method is proposed in
[178].Thenumericaloptimizationcomponentofthemethodisbasedonthemethod
ofinequalities(MOI).
Performancespecificationsfor control-systemsdesignarefrequently,andmore
naturally, given in terms of algebraic or functional inequalities, rather than in the
minimizationofsomeobjectivefunction.Forexample,thesystemmayberequired
tohavearisetimeoflessthanonesecond,asettlingtimeoflessthanfiveseconds
andanovershootoflessthan10%.Insuchcases,itisobviouslymorelogicaland
convenient if the design problem is expressed explicitly in terms of such inequal-
ities. The method of inequalities [191] is a computer-aided multiobjective design
approach,wherethedesiredperformanceis representedbysuchasetof algebraic
inequalities and where the aim of the design is to simultaneously satisfy these in-
equalities.Thedesignproblemisexpressedas
φ (p)≤(cid:18) , fori=1,...,n (5.38)
i i
where (cid:18) are real numbers, p∈P is a real vector (p ,p ,...,p ) chosen from a
i 1 2 q
given set P, and φ are real functions of p. The functions φ are performance in-
i i
dices,thecomponentsofprepresentthedesignparameters,and(cid:18) arechosenbythe
i
designerandrepresentthelargesttolerablevaluesofφ .Theaimisthesatisfaction
i
ofthesetofinequalitiessothatanacceptabledesignpisreached.
Forcontrol-systemsdesign,thefunctionsφ (p)maybefunctionalsofthesystem
i
stepresponse,forexample,therise-time,overshootortheintegralabsolutetracking
error, or functionals of the frequency responses, such as the bandwidth. They can
also represent measures of the system stability, such as the maximum real part of
theclosed-looppoles.Additionalinequalitiesthatarisefromthephysicalconstraints
of the system can also be included, to restrict, for example, the maximum control
signal.Inpractice,theconstraintsonthedesignparametersp thatdefinethesetP
arealsoincludedintheinequalityset,e.g.toconstrainthepossiblevaluesofsome
ofthedesignparametersortolimitthesearchtostablecontrollersonly.
Each inequality φ (p) ≤ (cid:18) of the set of inequalities (5.38) defines a set S
i i i
of points in the q-dimensional space Rq and the coordinates of this space are
p ,p ,...,p ,so
1 2 q
(cid:12) (cid:13)
S = p:φ (p)≤(cid:18) (5.39)
i i i
Theboundaryofthissetisdefinedby φ (p)=(cid:18) .Apoint p∈Rq isasolutionto
i i
thesetofinequalities(5.38)ifandonlyifitliesinsideeverysetS ,i=1,2,...,n,
i

62 5 H∞Loop-ShapingDesignProcedures
andhenceinsidethesetS thatdenotestheintersectionofallthesetsS :
i
"n
S= S (5.40)
i
i=1
S is called the admissible set and any point p in S is called an admissible point
denotedp .
s
The objective is thus to find a point p such that p∈S. Such a point satisfies
the set of inequalities (5.38) and is said to be a solution. In general, a point p is
s
not unique unless the set S is a singleton in the space Rq. In some cases, there is
no solution to the problem, i.e. S is an empty set. It is then necessary to relax the
boundaries of some of the inequalities, i.e. increase some of the numbers (cid:18) , until
i
anadmissiblepointp isfound.
s
Theactualsolutiontothesetofinequalities(5.38)maybeobtainedbymeansof
numericalsearchalgorithms,suchasthemoving-boundariesprocess(MBP);details
oftheMBPmaybefoundin[176,191].Theprocedureforobtainingasolutionis
interactive, in that it requires supervision and intervention from the designer. The
designerneedstochoosetheconfigurationofthedesign,whichdeterminesthedi-
mensionofthedesignparametervectorp,andinitialvaluesforthedesignparam-
eters. The progress of the search algorithm should be monitored and, if a solution
is not found, the designer may either change the starting point, relax some of the
desired bounds (cid:18) , or change the design configuration. Alternatively, if a solution
i
isfoundeasily,toimprovethequalityofthedesign,theboundscouldbetightened
or additional design objectives could be included in (5.38). The design process is
thusatwo-wayprocess,withtheMOIprovidinginformationtothedesignerabout
conflictingrequirements,andthedesignermakingdecisionsaboutthe“trade-offs”
betweendesignrequirementsbasedonthisinformationaswellasonthedesigner’s
knowledge,experience,andintuitionabouttheparticularproblem.Thedesignercan
besupportedinthisrolebyvariousgraphicaldisplays[131]orexpertsystems[66].
A difficult problem in control-systems design using the MOI method is how
to define the design parameter vector p. A straightforward idea is to directly
parametrize the controller, i.e. let p be the system matrices of the controller, or
thecoefficientsofthenumeratoranddenominatorpolynomialsofthecontroller.In
doingso,thedesignerhastochoosetheorderofthecontrollerfirst.Ingeneral,the
lowerthedimensionofthedesignvectorp,theeasieritisfornumericalsearchal-
gorithmstofindasolution,ifoneexists.Choosingalow-ordercontroller,sayaPI
controllerp +p2,mayreducethedimensionofp.However,itmaynotyieldaso-
1 s
lutionand,inthatcase,asolutionmayexistwithhigherordercontrollers.Afurther
limitationofusingtheMOIaloneinthedesignisthataninitialpointthatgivesthe
stabilityoftheclosed-loopsystemmustbelocatedasaprerequisitetosearchingthe
parameterspaceinordertoimprovetheindexsetof(5.38).
TwoaspectsoftheH ∞ LSDPmakeitamenabletocombinethisapproachwith
theMOI.First,unlikethestandardH ∞-optimizationapproaches,theH ∞-optimal
controller for the weighted plant can be synthesized from the solutions of two al-
gebraic Riccati equations (5.5) and (5.7) and does not require time-consuming γ-

5.4 AMixedOptimizationDesignMethodwithLSDP 63
iteration.Second,intheLSDPdescribedearlierinthischapter,theweightingfunc-
tions are chosen by considering the open-loop response of the weighted plant, so
effectivelythe weights W and W are the design parameters.This means that the
1 2
designproblemcanbeformulatedasinthemethodofinequalities,withtheparam-
eters of the weighting functions used as the design parameters p to satisfy the set
of closed-loopperformanceinequalities.Suchan approachto the MOI overcomes
the limitations of the MOI. The designer does not have to choose the order of the
controller,butinsteadchoosestheorderoftheweightingfunctions.Withlow-order
weightingfunctions,high-ordercontrollerscanbesynthesizedthatoftenleadtosig-
nificantlybetterperformanceorrobustnessthanifsimplelow-ordercontrollerswere
used.Additionally,theproblemoffindinganinitialpointforsystemstabilitydoes
not exist, because the stability of a closed-loop system is guaranteed through the
solution to the robust stabilization problem, provided that the weighting functions
donotcauseundesirablepole/zerocancellations.
Thedesignproblemisnowstatedasfollows.
Problem ForthesystemofFig.5.2,finda(W ,W )suchthat
1 2
γ (W ,W )≤(cid:18) (5.41)
o 1 2 γ
and
φ (W ,W )≤(cid:18) fori=1,...,n (5.42)
i 1 2 i
where
(cid:4) (cid:5)
γ = 1+λ (ZX) 1/2
o max
withZandXthesolutionsofthetwoAREs,(5.5)and(5.7),oftheweightedplant.
In the above formulation, φ are functionals representing design objectives, (cid:18)
i γ
and (cid:18) are real numbers representing desired bounds on γ and φ , respectively,
i o i
and (W ,W ) a pair of fixed order weighting functions with real parameters w=
1 2
(w ,w ,...,w ).
1 2 q
Consequently,adesignprocedurecanbestatedasfollows.
DesignProcedure Adesignproceduretosolvetheaboveproblemis
1. DefinetheplantG,anddefinethefunctionalsφ .
i
2. Definethevaluesof(cid:18) and(cid:18) .
γ i
3. DefinetheformandorderoftheweightingfunctionsW andW .Boundsshould
1 2
beplacedonthevaluesofw toensurethatW andW arestableandminimum
j 1 2
phasetopreventundesirablepole/zerocancellations.Theorderoftheweighting
functions,andhencethevalueofq,shouldbesmallinitially.
4. Define initial values of w based on the open-loop frequency response of the
j
plant.

64 5 H∞Loop-ShapingDesignProcedures
5. ImplementtheMBP,orotherappropriatealgorithms,inconjunctionwith(5.12)
or(5.13)tofinda(W ,W )thatsatisfiesinequalities(5.41)and(5.42).Ifasolu-
1 2
tionisfound,thedesignissatisfactory;otherwise,eitherincreasetheorderofthe
weightingfunctions,or relaxoneormoreofthedesiredbounds (cid:18),ortryagain
withdifferentinitialvaluesofw.
6. Withsatisfactory weightingfunctions W and W ,a satisfactoryfeedbackcon-
1 2
trollerisobtainedfrom(5.12)or(5.13).
Thismixedoptimizationdesignapproachhasbeenappliedinsomedesigncases.
Examplesofapplicationandsomeextensionscanbefoundin[124,160,177–181].

| Chapter 6  |     |           |     |     |     |
| ---------- | --- | --------- | --- | --- | --- |
| μ-Analysis | and | Synthesis |     |     |     |
Asdiscussedearlierinthebook,theH ∞optimizationapproachmayachieverobust
stabilizationagainstunstructuredsystemperturbationsandnominalperformancere-
quirements.Itisthoughpossiblethatbyapplyingappropriateweightingfunctions
some robust performance requirements can be obtained. Satisfactory designs have
beenreported,inparticularwhenusingtheH
∞loop-shapingdesignmethods.Inor-
dertoachieverobuststabilityandrobustperformance,designmethodsbasedonthe
structuredsingularvalueμcanbeused.Inthischapter,wefirstshowhowarobust
performancedesignspecificationforacontrolsystemwithunstructured/structured
perturbationscanbetransformedintoarobuststabilizationproblemwithregardto
structuredperturbation.Wethendiscusshowthesedesignspecificationsarerelated
to some indications of this new setting, followed by introduction of two iterative
| μ-synthesismethods,theD–K |     | iterationandμ–K | iterationmethods. |     |     |
| ------------------------- | --- | --------------- | ----------------- | --- | --- |
∈Cn×n
We recall, as defined in Chap. 3, for M and a known structure of Δ
(usuallyrepresentinguncertainties),
| (cid:12)        |          |                                               |          | (cid:13) |       |
| --------------- | -------- | --------------------------------------------- | -------- | -------- | ----- |
| (cid:2)= diag[δ |          |                                               | ]:δ ∈C,Δ | ∈Cmj ×mj |       |
|                 | I ,...,δ | I ,Δ ,...,Δ                                   |          |          | (6.1) |
|                 | 1 r1     | s rs 1                                        | f i      | j        |       |
| (cid:26)        | (cid:26) |                                               |          |          |       |
| s +             | f        | =nwithnisthedimensionoftheblockΔ,thestructure |          |          |       |
| where r         | m        |                                               |          |          |       |
| i=1 i           | j=1 j    |                                               |          |          |       |
singularvalueμisdefinedby
|                                   |            | (cid:12)     |        | (cid:13) |       |
| --------------------------------- | ---------- | ------------ | ------ | -------- | ----- |
|                                   | −1(M):=min | σ(Δ):det(I   | −MΔ)=0 |          |       |
|                                   | μ          |              |        |          | (6.2) |
|                                   | Δ          | Δ∈(cid:2)    |        |          |       |
| IfthereisnoΔ∈(cid:2)suchthatdet(I |            | −MΔ)=0,thenμ |        | (M):=0.  |       |
Δ
SomeimportantpropertiesofμhavebeenlistedinChap.3.
| 6.1 Considerationof |     | RobustPerformance |     |     |     |
| ------------------- | --- | ----------------- | --- | --- | --- |
WhenM isaninterconnectedtransferfunctionmatrixM(s)formedwithrespectto
theuncertaintyset(cid:2),thestructuredsingularvalueofM(s)
D.-W.Guetal.,RobustControlDesignwithMATLAB®,
65
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_6,©Springer-VerlagLondon2013

66 6 μ-AnalysisandSynthesis
Fig.6.1 StandardM–Δ
configuration
Fig.6.2 StandardM–Δ
configurationforRPanalysis
(cid:6) (cid:7) (cid:6) (cid:7)
μ M(s) := sup μ M(jω) (6.3)
Δ Δ
ω∈R
indicatestherobuststabilityoftheperturbedsystem.Withoutlossofgenerality,we
assume that the uncertainties have been normalized in the rest of this chapter, i.e.
Δ∈B(cid:2).FromTheorem3.4,thestandardconfigurationFig.6.1isrobustlystableif
M(s)isstableandμ (M(s))<1(or(cid:5)M(cid:5) <1).
Δ μ
AsdiscussedinChap.3indesignofcontrolsystems,inadditiontothestability
the performance of the system must be taken into account. The designed system
shouldperformwell(for instance,goodtracking)againstexogenousdisturbances,
whichrequiresaclosed-loopstructure.Thefeedbackcontrollerisusuallydesigned
basedonanominalplantmodel.Inthecaseoftheexistenceofplantperturbations,
the closed-loop system may well possibly perform badly, even degrade to an un-
satisfactory level. The robust performance requires that a designed control system
maintains a satisfactory performance level even in the presence of plant dynamic
uncertainties.
We now expand Fig. 6.1 to include input and output signals, as depicted in
Fig.6.2.
In Fig. 6.2, w, z, v and d are usually vector signals. w denotes the exogenous
inputtypicallyincludingcommandsignals,disturbances,noises,etc.;zdenotesthe
erroroutputusuallyconsistingofregulatoroutput,trackingerrors,filteredactuator
signals,etc.;v andd aretheinputandoutputsignalsofthedynamicuncertainties.
System-performancespecificationscanusuallybeinterpretedasreductionofzwith
respect of w. With the assumption that w and z are both energy-bounded signals,
theperformancerequirementisequivalenttotheminimizationoftheH ∞ normof
thetransferfunctionfromwtoz.LetM bepartitionedaccordinglyas
(cid:2) (cid:3)
M M
M= 11 12
M M
21 22

6.1 ConsiderationofRobustPerformance 67
Fig.6.3 StandardM–Δ
configurationwithΔp
analysis
itcaneasilybederivedthat
| (cid:4) |     |        | (cid:5)  |     |
| ------- | --- | ------ | -------- | --- |
| z= M    | +M  | Δ(I −M | Δ) −1M w |     |
|         | 22  | 21     | 11 12    |     |
=F
| u   | (M,Δ)w |     |     | (6.4) |
| --- | ------ | --- | --- | ----- |
Usingnormalization,asatisfactorylevelofperformancerequirementcanbeset
as
|     | (cid:24) | (cid:24) |     |       |
| --- | -------- | -------- | --- | ----- |
|     | (cid:24) | (cid:24) |     |       |
|     | F (M,Δ)  | <1       |     | (6.5) |
|     | u        | ∞        |     |       |
Equation (6.5) implies the stability of F (M,Δ), which means robust stability
u
withrespecttotheplantperturbationsΔ.
Condition(6.5)isequivalenttothesystemloopinFig.6.3toberobustlystable
withregardtoafictitiousuncertaintyblockΔ .Δ isunstructuredwithappropriate
p p
dimensions,satisfies(cid:5)Δ (cid:5) ≤1andisusuallycalledtheperformanceuncertainty
p ∞
block.Thepartenclosedinthedottedlineis,ofcourse,F (M,Δ).
u
Forrobustperformance,(6.5)shouldholdforallΔ∈B(cid:2).BasedonFig.6.3,the
robustperformancedesignaswellasrobuststabilizationagainstΔ,canbeequiva-
lentlyconsideredasarobuststabilizationprobleminFig.6.1withtheuncertainty
˜
blocktobereplacedbyΔwhere
(cid:12) (cid:13)
˜
| Δ ˜∈(cid:2) := | diag{Δ,Δ | }:Δ∈B(cid:2),(cid:5)Δ | (cid:5) ≤1 |     |
| -------------- | -------- | --------------------- | ---------- | --- |
|                |          | p                     | p ∞        |     |
Thisisthusarobuststabilizationproblemwithrespecttoastructureduncertainty
˜
(cid:2).And,wehavethefollowingindications.
˜
• RobustPerformance(RP)⇐⇒(cid:5)M(cid:5) <1,forstructureduncertainty(cid:2)
μ
• RobustStability(RS)⇐⇒(cid:5)M (cid:5) <1,forstructureduncertaintyB(cid:2)
11 μ
• NominalPerformance(NP)⇐⇒(cid:5)M (cid:5)
|     |     | 22 ∞<1 |     |     |
| --- | --- | ------ | --- | --- |
• NominalStability(NS)⇐⇒M isinternallystable
Ofcourse,iftheuncertaintyΔisunstructured,thentherobuststabilityrequire-
mentcorrespondsto(cid:5)M (cid:5)
∞<1.
11
Itiseasytoseethat,bysettingΔ ≡0,(cid:5)M(cid:5) <1implies(cid:5)M (cid:5) <1.Hence,
|     |     | p   | μ 11 μ |     |
| --- | --- | --- | ------ | --- |
the former condition yields a robust stability and robust performance (RSRP) de-
sign.

| 68  |     |     |     |     | 6 μ-AnalysisandSynthesis |     |     |
| --- | --- | --- | --- | --- | ------------------------ | --- | --- |
Fig.6.4 StandardM–Δ
configurationwithK
| 6.2 μ-Synthesis: | D–K | Iteration | Method |     |     |     |     |
| ---------------- | --- | --------- | ------ | --- | --- | --- | --- |
The transfer function matrix M(s) in Fig. 6.2 usually contains the controller K,
henceaclosed-loopinterconnectedmatrix.Forthepurposeofcontrollerdesign,we
mayrearrangetheconfigurationandexplicitlyshowthedependenceoftheclosed-
loopsystemonthecontrollerK.Thatis,Fig.6.2isagainshowninFig.6.4.
Thenominal,open-loopinterconnectedtransferfunctionmatrixP(s)inFig.6.4
doesnotincludethecontrollerK(s)noranyperturbationsthatareunderconsider-
ation.P(s)maybepartitionedas
|     |     |        | ⎡      | ⎤       |     |     |     |
| --- | --- | ------ | ------ | ------- | --- | --- | --- |
|     |     |        | P P    | P       |     |     |     |
|     |     |        | 11     | 12 13   |     |     |     |
|     |     | P(s)=⎣ |        | ⎦       |     |     |     |
|     |     |        | P 21 P | 22 P 23 |     |     |     |
|     |     |        | P P    | P       |     |     |     |
|     |     |        | 31     | 32 33   |     |     |     |
The signals y and u represent the feedback signals (measured output, tracking
error, etc., the input to the controller) and the control signal (the output from the
controller),respectively.
TherelationshipbetweenMinFig.6.2andP canbeobtainedbystraightforward
calculationsas
M(P,K)=F(P,K)
l
|     | (cid:2) | (cid:3) | (cid:2) (cid:3) |        |         |         |       |
| --- | ------- | ------- | --------------- | ------ | ------- | ------- | ----- |
|     |         |         |                 |        | (cid:4) | (cid:5) |       |
|     |         | P P     | P               |        | −1      |         |       |
|     | =       | 11 12   | + 13            | K(I −P | K) P    | P       | (6.6) |
|     |         | P P     | P               | 33     | 31      | 32      |       |
|     |         | 21 22   | 23              |        |         |         |       |
whereM(s)isexplicitlywrittenasM(P,K)toshowthatM isformedbyP andK.
FortheRSRPdesign,itisrequiredtofindastabilizingcontrollerK suchthat
|     |     | (cid:4) |            | (cid:5) |     |     |       |
| --- | --- | ------- | ---------- | ------- | --- | --- | ----- |
|     |     | sup μ   | M(P,K)(jω) | <1      |     |     | (6.7) |
ω∈R
˜
wherethesubscriptΔhasbeensuppressedforthesakeofsimplicity.
Or,forthe“optimal”RSRPdesign,theobjectiveistosolveforK
|     |     |         | (cid:4)      | (cid:5) |     |     |       |
| --- | --- | ------- | ------------ | ------- | --- | --- | ----- |
|     |     | inf sup | μ M(P,K)(jω) |         |     |     | (6.8) |
K(s)ω∈R

6.2 μ-Synthesis:D–KIterationMethod 69
An iterative method was proposed to solve (6.8) in [32]. The method is called
the D–K iteration μ-synthesis method, and is based on solving the following op-
timization problem, for a stabilizing controller K and a diagonal constant scaling
matrixD:
|         | (cid:4)        |        | (cid:5) |       |
| ------- | -------------- | ------ | ------- | ----- |
| inf sup | inf σ DM(P,K)D | −1(jω) |         | (6.9) |
K(s)ω∈RD∈D
where the scaling matrix set D is defined in Sect. 3.3. The justification for using
(6.9)isobvious,fromTheorem3.7andthediscussionafterwards,withμ[M(P,K)]
−1].
replacedbyitsupperboundinf σ[DM(P,K)D
D∈D
Corresponding to the case of (6.7), a stabilizing controller is to be found such
that
|     | (cid:4) | (cid:5) |     |     |
| --- | ------- | ------- | --- | --- |
−1(jω)
| sup inf | σ DM(P,K)D |     | <1  | (6.10) |
| ------- | ---------- | --- | --- | ------ |
ω∈RD∈D
TheD–K iterationmethodistoalternatelyminimize(6.9),ortoreducetheleft-
hand-sidevalueof(6.10),forK andDinturnwhilekeepingtheotheronefixed.
ForagivenmatrixD,eitherconstantortransferfunction,(6.9)isastandardH
∞
optimizationproblem
|     | (cid:24) | (cid:24)   |     |        |
| --- | -------- | ---------- | --- | ------ |
|     | (cid:24) | −1(cid:24) |     |        |
| inf | DM(P,K)D |            |     | (6.11) |
∞
K(s)
thatcanbefurtherwrittenas
| (cid:24)          | (cid:24)        | (cid:24) (cid:6)  | (cid:7)(cid:24) |        |
| ----------------- | --------------- | ----------------- | --------------- | ------ |
| (cid:24) DF(P,K)D | −1(cid:24) =inf | (cid:24) F P ˜ ,K | (cid:24)        |        |
| inf l             | ∞               | l                 | ∞               | (6.12) |
| K                 |                 | K                 |                 |        |
(cid:4) (cid:5) (cid:4) (cid:5)
withP ˜ = D0 P D−10 compatiblewiththepartitionofP.
0 I 0 I
On the other hand, for a fixed K(s), inf σ[DM(P,K)D −1(jω)] is a con-
D∈D
vexoptimizationproblemateachfrequencyω.Aftertheminimizationoverarange
of frequency of interest, the resultant diagonal (constant) matrices Ds can be ap-
proximated,viacurvefitting,byastable,minimumphase,rationaltransferfunction
matrixD(s),whichwillbeusedinthenextiterationforK.
TheD–K iterativeμ-synthesisalgorithmisthus:
Step1: StartwithaninitialguessforD,usuallysetD=I.
FixDandsolvetheH
Step2: ∞-optimizationforK,
|     | (cid:24)   | (cid:6) (cid:7)(cid:24) |     |     |
| --- | ---------- | ----------------------- | --- | --- |
|     | (cid:24)   | ˜ (cid:24)              |     |     |
|     | K=arginf F | P ,K                    |     |     |
|     |            | l ∞                     |     |     |
K
Step3: FixK andsolvethefollowingconvexoptimizationproblemforD ateach
frequencyoveraselectedfrequencyrange:
|           | (cid:4)        |     | (cid:5) |     |
| --------- | -------------- | --- | ------- | --- |
| D(jω)=arg |                |     | −1(jω)  |     |
|           | inf σ DF(P,K)D | l   |         |     |
D∈D

70 6 μ-AnalysisandSynthesis
Step4: Curve fit D(jω) to get a stable, minimum-phase D(s); go to Step 2 and
repeat, until a prespecified convergence tolerance or (6.10) is achieved, or a
prespecifiedmaximumiterationnumberisreached.
Successful applications of the D–K iteration method have been reported. This
methodhasalsobeenappliedinthecasestudiesinPartIIofthisbook.Itshouldbe
noticed,however,thatthealgorithmmaynotconvergeinsomecases.Theresultant
controller may be very conservative, particularly in the case of real and/or mixed
perturbations, due to the possible gap between μ(M) and inf D∈D σ[DMD −1] in
general cases, and due to the lack of powerful algorithms to compute the real and
mixedμvaluesandtosolvetheoptimizationproblemforD.Anotheradverseeffect
inpracticaldesignsisthattheorderofresultantμ-controllersisusuallyveryhigh,
andhencecontroller-orderreductionmustbeapplied.
6.3 μ-Synthesis: μ–K IterationMethod
As discussed above,the structured singular value μ plays an importantrole in the
robuststabilityandrobustperformancedesigns.Theμ-designistoseekastabilizing
controllerthateitherminimizesorreducestheμvalueoverafrequencyrange.There
is another design method proposed in the literature that can be applied to find a
μ-controller.Thatistheso-calledμ–K iterationmethod[99,101,139].
Itisshownin[72]thatinmanyoptimization-basedcontrol-systemdesigns,the
resultant,optimalcontrollerwillmakea“well-posed”costfunction(i.e.satisfying
certainassumptions[72],Theorem4.1)constant inthefrequency ω almostevery-
where. This feature is obvious in the H ∞ optimizations and can also be observed
in the μ-designs using the D–K iterations where the controller K(s) obtained in
the iteration gradually flattens the curve of μ(M). The μ–K iteration method is
motivated by the above. In the μ–K iterations, the obtained μ curves are used as
weighting functions on the H ∞ cost function (cid:5)F l (P ˜ ,K)(cid:5) ∞ with the aim to sup-
pressthepeakvaluesofthe μ curvesinthesuccessiveiterations.Analgorithmto
implementtheμ–K iterationmethodisdescribedbelow.
Step1: SolvetheH ∞-optimizationproblemforK
0
,
(cid:24) (cid:6) (cid:7)(cid:24)
K :=arginf (cid:24) F P ˜ ,K (cid:24)
0 l ∞
K
Step2: ComputetheμcurvecorrespondingtoK overachosenfrequencyrange,
0
(cid:4) (cid:5)
μ (jω):=μ F(P,K )(jω)
0 l 0
Step3: Normalizeμ byitsmaximumvalue,i.e.
0
μ
μ˜ := 0
0
max μ
ω 0
Step4: Curvefitμ˜ (jω)togetastable,minimum-phase,rationalμ˜ (s).
0 0

| 6.3 μ-Synthesis:μ–KIterationMethod |     |     | 71  |
| ---------------------------------- | --- | --- | --- |
SolvefortheH
| Step5: | ∞ optimalcontrollerK | 1 (s), |     |
| ------ | -------------------- | ------ | --- |
(cid:24) (cid:6) (cid:7)(cid:24)
(cid:24) ˜ (cid:24)
|     | K :=arginf | μ˜ F P ,K | (6.13) |
| --- | ---------- | --------- | ------ |
|     | 1          | 0 l ∞     |        |
K
go to Step 2, multiply the newly obtained μ curve function onto the previous
cost function in (6.13) (e.g. (cid:5)μ˜ μ˜ F (P ˜ ,K)(cid:5) ∞); repeat until the μ curve is
1 0 l
sufficiently flat or until a desired level of performance (measured by the peak
valueofμ)hasbeenachieved.

Chapter 7
Lower-Order Controllers
There is a dilemma concerning design of control systems. Due to increasing de-
mands on quality and productivity of industrial systems and with deeper under-
standing of these systems, mathematical models derived to represent the system
dynamicsare morecomplete,usuallyof multi-input-multi-outputform,andare of
highorders.Consequently,thecontrollersdesignedarecomplex.Theorderofsuch
controllers designed using, for instance, the H ∞ optimization approach or the μ-
method,ishigherthan,oratleastsimilarto,thatoftheplant.Ontheotherhand,in
theimplementationofcontrollers,high-ordercontrollerswillleadtohighcost,diffi-
cultcommissioning,poorreliabilityandpotentialproblemsinmaintenance.Lower-
ordercontrollersarealwayswelcomedbypracticingcontrolengineers.Hence,how
toobtainalow-ordercontrollerforahigh-orderplantisanimportantandinteresting
task,andisthesubjectofthepresentchapter.
Ingeneral,therearethreedirectionstoobtainalower-ordercontrollerforarela-
tivelyhigh-orderplant,asdepictedinFig.7.1,
(1) plantmodelreductionfollowedbycontrollerdesign;
(2) controllerdesignfollowedbycontroller-orderreduction;and,
(3) directdesignoflow-ordercontrollers.
Approaches(1)and(2)arewidelyusedandcanbeusedtogether.Whenacon-
trollerisdesignedusingarobustdesignmethod,Approach(1)wouldusuallypro-
duce a stable closed loop, though the reduction of the plant order is likely to be
limited. In Approach (2), there is freedom in choosing the final order of the con-
troller,butthestabilityoftheclosed-loopsystemshouldalwaysbeverified.
Thethirdapproachusuallywouldheavilydependonsomepropertiesoftheplant,
and require numerous computations. This approach will not be introduced in this
book.Interestedreadersarereferredto[14,23,65,76,80].
Fromtheviewpointofbeingacontrolsystem,modelreductions(usuallyreferred
tothereductionofordersoftheoriginalplantmodels)andcontrollerreductionsare
similar.Indeed,mostmethodsintroducedinthischapterareapplicableinbothcases,
thoughsomemethodsmaybemoresuitableforoneofthem.Thiswillbediscussed
alongwiththeintroductionofmethods.
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 73
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_7,©Springer-VerlagLondon2013

| 74  |     |     | 7 Lower-OrderControllers |     |
| --- | --- | --- | ------------------------ | --- |
Fig.7.1 Diagramfordesignoflow-ordercontrollers
In this book, only details of continuous-time case reduction will be discussed.
Wherethemethodisapplicableinthediscrete-timecaseaswellreferenceswillbe
given.Whenweusethephraseorderreductionsofplants/systems,weactuallyrefer
totheorderreductionofamodeloftheplant/system.
Intherestofthechapter,lettheoriginalsystemhaveastate-spacerepresentation
|     | G(s):=C(sI | −A) | −1B+D | (7.1) |
| --- | ---------- | --- | ----- | ----- |
(cid:2) (cid:3)
A B
|     |     | =:  |     | (7.2) |
| --- | --- | --- | --- | ----- |
C D
whereA:n×n,B:n×m,C:p×n,D:p×m,and[A,B,C]isassumedtobea
minimalrealization.Areduced-ordersystemG r (s)isrepresentedby
|     | (s):=C | −A        | −1B +D |       |
| --- | ------ | --------- | ------ | ----- |
|     | G r    | r (sI r ) | r r    | (7.3) |
(cid:2) (cid:3)
A B
|     | =:  | r r |     | (7.4) |
| --- | --- | --- | --- | ----- |
C r D r
| :r×r,B                          | :r×m,C :p×r,D | :p×m,andr<n. |     |     |
| ------------------------------- | ------------- | ------------ | --- | --- |
| withA r                         | r r           | r            |     |     |
| 7.1 Absolute-ErrorApproximation |               | Methods      |     |     |
Theaimofthefollowingmethodsistofindareduced-ordersystemG (s)suchthat
r
somenormoftheerrorsystemissmall,i.e.tominimize
|     |     | (cid:24)   | (cid:24) |       |
| --- | --- | ---------- | -------- | ----- |
|     |     | (cid:24)   | (cid:24) |       |
|     |     | G(s)−G (s) |          | (7.5) |
r
Three methods are to be introduced: Balanced Truncation, Singular Perturba-
tionApproximation(BalancedResidualization),andHankel-NormApproximation.
These methods are for stable systems only. The case of unstable systems will be
discussedattheendofthissection.

| 7.1   | Absolute-ErrorApproximationMethods |     |     |        |     |     |     |     | 75  |
| ----- | ---------------------------------- | --- | --- | ------ | --- | --- | --- | --- | --- |
| 7.1.1 | BalancedTruncation                 |     |     | Method |     |     |     |     |     |
Thegeneralideaoftruncationmethodsistoneglectthosepartsoftheoriginalsys-
temthatarelessobservableand/orlesscontrollable.Hopefully,thiswouldleadto
a system that is of lower order and retains the important dynamic behavior of the
original system. However, in some systems, a mode would be weakly observable
buthighlycontrollable,orviceversa.Todeletesuchamodemaybeinappropriate
withregardtothewholecharacteristicsofthesystem.Hence,inthebalancedtrun-
cationmethod[38,39,120,138],astatesimilaritytransformationisappliedfirstto
“balance”thecontrollabilityandobservabilityfeaturesofthesystem.
AstablesystemG(s)iscalledbalancedifthesolutionsP andQtothefollowing
Lyapunovequations:
|     |     |     | AP           | +PAT | +BBT | =0  |     |     | (7.6) |
| --- | --- | --- | ------------ | ---- | ---- | --- | --- | --- | ----- |
|     |     |     | ATQ+QA+CTC=0 |      |      |     |     |     | (7.7) |
are such that P =Q=diag(σ ,σ ,...,σ ):=Σ, with σ ≥σ ≥···≥σ >0.
|     |     |     | 1   | 2   | n   |     | 1   | 2   | n   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
P andQarecalledthecontrollabilityGramianandobservabilityGramian,respec-
tively. When the system is balanced, both Gramians are diagonal and equal. σ ,
i
i=1,...,n,istheithHankelsingularvalueofthesystem.
Forageneralsystemnotinthebalancedrealizationform,thefollowingalgorithm
[92]canbeapplied.
BalancedRealizationAlgorithm
Step1: CalculatetheGramiansP andQfrom(7.6)and(7.7),respectively
Step2: CalculateaCholeskyfactorRofQ,i.e.Q=RTR
Formapositive-definitematrixRPRT
| Step3: |           |                   |      |         |            | anddiagonalizeit, |            |                |               |
| ------ | --------- | ----------------- | ---- | ------- | ---------- | ----------------- | ---------- | -------------- | ------------- |
|        |           |                   |      | RPRT    | =UΣ2UT     |                   |            |                |               |
|        |           |                   |      | UTU     | =I,        |                   | =diag(σ    |                |               |
| where  | U         | is an orthonormal |      | matrix, |            | and               | Σ          | 1 ,σ           | 2 ,...,σ n ), |
| σ      | ≥σ ≥···≥σ |                   | >0   |         |            |                   |            |                |               |
|        | 1 2       | n                 |      |         |            |                   |            |                |               |
|        |           | =Σ −1 2UTR.       | [T,T | −1]     |            |                   |            |                |               |
| Step4: | Let       | T                 |      | is      | a required | state             | similarity | transformation |               |
(balancingtransformation).Thatis,[TAT −1,TB,CT −1]isabalancedrealiza-
tion.
We now assume that the state-space model of the original system G(s),
| [A,B,C,D], |     |            |        |          |             |       |        | =diag(Σ |     |
| ---------- | --- | ---------- | ------ | -------- | ----------- | ----- | ------ | ------- | --- |
|            |     | is already | in the | balanced | realization | form. | Assume | Σ       | 1 , |
Σ ),withΣ =diag(σ ,...,σ ),Σ =diag(σ r+1 ,...,σ ),w(cid:4)hereσ r(cid:5)>σ r+1(cid:4).Th(cid:5)e
| 2        |         | 1       | 1 r                          | 2   |     |     | n         |     |      |
| -------- | ------- | ------- | ---------------------------- | --- | --- | --- | --------- | --- | ---- |
|          |         |         |                              |     |     |     | A= A11A12 |     | = B1 |
| matrices | A,      | B,and C | canbepartitionedcompatiblyas |     |     |     |           | ,   | B ,  |
|          | (cid:4) | (cid:5) |                              |     |     |     | A21A22    |     | B2   |
andC=
|     | C1C2 | .Then,areduced-ordersystemG |     |          |     | r (s)canbedefinedby |         |     |       |
| --- | ---- | --------------------------- | --- | -------- | --- | ------------------- | ------- | --- | ----- |
|     |      |                             |     |          |     | (cid:2)             | (cid:3) |     |       |
|     |      |                             |     |          |     |                     | A B     |     |       |
|     |      | G (s)=C                     | (sI | −A ) −1B | +D= |                     | 11 1    |     | (7.8) |
|     |      | r                           | 1   | 11       | 1   |                     |         |     |       |
|     |      |                             |     |          |     |                     | C 1 D   |     |       |

| 76  |     |     |     |     |     | 7   | Lower-OrderControllers |     |
| --- | --- | --- | --- | --- | --- | --- | ---------------------- | --- |
SuchaG r (s)isofrthorderandiscalledabalancedtruncationofthefullorder
(nth)systemG(s).ItcanbeshownthatG (s)isstable,inthebalancedrealization
r
form,and
|           |                              |     | (cid:24)        |       | (cid:24)        |           |        |       |
| --------- | ---------------------------- | --- | --------------- | ----- | --------------- | --------- | ------ | ----- |
|           |                              |     | (cid:24) G(s)−G |       | (cid:24) ≤2tr(Σ |           |        |       |
|           |                              |     |                 | r (s) | ∞               | 2 )       |        | (7.9) |
|           |                              |     |                 |       |                 | )=σ       | +···+σ |       |
| wheretr(Σ | )denotesthetraceofthematrixΣ |     |                 |       |                 | ,i.e.tr(Σ | r+1    | ,the  |
|           | 2                            |     |                 |       |                 | 2 2       |        | n     |
sumofthelast(n−r)Hankelsingularvalues[39,55].
Inmostapplications,toreducetheoriginalsystemintoanrth-ordersystemthere
| shouldbealargegapbetweenσ |     |     |     | andσ | r+1 ,i.e.σ | (cid:16)σ r+1 . |     |     |
| ------------------------- | --- | --- | --- | ---- | ---------- | --------------- | --- | --- |
|                           |     |     | r   |      |            | r               |     |     |
7.1.2 SingularPerturbationApproximation
Inmanyengineeringsystems,thesteady-stategainofasystem,usuallycalleddc-
gain (the system gain at infinitive time, equivalent to G(0)), plays an important
role in assessing system performances. It is thus better to maintain the dc gain in
areduced-ordermodel,i.e.G (0)=G(0).TheBalancedTruncationmethodintro-
r
duced in the last subsection does not keep the dc gain unchanged in the reduced-
ordersystem.Thesingularperturbationapproximationmethod[103](or,balanced
residualizationmethod[149])presentedbelowdoesretainthedcgain.
Assumethat[A,B,C,D]isaminimalandbalancedrealizationofastablesys-
temG(s),andpartitionedcompatiblyasintheprevioussubsection.Itcanbeshown
thatA isstable(e.g.seeTheorem4.2of[55]),andthusinvertible.Define
22
|     |     |     |     | =A  | −A  | −1A  |     |        |
| --- | --- | --- | --- | --- | --- | ---- | --- | ------ |
|     |     |     | A r | 11  | 12  | A 21 |     | (7.10) |
22
|     |     |     |     | =B −A |      | −1B |     |        |
| --- | --- | --- | --- | ----- | ---- | --- | --- | ------ |
|     |     |     | B r | 1     | 12 A | 2   |     | (7.11) |
22
|     |     |     |     | =C −C | −1A |     |     |        |
| --- | --- | --- | --- | ----- | --- | --- | --- | ------ |
|     |     |     | C r | 1     | 2 A | 21  |     | (7.12) |
22
|     |     |     |     | =D−C | −1B |     |     |        |
| --- | --- | --- | --- | ---- | --- | --- | --- | ------ |
|     |     |     | D r |      | 2 A | 2   |     | (7.13) |
22
| Areduced-ordersystemG |     |     | (s)definedby |     |     |     |     |     |
| --------------------- | --- | --- | ------------ | --- | --- | --- | --- | --- |
r
−1B
|     |     |     | G (s)=C | (sI | −A ) | +D  |     | (7.14) |
| --- | --- | --- | ------- | --- | ---- | --- | --- | ------ |
|     |     |     | r       | r   | r    | r r |     |        |
is called a singular perturbation approximation (or, balanced residualization) of
G(s). It is a straightforward computation to show that the dc-gain remains un-
changed,i.e.
|     |     | −CA | −1B+D=−C |     |     | A −1B +D |     | (7.15) |
| --- | --- | --- | -------- | --- | --- | -------- | --- | ------ |
|     |     |     |          |     | r   | r r r    |     |        |
bynotingthat
|     |     | (cid:2) |        | (cid:3)(cid:2) |     | (cid:3) |     |        |
| --- | --- | ------- | ------ | -------------- | --- | ------- | --- | ------ |
|     |     |         | I      | 0              | I   | 0       |     |        |
|     |     |         |        |                |     | =I      |     | (7.16) |
|     |     |         | −A −1A |                | −1A |         |     |        |
|     |     |         |        | 21 I           | A   | 21 I    |     |        |
|     |     |         | 22     |                | 22  |         |     |        |

| 7.1 Absolute-ErrorApproximationMethods |     |         |     |                |      |         |     | 77     |
| -------------------------------------- | --- | ------- | --- | -------------- | ---- | ------- | --- | ------ |
|                                        |     | (cid:2) |     | (cid:3)(cid:2) |      | (cid:3) |     |        |
|                                        |     | I       | A   | A −1           | I −A | A −1    |     |        |
|                                        |     |         | 12  |                |      | 12      | =I  |        |
|                                        |     |         |     | 22             |      | 22      |     | (7.17) |
|                                        |     | 0       |     | I              | 0    | I       |     |        |
and
(cid:19)(cid:2) (cid:3)(cid:2) (cid:3)(cid:2) (cid:3)(cid:20) (cid:2) (cid:3)
−1
| I   | −A  | A − 1 | A     | A     | I       | 0   | A − 1 0 |          |
| --- | --- | ----- | ----- | ----- | ------- | --- | ------- | -------- |
|     | 1 2 | 22    | 1 1   | 1 2   |         |     | = r     |          |
|     |     |       |       |       | −A − 1A |     | −       | 1 (7.18) |
| 0   | I   |       | A 2 1 | A 2 2 |         | I   | 0 A     |          |
|     |     |       |       |       | 2 2     | 21  | 22      |          |
It can also be shown that such a reduction G (s) is a stable and balanced real-
r
ization [149] and enjoys the same error bound as the balanced truncation method,
i.e.
|     |     | (cid:24) |     | (cid:24) |      |        |     |     |
| --- | --- | -------- | --- | -------- | ---- | ------ | --- | --- |
|     |     | (cid:24) |     | (cid:24) |      |        |     |     |
|     |     | G(s)−G   |     | (s)      | ≤2(σ | +···+σ | )   |     |
|     |     |          |     | r ∞      |      | r+1    | n   |     |
Itcanbeseenthatinsteadofdiscardingthe“lessimportant”parttotallyasinthe
balancedtruncationmethod,thederivativeofx inthefollowingequationissetto
2
zero,inthesingularperturbationapproximation(balancedresidualization)method,
|     |     |     | x˙ =A |      | +A  | +B  |     |        |
| --- | --- | --- | ----- | ---- | --- | --- | --- | ------ |
|     |     |     |       | X    | x   | u   |     | (7.19) |
|     |     |     | 2     | 21 1 | 22  | 2 2 |     |        |
x isthensolvedin(7.19)intermsofx andu,andissubstitutedasresidualintothe
| 2   |     |     |     | 1   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
stateequationofx andoutputequationtoobtainthereduced-ordersystemG (s)
|     |     | 1   |     |     |     |     |     | r   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
asgivenabove.
This idea resembles what happens in analysis of singular perturbation systems
with
|     |     |     | (cid:18)x˙ =A | X   | +A   | x +B | u   |     |
| --- | --- | --- | ------------- | --- | ---- | ---- | --- | --- |
|     |     |     | 2             | 21  | 1 22 | 2 2  |     |     |
where0<(cid:18)(cid:8)1,andhencethetermofsingularperturbationapproximation.
7.1.3 Hankel-NormApproximation
For a stable system G(s) with Hankel singular values defined in Sect. 7.1.1, the
largest Hankel singular value σ is defined as the Hankel-norm of G(s) [55]. The
1
Hankel-normdenotesthelargestpossibleL -gainfrompastinputstofutureoutputs.
2
Insomeorder-reductioncases,minimizationoftheHankel-normoftheerrorsystem
ismoreappropriateandthusrequired.
Approximation1 LetG(s)representastableandsquaresystemwithastate-space
model[A,B,C,D]ofminimalandbalancedrealization.LettheGramiansbeP =
Q=diag(Σ
1 ,σI),whereσ l isthesmallestHankelsingularvaluewithmultiplicity
l and every diagonal element of Σ is larger than σ. Let [A,B,C] be partitioned
1
compatibly.An(n−l)th-ordersystemG (s)canbeconstructedasfollows.Define
h
|     |     |         | (cid:6) |      |          |     | (cid:7) |        |
| --- | --- | ------- | ------- | ---- | -------- | --- | ------- | ------ |
|     |     | ˆ =Γ −1 | σ2A     | T +Σ |          | −σC | TUB T   |        |
|     | A   |         |         | 11   | 1 A 11 Σ | 1   | 1 1     | (7.20) |
|     |     |         | (cid:6) |      | (cid:7)  |     |         |        |
|     |     | ˆ =Γ −1 |         | +σC  | TU       |     |         |        |
|     | B   |         | Σ 1 B   | 1    | 1        |     |         | (7.21) |

| 78  |     |      |      |     |     | 7 Lower-OrderControllers |        |
| --- | --- | ---- | ---- | --- | --- | ------------------------ | ------ |
|     |     | ˆ =C | +σUB | T   |     |                          |        |
|     | C   | 1    | Σ 1  | 1   |     |                          | (7.22) |
ˆ
|     | D   | =D−σU |     |     |     |     | (7.23) |
| --- | --- | ----- | --- | --- | --- | --- | ------ |
whereU isanorthonormalmatrixsatisfying
|     |     |     |     | =−C | TU  |     |        |
| --- | --- | --- | --- | --- | --- | --- | ------ |
|     |     |     |     | B 2 | 2   |     | (7.24) |
and
|     |     |     |     | Γ =Σ | 2−σ2I |     | (7.25) |
| --- | --- | --- | --- | ---- | ----- | --- | ------ |
1
| Thereduced-ordersystemG |     |     | (s)isdefinedas |     |     |     |     |
| ----------------------- | --- | --- | -------------- | --- | --- | --- | --- |
h
|     |     |     | (s)=C | ˆ   | −A ˆ −1B ˆ +D | ˆ   |        |
| --- | --- | --- | ----- | --- | ------------- | --- | ------ |
|     |     |     | G h   | (sI | )             |     | (7.26) |
It is shown in [55] that the (n−l)th-order G (s) is stable and is an optimal
h
approximationofG(s)satisfying
|     |     |     | (cid:24)        |     | (cid:24)    |     |        |
| --- | --- | --- | --------------- | --- | ----------- | --- | ------ |
|     |     |     | (cid:24) G(s)−G |     | (cid:24) =σ |     |        |
|     |     |     |                 |     | h (s)       |     | (7.27) |
H
| And,itisalsotruethatG(s)−G |     |     |     | (s)isall-passwiththeinf-norm |     |     |     |
| -------------------------- | --- | --- | --- | ---------------------------- | --- | --- | --- |
h
|     |     |     | (cid:24) |     | (cid:24) |     |        |
| --- | --- | --- | -------- | --- | -------- | --- | ------ |
|     |     |     | (cid:24) |     | (cid:24) |     |        |
|     |     |     | G(s)−G   |     | (s) =σ   |     | (7.28) |
|     |     |     |          |     | h ∞      |     |        |
Approximation2 ItcanbeshownthattheHankelsingularvaluesofG (s)defined
h
in(7.26)arecorrespondinglyequaltothosefirst(n−l)Hankelsingularvaluesof
G(s).Hence,theabovereductionformulacanberepeatedlyappliedtogetfurther
reduced-ordersystemswithknownerrorbounds.
LettheHankelsingularvaluesofG(s)beσ >σ >···>σ withmultiplicities
|                 |     |     |        |     | 1 2                                | r   |     |
| --------------- | --- | --- | ------ | --- | ---------------------------------- | --- | --- |
| i=1,...,r,i.e.m |     | +m  | +···+m |     | =n.Byrepeatedlyapplyingtheformulas |     |     |
| m i ,           |     | 1   | 2      |     | r                                  |     |     |
(7.20)–(7.26),wemayhave
|     | G(s)=D |     | +σ  | E (s)+σ | E (s)+···+σ | E (s) | (7.29) |
| --- | ------ | --- | --- | ------- | ----------- | ----- | ------ |
|     |        |     | 0 1 | 1       | 2 2         | r r   |        |
i=1,...,r,arestable,norm-1,all-pass
| whereD 0 isaconstantmatrixandE |     |     |     | i (s), |     |     |     |
| ------------------------------ | --- | --- | --- | ------ | --- | --- | --- |
transfer function matrices. E (s)s are the differences at each approximation.Con-
i
sequently,wemaydefinereduced-ordermodels,fork=1,...,r−1,
(cid:14)k
|     |     |     | ˆ (s)=D |     | +           |     |        |
| --- | --- | --- | ------- | --- | ----------- | --- | ------ |
|     |     |     | G k     | 0   | σ i E i (s) |     | (7.30) |
i=1
| SuchaG ˆ (s)isstable,withtheorderm |     |                 |     |          | +···+m ,andsatisfies |     |        |
| ---------------------------------- | --- | --------------- | --- | -------- | -------------------- | --- | ------ |
| k                                  |     |                 |     | 1        | k                    |     |        |
|                                    |     | (cid:24)        |     | (cid:24) |                      |     |        |
|                                    |     | (cid:24) G(s)−G | ˆ   | (cid:24) | ≤(σ +···+σ           |     |        |
|                                    |     |                 |     | k (s)    | k+1                  | r ) | (7.31) |
∞
However,G ˆ (s)isnotanoptimalHankelapproximation,fork<r−1.Themethod
k
toobtainanoptimalHankelapproximationwith“general”orderisgivenbelow.

| 7.1 Absolute-ErrorApproximationMethods |                                     |     |     |     |           | 79  |
| -------------------------------------- | ----------------------------------- | --- | --- | --- | --------- | --- |
|                                        |                                     |     |     |     | ≥σ ≥···≥σ |     |
| Approximation3                         | LettheHankelsingularvaluesofG(s)beσ |     |     |     | 1 2       | k > |
σ k+1 =···=σ k+l >σ k+l+1 ≥···≥σ .Applyappropriatestatesimilaritytransfor-
n
mationstomaketheGramiansofG(s)bearrangedas
|     | Σ=diag(σ | ,σ ,...,σ | ,σ ,...,σ | ,σ  | ,...,σ ) |     |
| --- | -------- | --------- | --------- | --- | -------- | --- |
|     |          | 1 2       | k k+l+1   | n   | k+1 k+l  |     |
Define the last l Hankel singular values to be σ. Following the formulas (7.20)–
ˆ ˆ
(7.26), define an (n−l)th-order G (s). This G (s) is not stable but has exactly k
ˆ
stable poles. The kth-order stable part G h,k (s) of G(s), obtained by using modal
decompositionssay,isankth-orderHankeloptimalapproximationofG(s)andsat-
isfies
|     |     | (cid:24) |     | (cid:24) |     |        |
| --- | --- | -------- | --- | -------- | --- | ------ |
|     |     | (cid:24) |     | (cid:24) |     |        |
|     |     | G(s)−G   | (s) | =σ       |     | (7.32) |
h,k H
Nonsquareplantscanbeaugmentedwithzerocolumns/rowsandthenbeapplied
bytheaboveprocedures.
Remarks
1. The three methods introduced in the last three subsections can be applied to
originalsystems(plants)aswellastocontrollers.However,mostreportedcases
areonplantreductions.Thismaybeduetorobustcontrollerdesignmethodsused
subsequentlythatleadstobetterclosed-loopperformanceevenwithareduced-
orderplant.Examplesofapplicationoncontroller-sizereductioncanbefoundin
[149].In[149]itisalsoobservedthattheBalancedTruncationmethodandthe
Hankel-normApproximationusuallyperformbetterathighfrequency,whilethe
singularperturbationapproximation(balancedresidualization)methodperforms
betterinthelow-andmedium-frequencyranges.
2. Glover shows in [55] that any stable, rth-order approximation G r of G(s) can
neverachieve(cid:5)G(s)−G (s)(cid:5) ∞ ≤σ r+1 .Thislowererrorboundmayserveasa
r
yardsticktocomparewiththeactualerrorobtainedinpractice.
3. All the three methodsare applicablefor stable systems only.If a system is un-
stable,modaldecompositioncanbeappliedfirst.Thatis,findastableG (s)and
s
an antistable G us (s) (with all the poles in the closed right-half complex plane)
suchthat
|     |     | G(s)=G | (s)+G |     |     |        |
| --- | --- | ------ | ----- | --- | --- | ------ |
|     |     |        |       | (s) |     | (7.33) |
s us
Then,G s (s)canbereducedtoG sr (s),byusinganyofthethreemethods,anda
reduced-ordersystemoftheoriginalG(s)canbeformedas
|     |     | (s)=G | (s)+G |        |     |        |
| --- | --- | ----- | ----- | ------ | --- | ------ |
|     |     | G r   | sr    | us (s) |     | (7.34) |
Theroutinestocalculateamodaldecompositioncanbefoundinsoftwarepack-
agessuchasMATLAB®orSlicot.

80 7 Lower-OrderControllers
4. The formulas introduced here are for continuous-time systems. In the case of
discrete-time systems, the Gramians are calculated from the discrete Lyapunov
equationsinstead,
APAT −P +BBT =0 (7.35)
ATQA−Q+CTC=0 (7.36)
The balanced truncation method can then be applied similar to the case of
continuous time. However, it should be noted that the reduced-order system is
nolongerinabalancedrealizationform[43,138],thoughthesameerrorbound
stillholds[7].
For using the singular perturbation approximation (balanced residualiza-
tion) on a system with zero D-matrix, the reduced-order system G (s) =
r
[A ,B ,C ,D ]canbeinsteaddefinedby
r r r r
A =A +A (I −A ) −1A
r 11 12 22 21
B =B +A (I −A ) −1B
r 1 12 22 2
(7.37)
C =C +C (I −A ) −1A
r 1 2 22 21
D =C (I −A ) −1B
r 2 22 2
Suchareduced-ordersystemisstillinabalancedrealizationandenjoysthesame
errorbound[7,44,103,123].
The discrete-time case of Hankel-norm approximation has been studied for
a long time and is also called the Hankel-matrixapproximation.Detailscan be
foundin[6,89,90,129,194].
5. Research has been conducted on numerical implementations of the above re-
ductionmethods.Forinstance,inbalancedtransformationinordertoavoidnu-
mericalinstabilityofformingproductsBBT andCTC,algorithmsfordirection
calculation of the Choleski factors and improved balanced truncation scheme
havebeenproposed[70,93,162].Also,toavoidill-conditionedcomputational
problems, balancing-free approaches can be considered [146, 147, 168]. It is
recommended that the model-reduction subroutines developed in the software
packageSlicotbeusedbecauseoftheirsuperiornumericalproperties.
7.2 ReductionviaFractionalFactors
The modal decomposition can be used to reduce the order of a general, unstable
systemasdiscussedinthelastsection.However,theorderoftheantistablepartwill
notbereducedatall.Anotherreductionmethodapplicableinthecaseofunstable
systemsisviareductionofnormalizedcoprimefactorsofthesystemintroducedin
Chap.5.

7.2 ReductionviaFractionalFactors 81
(cid:4) (cid:5)
ForaminimalrealizationmodelG(s)= A B ,recallthatanormalizedleftco-
C 0
prime factorization is defined by G(s)=M ˜ (s) −1 N ˜ (s), where M ˜ (s) and N ˜ (s) are
stable and satisfy (5.2) and (5.3). Note that we assume G(s) has a zero D-matrix
and model reduction is conducted with regard to such a strictly proper system. In
the case of a nonzero feedthrough term in G(s), the nonzero D-matrix should be
addedtothereduced-ordermodel.Suchatreatmentgreatlysimplifiesformulas.It
willkeepthehigh-frequencygainoftheoriginalsysteminthefractionalbalanced
truncation(FBT)method,ormaintainthedc-gaininthefractionalsingularpertur-
bationapproximation(FSPA)method,bothintroducedbelow.
˜ ˜
ThefactorsM(s)andN(s)havethefollowingstate-spacemodels:
(cid:2) (cid:3)
(cid:4) N ˜ M ˜ (cid:5) = A+HC B H (7.38)
C 0 I
whereH =−ZCT withZ>0solvesthefollowingalgebraicRiccatiequation:
AZ+ZAT −ZCTCZ+BBT =0 (7.39)
[N ˜ M ˜ ] in (7.38) is stableand a balancedrealizationtransformationcan befound.
FollowingthebalancedrealizationalgorithminSect.7.1.1,astatesimilaritytrans-
formation [T,T −1] can be obtained such that [T(A+HC)T −1,T[B H],CT −1]
isabalancedrealizationwiththeGramianΣ =diag(σ ,σ ,...,σ ).Toreducethe
1 2 n
systemtorthorder,whereσ r >σ r+1 ,let
(cid:2) (cid:3) (cid:2) (cid:3)
T(A+HC)T −1=: A A ˜ ˜ 1 2 1 1 A A ˜ ˜ 1 2 2 2 = A A 1 2 1 1 + + H H 1 2 C C 1 1 A A 1 2 2 2 + + H H 1 2 C C 2 2 (7.40)
(cid:2) (cid:3) (cid:2) (cid:3)
(cid:4) (cid:5) ˜
B B H
T B H =: ˜ 1 = 1 1 (7.41)
B 2 B 2 H 2
(cid:4) (cid:5) (cid:4) (cid:5)
CT −1=: C ˜ C ˜ = C C (7.42)
1 2 1 2
(cid:4) (cid:5)
D ˜ := 0 I (7.43)
where
(cid:2) (cid:3)
TAT −1=: A 11 A 12 (7.44)
A A
21 22
(cid:2) (cid:3)
B
TB =: 1 (7.45)
B
2
(cid:4) (cid:5)
CT
−1=:
C C (7.46)
1 2
(cid:2) (cid:3)
H
TH =: 1 (7.47)
H
2

| 82  |     |     |     |     |     | 7   | Lower-OrderControllers |     |
| --- | --- | --- | --- | --- | --- | --- | ---------------------- | --- |
Accordingly,theGramianisdividedas
|     |     |     |     | (cid:2) | (cid:3) |     |     |        |
| --- | --- | --- | --- | ------- | ------- | --- | --- | ------ |
|     |     |     |     | Σ       | 0       |     |     |        |
|     |     |     | Σ=  | 1       |         |     |     | (7.48) |
|     |     |     |     | 0       | Σ       |     |     |        |
2
|         | =diag(σ  |         |     | =diag(σ |            |      |     |     |
| ------- | -------- | ------- | --- | ------- | ---------- | ---- | --- | --- |
| withΣ 1 | 1 ,...,σ | r )andΣ | 2   |         | r+1 ,...,σ | n ). |     |     |
Now, the reduction methods introduced in Sect. 7.1 can be applied to obtain
|     | [ ˜ ˜ | ],  |     |     |     |     |     | (s)= |
| --- | ----- | --- | --- | --- | --- | --- | --- | ---- |
an rth-order N r M r which leads to a reduced order (rth-order) model G r
−1
| M ˜ (s) | N ˜ (s).                     |     |     |     |             |     |     |     |
| ------- | ---------------------------- | --- | --- | --- | ----------- | --- | --- | --- |
| r       | r                            |     |     |     |             |     |     |     |
| 7.2.1   | FractionalBalancedTruncation |     |     |     | (FBT)Method |     |     |     |
Inthisdirecttruncationmethod,wedefine
|     |         | (cid:2) |             | (cid:3)   | (cid:2) |         | (cid:3) |        |
| --- | ------- | ------- | ----------- | --------- | ------- | ------- | ------- | ------ |
|     | (cid:4) | (cid:5) | A ˜         | B ˜       | A + H   | C B     | H       |        |
|     | ˜ ˜     | :=      | 1 1 (cid:4) | 1 (cid:5) | = 11    | 1 1     | 1 1     |        |
|     | N r M   | r       | ˜           |           |         |         |         | (7.49) |
|     |         |         | C 0         | I         | C       | 0       | I       |        |
|     |         |         | 1           |           | 1       |         |         |        |
|     |         |         |             |           | (cid:4) | (cid:5) |         |        |
It is easy to checkthat the aboverealizationof N ˜ M ˜ is still a balancedreal-
|                        |     |     |         |     |     | r r |     |     |
| ---------------------- | --- | --- | ------- | --- | --- | --- | --- | --- |
| izationwiththeGramianΣ |     |     | .Define |     |     |     |     |     |
1
|     |     |     |          | ˜   | −1 ˜  |     |     |        |
| --- | --- | --- | -------- | --- | ----- | --- | --- | ------ |
|     |     |     | G (s):=M | (s) | N (s) |     |     | (7.50) |
|     |     |     | r        | r   | r     |     |     |        |
Bydirectmanipulations,wehave
|     |     |     |        | (cid:2) | (cid:3) |     |     |        |
| --- | --- | --- | ------ | ------- | ------- | --- | --- | ------ |
|     |     |     |        | A       | B       |     |     |        |
|     |     |     | G (s)= |         | 11 1    |     |     | (7.51) |
|     |     |     | r      | C       | 0       |     |     |        |
1
An error bound directly follows from the result in Sect. 7.1.1 and as shown in
[119]itis
|     |     | (cid:24)(cid:4) |      |     | (cid:5)(cid:24) (cid:14)n |     |     |        |
| --- | --- | --------------- | ---- | --- | ------------------------- | --- | --- | ------ |
|     |     | (cid:24) ˜      | ˜ ˜  | ˜   | (cid:24)                  |     |     |        |
|     |     | N               | −N M | −M  | ≤2                        | σ   |     | (7.52) |
|     |     |                 | r    | r   | ∞                         | i   |     |        |
i=r+1
| 7.2.2 | FractionalSingularPerturbationApproximation |     |     |     |     |     | (FSPA) |     |
| ----- | ------------------------------------------- | --- | --- | --- | --- | --- | ------ | --- |
Method
Naturally,thesingularperturbationapproximationmethod(or,thebalancedresidu-
| alizationmethod)inSect.7.1.2canbeusedtoreducetheorderof[ |     |     |     |     |     |     | ].      |     |
| -------------------------------------------------------- | --- | --- | --- | --- | --- | --- | ------- | --- |
|                                                          |     |     |     |     |     |     | N ˜ M ˜ |     |
Define
|     |     |     | =A  | ˜ −A | ˜ ˜−1A ˜ |     |     |        |
| --- | --- | --- | --- | ---- | -------- | --- | --- | ------ |
|     |     |     | A r | 11   | 12 A 21  |     |     | (7.53) |
22

7.2 ReductionviaFractionalFactors 83
B =B ˜ −A ˜ A ˜−1B ˜ (7.54)
r 1 12 22 2
C =C ˜ −C ˜ A ˜−1A ˜ (7.55)
r 1 2 22 21
D =D ˜ −C ˜ A ˜−1B ˜ (7.56)
r 2 22 2
Furthermore,B andD canbecompatiblypartitionedas
r r
(cid:4) (cid:5) (cid:4) (cid:5)
B r = B r,1 B r,2 := B 1 −A ˜ 12 A ˜− 22 1B 2 H 1 −A ˜ 12 A ˜− 22 1H 2 (7.57)
(cid:4) (cid:5) (cid:4) (cid:5)
D r = D r,1 D r,2 := −C 2 A ˜− 22 1B 2 I −C 2 A ˜− 22 1H 2 (7.58)
Hence,let
(cid:2) (cid:3)
(cid:4) (cid:5)
N ˜ M ˜ := A r B r,1 B r,2 (7.59)
r r C D D
r r,1 r,2
which is of balanced realization form with the Gramian Σ . An rth-order model
1
G (s)isthenobtainedby
r
(cid:30) (cid:31)
G (s)=M ˜ (s) −1 N ˜ (s)= A r −B r,2 D r − ,2 1C r B r,1 −B r,2 D r − ,2 1D r,1 (7.60)
r r r
D
−1C
D
−1D
r,2 r r,2 r,1
In the case that the original model G(s) is not strictly proper, the nonzero
feedthroughtermshouldbeaddedintheD-matrixin(7.60).
Theerrorbound(7.52)obviouslyholdshereaswell,fromtheresultinSect.7.1.2.
Remarks
1. Meyer [119] shows that (cid:5)[N ˜ M ˜ ](cid:5) <1, i.e. Σ <I. Also, the infinitive norm
H
(cid:5)[N ˜ M ˜ ](cid:5) ∞ =1,becauseofthenormalizedcoprimefactorization.
2. Theresultcanbeobtainedthat,ineithertheFBTmethodorFSPAmethod,we
have
(cid:24) (cid:24) (cid:24) (cid:24) (cid:24)(cid:4) (cid:5)(cid:24) (cid:24) (cid:24)
(cid:24) G(s)−G (s) (cid:24) ≤(cid:24) M ˜−1(cid:24) (cid:24) N ˜ −N ˜ M ˜ −M ˜ (cid:24) (cid:24) M ˜−1(cid:24) (7.61)
r ∞ r ∞ r r ∞ ∞
bywriting
G−G =M ˜−1N ˜ −M ˜−1N ˜
r r r
(cid:19) (cid:2) (cid:3)(cid:20)
(cid:4) (cid:5)
=M ˜ r −1 N ˜ −N ˜ r M ˜ −M ˜ r −M ˜ I −1N ˜
(cid:19) (cid:2) (cid:3)(cid:20)
(cid:4) (cid:5) ˜
=M ˜ r −1 N ˜ −N ˜ r M ˜ −M ˜ r M ˜−1 − M N ˜ (7.62)
(cid:24)(cid:4) (cid:5)(cid:24)
andbythefactthat (cid:24) M ˜ (cid:24) =1.
−N ˜ ∞

| 84  |     |     | 7 Lower-OrderControllers |     |
| --- | --- | --- | ------------------------ | --- |
3. Notethatthemethodsintroducedabovearebasedontheleftcoprimefactoriza-
tion.Similarly,modelreductionscanbedonewithregardtothenormalizedright
coprimefactorization.
4. Themodelreductioninthediscrete-timecaseusingthefractionalbalancedtrun-
cation method is straightforward, and using the fractional singular perturbation
approximationmethodcanbefoundin[123,127].
| 7.3 Relative-ErrorApproximation |     | Methods |     |     |
| ------------------------------- | --- | ------- | --- | --- |
Asdiscussedin Sect.7.1.3,thebalancedtruncationmethodgivesagoodapproxi-
mationover high-frequencyranges, whilethe singular perturbation approximation
performsbetteroverlow-andmedium-frequencyranges.Ifareduced-ordersystem
isrequiredinsomepracticalproblemstoapproximateequallywelloverthewhole
frequencyrange,thenthemethodcalledthebalancedstochastictruncation(BST)
methodmaybe considered[26, 60,61, 102, 169]). The effect of this methodmay
beviewed,forastable,squareandinvertibleG(s),asaminimizationof
|     | (cid:24) (cid:6) |     | (cid:7)(cid:24) |        |
| --- | ---------------- | --- | --------------- | ------ |
|     | (cid:24) −1(s)   |     | (cid:24)        |        |
|     | G G(s)−G         | (s) |                 | (7.63) |
|     |                  | r   | ∞               |        |
Hence, the reduced-order system G (s) approximates the original system in the
r
−1G
senseofmaking G r nearertoidentity.Problem(7.63)representsaminimiza-
tion of a relative error and is one of several relative-error approximation methods
(e.g.,see[56,58]).
The idea of the BST method is the following. First, a spectral factor W(s) of
G(s)G − (s)istobefound.Thatis,
|                | − (s)W(s)=G(s)G |            | −                   |            |
| -------------- | --------------- | ---------- | ------------------- | ---------- |
|                | W               |            | (s)                 |            |
| − (s):=WT(−s), |                 | −          |                     |            |
| where W        | similarly       | for G (s); | and W(s) is stable, | square and |
of minimum phase (i.e. (W(s)) −1 ∈ H ∞). W(s) contains the “magnitude” part
=
of G(s). Correspondingly, a “phase” matrix of G(s) can be defined as F(s)
− −1G(s).F(s)isanall-passtransferfunctionmatrixandcontainsbothsta-
(W (s))
bleandunstablemodes.TheBSTmethodisthentoapplyabalancedtruncationon
the stable part of F(s) (which is of the same order as G(s)), with the same state
similaritytransformationandpartitiononthestatespacemodelofG(s)toobtaina
reduced-orderG (s).
| r   |     |     | (cid:4) (cid:5) |     |
| --- | --- | --- | --------------- | --- |
Foragivennth-order,stableandsquareG(s)= A B weassumethisisamin-
C D
−1.
imalrealizationandtheinvertibilityofG(s)impliestheexistenceofD
ThecomputationalstepsoftheBSTmethodcanbedescribedas
Step1: SolvetheLyapunovequation
|                   | AP +PAT | +BBT | =0  | (7.64) |
| ----------------- | ------- | ---- | --- | ------ |
| wherethesolutionP | >0.     |      |     |        |

7.3 Relative-ErrorApproximationMethods 85
Step2: Let
B =PCT +BDT (7.65)
W
(cid:6) (cid:7)
C =D −1 C−BT Q (7.66)
W W W
whereQ isthestabilizingsolutiontothefollowingRiccatiequation:
W
ATQ +Q A+CT C =0 (7.67)
W W W W
Remark:(A,B ,C )formsthestablepartofF(s).
W W
Step3: Decidea balancedrealizationtransformationwithregardto (P,Q ) and
W
applythe transformation onto G(s). Let the balancedGramianmatrix be Σ =
diag(σ ,...,σ )indescendingorder.
1 n
Remarks: (1) After applyingthe abovetransformation, G(s) is, in general,not
inthebalancedrealizationform,butwithitscontrollabilityGramianbeing Σ;
(2)Σ≤I,duetoF(s)beinganall-passmatrix.
Step4: PartitionΣ as
(cid:2) (cid:3)
Σ 0
Σ= 1 (7.68)
0 Σ
2
whereΣ 1 =diag(σ 1 ,...,σ r ),Σ 2 =diag(σ r+1 ,...,σ n ),withσ r >σ r+1 .Parti-
tioncompatibl(cid:4)ythema(cid:5)tricesA(cid:4), B(cid:5),andC(of(cid:4)thetra(cid:5)nsformedstate-spacemodel
ofG(s))A= A
A
1
2
1
1
A
A
1
2
2
2
,B= B
B
1
2
,andC= C1C2 .Then,areduced-ordersys-
temG (s)canbedefinedby
r
G (s)=C (sI −A ) −1B +D (7.69)
r 1 11 1
Forthisreduced-ordersystem,arelativeerrorboundcanbederived[61]as
(cid:24)
(cid:24) G −1(G−G )
(cid:24)
(cid:24) ≤
#n 1+σ
i −1 (7.70)
r ∞ 1−σ
i=r+1 i
The errors between the phase matrices, with the same antistable and constant
parts,areboundedby
(cid:24) (cid:24)
(cid:24) F(s)−F r (s) (cid:24) ∞ ≤4(σ r+1 +···+σ n ) (7.71)
(cid:24) (cid:24)
(cid:24) F(s)−F r (s) (cid:24) H ≤2(σ r+1 +···+σ n ) (7.72)
Remarks
1. TheBSTmethodcanbeappliedtononsquareG(s)aswell,withslightmodifi-
cations.TheinvertibilityofG(s) ischangedtotheassumptionthatD isoffull
rowrank.TheconstantmatrixofthesquarespectralfactorW(s)wouldbeD ,
W
withDT D =DDT,andtheoutputmatrixC =D (DDT) −1(C−BT Q ).
W W W W W W

| 86  |     |     |     | 7 Lower-OrderControllers |     |
| --- | --- | --- | --- | ------------------------ | --- |
Fig.7.2 Closed-loopsystem
withreduced-order
controllers
However,inthenonsquarecase,therewouldbenoexplicitexplanationoftherel-
ativeerrorformat(7.63).Thereductionjustshowsanapproximationwithrespect
tophase.
2. Intheabovemethod,insteadofbalancedtruncation,theHankel-normapproxi-
mationcanbeused[56].Thatis,thebalancedrealizationofthestablepart,F (s),
s
ofthephasematrixF(s)istobeapproximatedbyaHankel-normapproximant,
F (s),calculatedusingtheformulainSect.7.1.3.Thereducedmodel,G ,can
| s,r |     |     |     |     | r   |
| --- | --- | --- | --- | --- | --- |
thenbedefinedas
|     |     | G =G−W | − (F | −F ) | (7.73) |
| --- | --- | ------ | ---- | ---- | ------ |
|     |     | r      | s    | s,r  |        |
Itcanbeshown[56,61]thatG isstableandsatisfiesthefollowingerrorbound:
r
|     | (cid:24)        |     | (cid:24) #n |          |        |
| --- | --------------- | --- | ----------- | -------- | ------ |
|     | (cid:24) −1(G−G |     | (cid:24)    |          |        |
|     | G               | )   | ≤           | (1+σ )−1 | (7.74) |
|     |                 | r   | ∞           | i        |        |
i=r+1
| 7.4 Frequency-Weighted |     | Approximation |     | Methods |     |
| ---------------------- | --- | ------------- | --- | ------- | --- |
The model-order reduction approaches introduced above can be in theory applied
toplants(theoriginalsystemmodels)aswellastocontrollers.However,toreduce
theorderofadesignedcontroller,itisnecessarytotakeintoaccounttheplantthat
is being compensated and other design specifications of the closed-loop system.
With such considerations, the controller-order reduction problem would be better
formulatedasafrequency-weightedmodelreduction,andsuitableapproacheshave
beensuggested.
AssumethatacontrollerK(s)hasbeendesignedforaplantwithamodelG(s),
and denote a reduced-order controller by K (s). The configuration with K(s) re-
r
placedbyK (s)intheclosed-loopsystemcanbedepictedbyFig.7.2.
r
FromtheSmall-GainTheorem(Theorem3.1),itiseasytoobtaintheresultthat
the closed-loop system with the reduced-order controller K (s) remains stable if
r
K(s)andK r (s)havethesamenumberofunstablepolesandif
| (cid:24)(cid:4) |     |            |           | (cid:24)           |        |
| --------------- | --- | ---------- | --------- | ------------------ | ------ |
|                 |     | (cid:5)    | (cid:4)   | (cid:5) −1(cid:24) |        |
| (cid:24) K(s)−K |     |            | +K(s)G(s) |                    |        |
|                 |     | r (s) G(s) | I         | ∞ <1               | (7.75) |

| 7.4 | Frequency-WeightedApproximationMethods |     |     |     |     |     |     |     | 87  |
| --- | -------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
or
|     |     | (cid:24)(cid:4) |     | (cid:5) | (cid:4) |     | (cid:5)(cid:24) |     |        |
| --- | --- | --------------- | --- | ------- | ------- | --- | --------------- | --- | ------ |
|     |     | (cid:24)        |     | −1      |         |     | (cid:24)        |     |        |
|     |     | I +G(s)K(s)     |     | G(s)    | K(s)−K  |     | (s) <1          |     | (7.76) |
|     |     |                 |     |         |         |     | r ∞             |     |        |
Let W (s):=G(s)[I +K(s)G(s)]−1 and W (s):=[I +G(s)K(s)]−1G(s). Then
|     | i   |     |     |     |     | o   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
inordertoreservethestabilityoftheclosed-loopsystem,areduced-ordercontroller
K (s)issoughttominimizethefrequency-weightedcostfunctions
r
|     |     |     |     | (cid:24)(cid:4) | (cid:5) | (cid:24) |     |     |        |
| --- | --- | --- | --- | --------------- | ------- | -------- | --- | --- | ------ |
|     |     |     |     | (cid:24) K(s)−K |         | (cid:24) |     |     |        |
|     |     |     |     |                 | (s)     | W (s)    |     |     | (7.77) |
|     |     |     |     |                 | r       | i        | ∞   |     |        |
or
|     |     |     |     | (cid:24) (cid:4) |     | (cid:5)(cid:24) |     |     |        |
| --- | --- | --- | --- | ---------------- | --- | --------------- | --- | --- | ------ |
|     |     |     |     | (cid:24)         |     | (cid:24)        |     |     |        |
|     |     |     |     | W (s) K(s)−K     |     | (s)             |     |     | (7.78) |
|     |     |     |     | o                |     | r               | ∞   |     |        |
Noteinthiscasetheinputfrequencyweightfunction W (s) equalstheoutputfre-
i
| quencyweightfunctionW |     |     |     | (s). |     |     |     |     |     |
| --------------------- | --- | --- | --- | ---- | --- | --- | --- | --- | --- |
o
Anotherconsiderationisabouttheperformanceoftheclosed-loopsystem.The
performance is closely related to the transfer function of the closed-loop system.
Naturally, to maintain the performance of the designed, closed-loop system, it re-
quiresthetransferfunctionoftheclosed-loopsystemwithreduced-ordercontroller
tobeasnearaspossibletothatwiththeoriginalcontroller.Thetwotransferfunc-
tionsare,respectively,
|     |          | (cid:4)     |     | (cid:5) |           |     | (cid:4)      | (cid:5) |     |
| --- | -------- | ----------- | --- | ------- | --------- | --- | ------------ | ------- | --- |
|     |          |             |     | −1      |           |     |              |         | −1  |
|     | G(s)K(s) | I +G(s)K(s) |     |         | and G(s)K |     | (s) I +G(s)K | (s)     |     |
|     |          |             |     |         |           | r   |              | r       |     |
Thedifferencebetweenthesetwotransferfunctions,byneglectingtermsofsecond
| andhigherordersinK−K |     |     |     | ,is |     |     |     |     |     |
| -------------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
r
|     |     | (cid:4)          |     | (cid:5) (cid:4) |     | (cid:5)(cid:4) |             | (cid:5) |     |
| --- | --- | ---------------- | --- | --------------- | --- | -------------- | ----------- | ------- | --- |
|     |     |                  |     | −1              |     |                |             | −1      |     |
|     |     | G(s) I +K(s)G(s) |     | K(s)−K          |     | (s)            | I +G(s)K(s) |         |     |
r
| Hence,areduced-ordercontrollerK |     |     |     | (s)shouldtrytominimize |     |     |     |     |     |
| ------------------------------- | --- | --- | --- | ---------------------- | --- | --- | --- | --- | --- |
r
|        |         |              | (cid:24) |         |             |         | (cid:24)      |     |        |
| ------ | ------- | ------------ | -------- | ------- | ----------- | ------- | ------------- | --- | ------ |
|        |         |              |          | (cid:4) |             | (cid:5) |               |     |        |
|        |         |              | (cid:24) | K(s)−K  |             |         | (cid:24)      |     |        |
|        |         |              | W        | o (s)   | r (s)       | W i (s) | ∞             |     | (7.79) |
|        | (s):=[I | +G(s)K(s)]−1 |          |         | (s):=G(s)[I |         | +K(s)G(s)]−1. |     |        |
| whereW | i       |              |          | andW    | o           |         |               |     |        |
Let us now concentrate on the general form of frequency-weighted model re-
duction of (7.79), but replacing K(s) and K (s) by G(s) and G (s), respectively.
|     |     |     |     |     |     | r   |     | r   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
AssumethatG(s)isstableandhastheminimalrealizationasdefinedin(7.2).The
inputweightfunctionW (s)andtheoutputweightW (s)arealsostablewithmini-
|                   |     |      | i (cid:4) | (cid:5)    |      | (cid:4) | o (cid:5)         |     |     |
| ----------------- | --- | ---- | --------- | ---------- | ---- | ------- | ----------------- | --- | --- |
| malrealizations:W |     | (s)= |           | Ai Bi andW | (s)= | Ao      | Bo ,respectively. |     |     |
|                   |     | i    |           |            | o    |         |                   |     |     |
|                   |     |      |           | Ci Di      |      | Co      | Do                |     |     |
Remark Obviously the stability assumption of G(s) would be a restriction in the
caseofcontroller-orderreduction.InthecaseofunstableG(s),themodaldecom-
positiondiscussedinSect.7.1.3canbeconsidered.

| 88  |     |     |     |     |     |     | 7 Lower-OrderControllers |     |
| --- | --- | --- | --- | --- | --- | --- | ------------------------ | --- |
TheaugmentedsystemsG(s)W i (s)andW o (s)G(s)havethestate-spacemodels
|     |     |       |      |          | ⎡        |       | ⎤   |        |
| --- | --- | ----- | ---- | -------- | -------- | ----- | --- | ------ |
|     |     |       |      | (cid:30) | (cid:31) |       |     |        |
|     |     |       |      | ˆ        | ˆ        | A BC  | BD  |        |
|     |     |       |      | A B      |          | i     | i   |        |
|     |     |       | (s)= | i        | i =⎣     |       | ⎦   |        |
|     |     | G(s)W | i    | ˆ        | ˆ        | 0 A i | B i | (7.80) |
C D
|     |     |         |          | i     | i          | C DC | DD     |        |
| --- | --- | ------- | -------- | ----- | ---------- | ---- | ------ | ------ |
|     |     |         |          |       |            | i    | i      |        |
|     |     |         | (cid:30) |       | (cid:31) ⎡ |      | ⎤      |        |
|     |     |         |          | ˆ ˆ   |            | A 0  |        |        |
|     |     |         | A        | o B o | =⎣         |      | B B D⎦ |        |
|     |     | W G(s)= |          |       | B          | C A  | o      | (7.81) |
|     |     | o       |          | ˆ ˆ   |            | o o  |        |        |
|     |     |         | C        | o D o | D          | C C  |        |        |
|     |     |         |          |       |            | o o  | D o D  |        |
|     | ˆ   | ˆ       |          |       |            |      |        |        |
Let P and Q be two non-negative matrices satisfying the following two Lya-
punovequations,respectively:
|                        |     |     | ˆ      | ˆ +P ˆ | ˆT +B ˆ   | ˆT =0   |     |        |
| ---------------------- | --- | --- | ------ | ------ | --------- | ------- | --- | ------ |
|                        |     |     | A      | P      | A         | B       |     | (7.82) |
|                        |     |     | ˆTQ    | ˆ      | ˆ ˆ+C ˆTC | ˆ       |     |        |
|                        |     |     | A      | +Q     | A         | =0      |     | (7.83) |
|                        |     |     | ˆ      | ˆ      |           |         |     |        |
| Furthermore,partitionP |     |     | andQas |        |           |         |     |        |
|                        |     |     |        |        | (cid:2)   | (cid:3) |     |        |
|                        |     |     |        | ˆ =    | P P       | 12      |     |        |
|                        |     |     |        | P      |           |         |     | (7.84) |
PT P
|     |     |     |     |     | 12      | 22      |     |        |
| --- | --- | --- | --- | --- | ------- | ------- | --- | ------ |
|     |     |     |     |     | (cid:2) | (cid:3) |     |        |
|     |     |     |     | ˆ   | Q       | Q 12    |     |        |
|     |     |     |     | Q = |         |         |     | (7.85) |
QT Q
|     |     |     |     |     | 12  | 22  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
whereP andQareofn-dimension,andarecalledtheinputweightedGramianand
outputweightedGramian,respectively.
Severalfrequency-weightedmodel-reductionalgorithmsusebalancedrealization
transformationsonP andQorarerelatedwithtruncations.Threesuchmethodsare
introducedbelow.
| 7.4.1 Frequency-Weighted |     |     |     | BalancedTruncation |     |     | (FWBT) |     |
| ------------------------ | --- | --- | --- | ------------------ | --- | --- | ------ | --- |
Enns [38, 39] proposes to find a balanced realization on P and Q, i.e. to find an
| invertiblen×nmatrixT |     |     | (seeSect.7.1.1)suchthat |     |     |     |     |     |
| -------------------- | --- | --- | ----------------------- | --- | --- | --- | --- | --- |
(cid:6) (cid:7)
|               |           |                                     | −1 T   | −1=diag(σ |                                    |           |              |        |
| ------------- | --------- | ----------------------------------- | ------ | --------- | ---------------------------------- | --------- | ------------ | ------ |
|               | TPTT      | =                                   | T      | QT        |                                    | ,...,σ ,σ | r+1 ,...,σ ) |        |
|               |           |                                     |        |           |                                    | 1 r       | n            |        |
|               | ≥σ ≥···≥σ |                                     |        | ≥···≥σ    | ≥0.Applysuchastatesimilaritytrans- |           |              |        |
| withσ 1       | 2         | r                                   | >σ r+1 |           | n                                  |           |              |        |
| formation(T,T |           | −1)onG(s)andpartitionitaccordingly, |        |           |                                    |           |              |        |
|               |           |                                     |        |           | ⎡                                  |           | ⎤            |        |
|               |           | (cid:2)                             |        | (cid:3)   |                                    |           |              |        |
|               |           |                                     | −      |           | A 1 1                              | A 1 2     |              |        |
|               |           | T A                                 | T 1    | T B =⎣    |                                    | B         | B 2⎦         |        |
|               |           |                                     |        |           | A                                  | A 1       |              | (7.86) |
|               |           | C                                   | T − 1  | D         | 2 1                                | 2 2       |              |        |
|               |           |                                     |        |           | C 1                                | C 2 D     |              |        |

| 7.4 Frequency-WeightedApproximationMethods |     |     |     | 89  |
| ------------------------------------------ | --- | --- | --- | --- |
isofr×r
| whereA 11 | dimension.Areduced-orderG | r   | (s)canthenbedefinedby |     |
| --------- | ------------------------- | --- | --------------------- | --- |
(cid:2) (cid:3)
(s)= A 11 B 1
|     | G   |     |     | (7.87) |
| --- | --- | --- | --- | ------ |
r C D
1
G (s)obtainedin(7.87)isnotnecessarilystable,exceptinthecaseswhereeither
r
| =I =I |     |     |     |     |
| ----- | --- | --- | --- | --- |
W i orW o (one-sideweightonly).Thereisanerrorboundderived[84]for
|     | (cid:24) (cid:4) | (cid:5)       | (cid:24) |     |
| --- | ---------------- | ------------- | -------- | --- |
|     | (cid:24) G(s)−G  |               | (cid:24) |     |
|     | W o (s)          | r (s) W i (s) |          |     |
∞
However, this bound has to be computed iteratively, depending on reduced-order
modelsofn−1,...,r+1,andisnotpracticallyuseful.
7.4.2 Frequency-Weighted SingularPerturbationApproximation
(FWSPA)
Lin and Chiu [100] introduce another truncation method to obtain a frequency-
weighted reduced model. Assume that P and Q in (7.84) and (7.85), respec-
22 22
tively, are nonsingular. This condition is guaranteed, for example, in the case that
therealizations(7.80)and(7.81)areminimal,i.e.iftherearenopole/zerocancel-
lationsbetweenG(s)andW (s),norbetweenW (s)andG(s).Insteadofapplying
|     | i   | o   |     |     |
| --- | --- | --- | --- | --- |
a balanced realization transformation on P and Q as in the Enns method, a bal-
|                                                        |     |     | −P  | −1PT  |
| ------------------------------------------------------ | --- | --- | --- | ----- |
| ancedrealizationtransformationistobefoundwithregardtoP |     |     |     | P and |
12 22 12
Q−QT −1Q
Q 1 2.Thisbalancedrealizationisthenappliedontotheoriginalmodel
12 22
G(s)andtruncationtakeninthesamewayasin(7.86)and(7.87).
Apparently,thismethodissonamedbecausethematricesP −P P −1PT and
12 22 12
−1Q
Q−QT Q 2 are in the form of the reduced-order state matrix used in the
| 12 22 1 |     |     |     |     |
| ------- | --- | --- | --- | --- |
Singular Perturbation (cid:4) Approximation (cid:5) (cid:4) method (Sect. (cid:5) 7.1.2). It is observed that, by
−
pre/postmultiplying I −P1 2P 1 and I 0 on(7.82),andsimilarmultiplica-
|                                      | 2 2 −P | − 1P T I |              |       |
| ------------------------------------ | ------ | -------- | ------------ | ----- |
|                                      | 0 I    | 2 2 1 2  |              |       |
|                                      |        | −P       | −1PT andQ−QT | −1Q   |
| tionswithregardtoQon(7.83),matricesP |        | 12 P     |              | Q 1 2 |
|                                      |        |          | 22 12        | 12 22 |
satisfy two Lyapunov equations, respectively. Hence, the diagonalized matrices of
thesetwoafterthebalancedrealizationtransformationssatisfytheLyapunovequa-
tions,too.Thisindicatesthereduced-ordersystemisguaranteedtobestable.
Thereisanerrorboundavailableforthismethod[157].However,itsuffersthe
sameweaknessastheerrorboundfortheEnnsmethod.Theerrorboundcannotbe
simplycalculatedfromtheoriginalmodeldata.
| 7.4.3 Frequency-Weighted | ModuliTruncation |     | Method(FWMT) |     |
| ------------------------ | ---------------- | --- | ------------ | --- |
The error bounds for the above two methods are not practically useful. In [175],
Wang et al. propose another truncation method with a priori computable error
bound.

90 7 Lower-OrderControllers
Quotingtheupper-leftblocksof(7.82)and(7.83)givesthefollowingtwomatrix
equations:
AP +PAT +BC P +PTCTBT +BD DTBT =0 (7.88)
i 12 12 i i i
ATQ+QA+Q B C+CTBTQT +CTDTD C=0 (7.89)
12 o o 12 o o
Let
X=BC P +PTCTBT +BD DTBT (7.90)
i 12 12 i i i
Y =Q B C+CTBTQT +CTDTD C (7.91)
12 o o 12 o o
NotethatX andY definedabovearesymmetricbutnotsign-definiteingeneral.
ApplycongruenttransformationsonX andY toobtainorthogonalmatricesU and
V suchthat
X=UΘUT (7.92)
Y =VΓVT (7.93)
where Θ =diag(θ ,...,θ ,0,...,0), Γ =diag(γ ,...,γ ,0,...,0), with |θ |≥
1 i 1 o 1
···≥|θ |>0and|γ |≥···≥|γ |>0.Now,define
i 1 o
(cid:6) (cid:7)
B ˜ =Udiag |θ
1
|1 2,...,|θ
i
|1 2,0,...,0 (7.94)
(cid:6) (cid:7)
C ˜ =diag |γ
1
|1 2,...,|γ
o
|1 2,0,...,0 VT (7.95)
SolvethefollowingtwoLyapunovequations:
AP ˜ +P ˜ AT +B ˜ B ˜T =0 (7.96)
Q ˜ A+ATQ ˜ +C ˜TC ˜ =0 (7.97)
˜ ˜
Itcanbeshown[175]that(A,B,C)isaminimalrealizationandhencetheso-
˜ ˜
lutions P and Q to (7.96) and (7.97), respectively, are positive definite. Similar
˜
to FWBT and FWSPA methods, a balanced realization is found with regard to P
˜
andQandthetransformationisappliedtotheoriginalmodel(A,B,C)toyielda
reduced-order model G (s). Such a G (s) is stable, following the same reasoning
r r
as in the FWSPA method. Furthermore, the following error bound can be derived
[175].
Define
(cid:6) (cid:7)
K =diag |θ
1
|1 2,...,|θ
i
|1 2,0,...,0 UTB (7.98)
(cid:6) (cid:7)
L=CVdiag |γ
1
|1 2,...,|γ
o
|1 2,0,...,0 (7.99)
Then,itisshownin[175]that
(cid:24) (cid:6) (cid:7) (cid:24) (cid:14)n
(cid:24) W (s) G(s)−G (s) W (s) (cid:24) ≤k σ (7.100)
o r i ∞ j
j=r+1

7.4 Frequency-WeightedApproximationMethods 91
where
(cid:24) (cid:24) (cid:24) (cid:24)
k=2 (cid:24) W (s)L (cid:24) (cid:24) KW (s) (cid:24)
o ∞ i ∞
and (σ 1 ,·,σ r ,σ r+1 ,...,σ n ) are the diagonal elements of the balanced form of P ˜
˜
(Q).

Chapter 8
LMI Approach
In Chaps. 4, 5, and 6, we discussed how a robust controller design problem can
be cast as an optimization problem, in H ∞ or μ-synthesis formulations. Optimal
or sub-optimal solutions can be found by following some formulas which are de-
rivedusingfunctionalanalysisoroperatortheories.Thereisactuallyanotherwayto
considertherobustdesignproblem,andcontrolsystemdesigningeneral,asanop-
timizationproblem,solutionstowhichcanbedirectlycomputedbyconvexcompu-
tationalprocedures.ThatisthesocalledLinearMatrixInequality(LMI)approach.
Inthischapter,basicconceptsofLMIandafewapplicationsofLMIinrobustand
othercontrolsystemdesignproblemswillbeintroduced.
8.1 BasicsAbout LMI
Variables involvedin a linear matrix inequality problem are either scalars or sign-
definitematrices.Recallthata(real)symmetricmatrixM ispositive(negative)def-
initeifxTMx>(<)0,∀x(cid:3)=0.Also,M iscalledpositive(negative)semi-definite
ifxTMx≥(≤)0,∀x.ThemostgeneralformofanLMIis
(cid:14)l
F(x)=M + x M >0 (8.1)
0 i i
i=1
where x arereal,scalarvariables, x=[x ,...,x]T,and M and M areconstant
i 1 l 0 i
(given), symmetric matrices of dimension n×n. The above LMI is feasible, if a
vectorxexistswhichsatisfies(8.1).
Insomecontrolsystemproblems,itismoreconvenienttobeformulatedasthe
followingLMI:
(cid:14)k
F(X ,...,X )=M + G X H >0 (8.2)
1 k 0 i i i
i=1
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 93
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_8,©Springer-VerlagLondon2013

| 94    |             |            |           |             | 8               | LMIApproach    |
| ----- | ----------- | ---------- | --------- | ----------- | --------------- | -------------- |
|       | ∈(cid:18)pi | ×qi        |           |             | ∈(cid:18)n×pi,H | ∈(cid:18)qi ×n |
| where | X i         | are matrix | variables | to be found | and G i         | i              |
areknownmatrices.Itiseasytoseethatthevectorvariablexin(8.1)canbeformed
| bystackingthecolumnsofX |     |     | in(8.2). |     |     |     |
| ----------------------- | --- | --- | -------- | --- | --- | --- |
i
In general, an optimization problem can have an LMI as its cost function with
severalotherLMI’softhesamematrixvariablesasconstraints.
Introduction of LMI can be as a matter of fact traced back to the work of Lya-
punov.Ithasalsobeenknownforseveraldecadesthatsomecontrolproblemscan
be formulated as LMI problems (see [49, 184, 185], for example). The major im-
pact behind the wide use of LMIs in control systems analysis and design in the
last decade or so is due to the breakthrough of efficient numerical algorithms of
interior-pointmethodsinconvexoptimization[50,130].Suchadevelopmentmakes
itpracticallypossibletofindsolutionstoLMI’srepresentingmanycontrolsystems
problemswhichwewillintroducenext.
8.2 ControlProblemsUsingLMI
| 8.2.1 | Lyapunov | StabilityCriterion |     |     |     |     |
| ----- | -------- | ------------------ | --- | --- | --- | --- |
Foracontinuous-timelinearsystemS
x˙(t)=Ax(t)+Bu(t)
(8.3)
y(t)=Cx(t)+Du(t)
where x(t) ∈ Rn is the state vector, u(t) ∈ Rm the input (control) vector, and
y(t)∈Rp the output (measurement) vector, the system is asymptotically stable if
| thereexistsapositivedefinitematrixP |     |     |     | >0suchthat |     |     |
| ----------------------------------- | --- | --- | --- | ---------- | --- | --- |
ATP +PA<0
(8.4)
ThisisanLMIfeasibilityproblem.
|        |      | ={p }, | =p                            |       |         |       |
| ------ | ---- | ------ | ----------------------------- | ----- | ------- | ----- |
| Remark | LetP | ij p   | ij ji .(8.4)canbere-writtenas |       |         |       |
|        |      |        | (cid:14) (cid:6)              |       | (cid:7) |       |
|        |      |        | p ATE                         | +E A  | <0      | (8.5) |
|        |      |        | ij                            | ij ji |         |       |
i,j
whereE ij isazeromatrixexceptits(i,j)elementbeing1.(8.5)isobviouslyinthe
formof(8.1).
8.2.2 StabilizationbyStateFeedback
Consider the system in (8.3) again. In the case that it is not asymptotically stable,
u=v−Fx,
a state feedback matrix F, in may be sought to form the following

8.2 ControlProblemsUsingLMI 95
closed-loopsystem:
x˙=(A−BF)x+Bv(t)
(8.6)
y(t)=Cx(t)+Dv(t)
whereweusev(t)todenotetheexternalinputandu(t)in(8.3)isgivenasu(t)=
v(t)−Fx(t).Tomaketheclosed-loopsystemasymptoticallystable,werequirethe
statefeedbackmatrixF tosatisfy,following(8.4),
| (A−BF)TP | +P(A−BF)<0 |     |     |
| -------- | ---------- | --- | --- |
(8.7)
or
| ATP | +PA−FTBTP | −PBF <0 | (8.8) |
| --- | --------- | ------- | ----- |
whereP >0istobefound.Herewewanttofindtwomatrices,F andP,in(8.8).
Thisisnotalinearinequality,ratheraquadraticone,duetothelasttwotermsinthe
−1
inequality. To make it linear, we may pre- and post-multiply P on (8.8), which
leadsto
| −1AT +AP | −1−P −1FTBT | −BFP −1<0 |       |
| -------- | ----------- | --------- | ----- |
| P        |             |           | (8.9) |
−1=:QanddefiningR=FQ,(8.9)becomes
BylettingP
| QAT | +AQ−RTBT | −BR<0 | (8.10) |
| --- | -------- | ----- | ------ |
which obviously is “linear”. Once the variables Q and R are found, the original
variablesP andF canbedirectlyrecovered.
Remark Thetechniqueusedaboveiscalled“changeofvariables”,whichisuseful
toderivealinearinequalityfromanoriginallynonlinearone.Itisimportanttonote
thatinthetransformationstheequivalenceofinequalitiesshouldberetainedandthe
originalvariablesshouldberecoverable.
L
8.2.3 Computationof Norm
2
Forageneral(stable)systemwithu(t)asitsinputandz(t)astheoutput,L norm
2
canbedefinedasanumberγ whichistheminimumpositivesatisfyingthefollowing
inequality:
|     | (cid:5)y(cid:5) <γ(cid:5)u(cid:5) | +β  |        |
| --- | --------------------------------- | --- | ------ |
|     | 2                                 | 2   | (8.11) |
where(cid:5)·(cid:5) denotesthestandard2-normofavectorfunction,i.e.
2
|                 | (cid:19)(cid:17) | (cid:20) |     |
| --------------- | ---------------- | -------- | --- |
|                 | ∞                | 1/2      |     |
| (cid:5)x(cid:5) | = xT(t)x(t)dt    |          |     |
2
0

| 96  |     |     |     |     |     |     |     | 8 LMIApproach |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ------------- | --- |
isalsocalledtheL
| asdefinedearlierinthebook,andβ |     |     |     | isapositiveconstant.γ |     |     |     |     | 2 - |
| ------------------------------ | --- | --- | --- | --------------------- | --- | --- | --- | --- | --- |
gainofthesystemwhichshowsthemaximumgainofthesystemoutputintermsof
“size”withregardtothatoftheinput,theRMSenergygain.
For a linear system in (8.3), the gain γ can be calculated from solving the fol-
| lowingmatrixinequality,forP |     |          |      | >0:  |     |        |          |     |        |
| --------------------------- | --- | -------- | ---- | ---- | --- | ------ | -------- | --- | ------ |
|                             |     | (cid:30) |      |      |     |        | (cid:31) |     |        |
|                             |     | ATP      | +PA+ | 1CTC | PB+ | 1CTD   |          |     |        |
|                             |     |          |      | γ    |     | γ      | <0       |     | (8.12) |
|                             |     |          | +    | 1DTC | −γI | + 1DTD |          |     |        |
BTP
|     |     |     |     | γ   |     | γ   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
(8.12)canbederivedasfollows.
(cid:5)(8.12) is equivalent to (8.13) below, by pre- and post-multiplying [xT uT] and
(cid:4)
| x ,∀[xT | uT]T | (cid:3)=0,respectively, |     |     |     |     |     |     |     |
| ------- | ---- | ----------------------- | --- | --- | --- | --- | --- | --- | --- |
u
|     | (cid:2) | (cid:3) (cid:30) |       |      |     |        | (cid:31)(cid:2) (cid:3) |     |        |
| --- | ------- | ---------------- | ----- | ---- | --- | ------ | ----------------------- | --- | ------ |
|     |         | T ATP            | +PA+  | 1CTC | PB+ | 1CTD   |                         |     |        |
|     | x       |                  |       |      |     |        | x                       |     |        |
|     |         |                  |       | γ    |     | γ      |                         | <0  | (8.13) |
|     | u       |                  | BTP + | 1DTC | −γI | + 1DTD | u                       |     |        |
|     |         |                  |       | γ    |     | γ      |                         |     |        |
whichleadsto
|     |               |          |     |           |               | (cid:19) |     | (cid:20) |        |
| --- | ------------- | -------- | --- | --------- | ------------- | -------- | --- | -------- | ------ |
|     |               |          |     | 1         |               |          | 1   |          |        |
|     | xTATPx+xTPAx+ |          |     | xTCTCx+xT |               | PB+      | CTD | u        |        |
|     |               |          |     | γ         |               |          | γ   |          |        |
|     |               | (cid:19) |     | (cid:20)  |               |          |     |          |        |
|     |               |          |     | 1         | 1             |          |     |          |        |
|     |               | +uT BTP  | +   | DTC x+    | uTDTDu−γuTu<0 |          |     |          | (8.14) |
|     |               |          |     | γ         | γ             |          |     |          |        |
and
1
|     | xTATPx+xTPAx+2xTPBu+ |     |     |     |     | yTy−γuTu<0 |     |     | (8.15) |
| --- | -------------------- | --- | --- | --- | --- | ---------- | --- | --- | ------ |
γ
˙
| BydefiningV |     | =xTPx | andusingV |     | =xTATPx+xTPAx+2xTPBu,(8.15) |     |     |     |     |
| ----------- | --- | ----- | --------- | --- | --------------------------- | --- | --- | --- | --- |
canbeexpressedas
1
|     |     |     | V   | ˙ + yTy−γuTu<0 |     |     |     |     | (8.16) |
| --- | --- | --- | --- | -------------- | --- | --- | --- | --- | ------ |
γ
Integratingtheabovefrom0to∞yields
|     |     |      | (cid:17) |              |     | (cid:17)      |     |     |     |
| --- | --- | ---- | -------- | ------------ | --- | ------------- | --- | --- | --- |
|     |     |      | ∞        | 1            |     | ∞ 1           |     |     |     |
|     |     | −V + |          | yT(t)y(t)dt− |     | uT(t)u(t)dt<0 |     |     |     |
V∞ 0
|     |     |     |     | γ   |     | γ   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     | 0   |     |     | 0   |     |     |     |
Furtherbyshiftingterms,takingthesquarerootandapplyingthetriangleinequality,
theaboveinequalitycanbere-writtenintheformof(8.11).

| 8.2 ControlProblemsUsingLMI |     |      |     | 97  |
| --------------------------- | --- | ---- | --- | --- |
| 8.2.4 Computationof         | H   | Norm |     |     |
∞
The H ∞ norm of a linear, stable system S as in (8.3) is bounded by a constant
| numberγ,i.e.(cid:5)S(cid:5) | ∞<γ,ifthereexistsP | >0suchthat |         |     |
| --------------------------- | ------------------ | ---------- | ------- | --- |
|                             | (cid:2)            |            | (cid:3) |     |
|                             | ATP +PA+CTC        | PB+CTD     |         |     |
<0
|     | BTP | +DTC DTD−γ2I |     |     |
| --- | --- | ------------ | --- | --- |
TheabovecanbeusediterativelytofindtheH ∞-normofS,theminimumγ.
Thisresultisactuallythewell-knownbounded-reallemma[184].Suchasystem
asin(8.3)iscallednonexpansive;ithastheproperty
|                        | (cid:17)       | (cid:17) |             |     |
| ---------------------- | -------------- | -------- | ----------- | --- |
|                        | tf             | tf       |             |     |
|                        | yT(t)y(t)dt≤γ2 |          | uT(t)u(t)dt |     |
|                        | 0              | 0        |             |     |
| foranyt >0,whenx(0)=0. |                |          |             |     |
f
8.2.5 FormulationofLQRinLMI
Forthelinear,time-invariantsystemin(8.3),theLinear–QuadraticRegulator(LQR)
problemis,givenaninitialconditionx(0)=x ,tofindastatefeedbacku=−Fx
o
thatminimizesthecostfunction
(cid:17)
|     |     | ∞(cid:6)  | (cid:7) |        |
| --- | --- | --------- | ------- | ------ |
|     | J = | xTQx+uTRu | dt      | (8.17) |
0
whereQ,R>0.
Thesolutiontothisproblemiswellknown(forexamplesee[8])andu=−Fx=
−R −1BTP, where P > 0 and solves the following Algebraic Riccati Equation
(ARE):
|     | ATP +PA−PBR | −1BTP | +Q=0 |     |
| --- | ----------- | ----- | ---- | --- |
Furthermore,
(cid:17)
|     |        | ∞(cid:6)  | (cid:7) |     |
| --- | ------ | --------- | ------- | --- |
|     | J =min | xTQx+uTRu | dt=xTPx |     |
|     | min    |           | o o     |     |
0
TheLQRproblemcanalsobeformulatedasanLMIProblem.Itcanbeshown
bydirectdeductionsthatwithaP >0satisfyingthefollowingmatrixinequality:
|     | ATP +PA−PBR | −1BTP | +Q<0 |     |
| --- | ----------- | ----- | ---- | --- |
(8.18)
−1BTP,wehave
| andbysettingthenegativestatefeedbackmatrixF |     |     | =R  |     |
| ------------------------------------------- | --- | --- | --- | --- |
(cid:17)
|     | ∞(cid:6) |           | (cid:7) |     |
| --- | -------- | --------- | ------- | --- |
|     | J =      | xTQx+uTRu | dt<xTPx |     |
o o
0

| 98  |     |     |     |     | 8 LMIApproach |
| --- | --- | --- | --- | --- | ------------- |
HencewecanreducethecostfunctionJ ifwecanfindsmallerP.However,(8.18)
isnotalinearinequalityinP.Weneedafew“tricks”here.
First, we define L=P −1 and pre- and post-multiply L on both sides of the
inequality(8.18),whichchangesitinto
|     |     | LAT +AL−BR | −1BT | +LQL<0 |     |
| --- | --- | ---------- | ---- | ------ | --- |
(8.19)
Next, we use the following Schur Complement Formula to transform equiva-
lently(8.19)intolinearinequalities.
| SchurComplementFormula |     |     | Forasymmetricmatrix |         |     |
| ---------------------- | --- | --- | ------------------- | ------- | --- |
|                        |     |     | (cid:2)             | (cid:3) |     |
M M
|     |     |     | M= 11 | 12   |        |
| --- | --- | --- | ----- | ---- | ------ |
|     |     |     | MT    |      | (8.20) |
|     |     |     |       | M 22 |        |
12
|                |     |             | −M  | −1MT     |     |
| -------------- | --- | ----------- | --- | -------- | --- |
| M<0ifandonlyif |     | M 22 <0andM | 11  | 12 M <0. |     |
22 12
SchurComplementFormulacanbeverifiedbypre-andpost-multiplying
|     |     |     | (cid:2) | (cid:3) |     |
| --- | --- | --- | ------- | ------- | --- |
−M −1
|     |     |     | I   | 12 M |     |
| --- | --- | --- | --- | ---- | --- |
22
|     |     |     | 0   | I   |     |
| --- | --- | --- | --- | --- | --- |
and
|     |     |     | (cid:2) | (cid:3) |     |
| --- | --- | --- | ------- | ------- | --- |
|     |     |     | I       | 0       |     |
|     |     |     | −M −1MT | I       |     |
22 12
respectively,onbothsidesoftheinequalityM<0.
|     |             | =LAT | +AL−BR | −1BT, =L | =−Q −1   |
| --- | ----------- | ---- | ------ | -------- | -------- |
| Now | by defining | M 11 |        | M 12     | and M 22 |
andusingtheSchurComplementFormula,solvingthequadraticmatrixinequality
(8.19)isequivalenttosolvingthefollowinglinearmatrixinequality:
|     |     | (cid:2) |     | (cid:3) |     |
| --- | --- | ------- | --- | ------- | --- |
−1BT
|     |     | LAT +AL−BR |     | L   |     |
| --- | --- | ---------- | --- | --- | --- |
<0 (8.21)
−Q −1
L
Further,inorderto findtheminimalcostfunction,we mayminimize γ, where
| >xTPx                                               | isrequired,i.e.xTPx |     | −γ                                    |     |         |
| --------------------------------------------------- | ------------------- | --- | ------------------------------------- | --- | ------- |
| γ o                                                 | o                   | o   | o <0.TowritethisinequalityintermsofL, |     |         |
| theSchurComplementFormulacanbeusedagain.BydefiningM |                     |     |                                       |     | =−γ,M = |
11 12
| xT andM | =−L=(−P | −1),itisequivalentto |         |         |        |
| ------- | ------- | -------------------- | ------- | ------- | ------ |
| o       | 22      |                      |         |         |        |
|         |         |                      | (cid:2) | (cid:3) |        |
|         |         |                      | −γ xT   |         |        |
|         |         |                      |         | o <0    | (8.22) |
−L
|     |     |     | x o |     |     |
| --- | --- | --- | --- | --- | --- |
Therefore,thestatefeedbackmatrixF,inu=−Fx,whichleadstotheminimal
cost function J can be found by solving the following LMI optimization problem
| forL>0andγ | >0: |     |     |     |     |
| ---------- | --- | --- | --- | --- | --- |

8.3 AFewMorePropertiesConcerningLMI 99
minγ
| (cid:2) | (cid:3) |     |     |     |
| ------- | ------- | --- | --- | --- |
| −γ      | xT      |     |     |     |
o
| s.t. | −L <0 |     |     |     |
| ---- | ----- | --- | --- | --- |
x o
| (cid:2) |        |      | (cid:3) |     |
| ------- | ------ | ---- | ------- | --- |
| LAT     | +AL−BR | −1BT |         |     |
L
|     |     |     | −1 <0 |     |
| --- | --- | --- | ----- | --- |
|     | L   | −Q  |       |     |
andF =R −1BTL −1.
8.3 AFewMorePropertiesConcerningLMI
InformulationsandsolutionproceduresofLMIs,anumberofexistingresults,such
astheSchurComplementFormula,canbeusedtohelpsolvetheproblems.Inthis
section,wewillintroduceafewofthem.Pleasenotethatproofsarenotgivenhere.
Interestedreaderscanconsulttheliterature,forexample[15,49,50]andreferences
therein.
8.3.1 Congruence Transformation
For a given positive definite (real) matrix M >0, the matrix VMVT >0 holds,
whereV isarealmatrixoffullrowrank.Thiscanbeprovedbyusingthedefinition
ofpositivedefinitenessandiscalledcongruencetransformation.Thepositivedef-
initeness is therefore invariant under congruence transformations. This property is
useful,forexample,totransformbilineartermsinamatrixinequalityintoalinear
one,withvariablechangesasinthefollowing.
Wehavethematrixinequality
| (cid:2) |     |      | (cid:3) |     |
| ------- | --- | ---- | ------- | --- |
| ATP     | +PA | +CTQ |         |     |
PBF
| M=    |     |     | <0  | (8.23) |
| ----- | --- | --- | --- | ------ |
| FTBTP | +QC | −2Q |     |        |
wherethematrices A, B and C aregivenand P >0, Q>0 and(unstructured) F
| arematrixvariablestobefound.(8.23)isnotalinearmatrixinequalitybecauseof |     | (cid:4) | (cid:5) |     |
| ----------------------------------------------------------------------- | --- | ------- | ------- | --- |
P−1
the “bilinear” terms involved. By defining V = 0 and pre-multiplying V
Q−1
0
andpost-multiplyingVT (=V)onbothsidesof(8.23),yields
| (cid:2)    |        |           | (cid:3) |        |
| ---------- | ------ | --------- | ------- | ------ |
| P −1AT +AP | −1 BFQ | −1+P −1CT |         |        |
| −1FTBT     | −1     | −1        | <0      | (8.24) |
| Q          | +CP    | −2Q       |         |        |
Further,byintroducingX=P −1,Y =Q −1andZ=FQ −1,wehavethefollowing
linearmatrixinequalityinsteadof(8.24)or(8.23):
| (cid:2)                             |            | (cid:3)       |     |        |
| ----------------------------------- | ---------- | ------------- | --- | ------ |
| XAT                                 | +AX BZ+XCT |               |     |        |
|                                     |            |               | <0  | (8.25) |
| ZTBT                                | +CX        | −2Y           |     |        |
| ItisstraightforwardtorecoverP,QandF |            | fromX,Y andZ. |     |        |

| 100         |                                     |     |     |     |     |     |     | 8 LMIApproach |     |
| ----------- | ----------------------------------- | --- | --- | --- | --- | --- | --- | ------------- | --- |
| 8.3.2 Schur | ComplementsforNonstrictInequalities |     |     |     |     |     |     |               |     |
Intheprevioussection,theSchurComplementFormulawasintroducedforthecase
ofstrictinequalities.Fornonstrictinequalities,theMoore–Penrosepseudoinverse
ofconstantmatrixwillhavetobeused[15].
Forasymmetricmatrix
|     |     |     |     | (cid:2) |     | (cid:3) |     |     |     |
| --- | --- | --- | --- | ------- | --- | ------- | --- | --- | --- |
|     |     |     |     | M       | M   |         |     |     |     |
|     |     |     | M=  | 11      | 12  |         |     |     |     |
MT
M 22
12
| M≤0ifandonlyif |                                         | M ≤0andM |     | −M  | M†    | MT ≤0,andM |     | (I−M | M† )= |
| -------------- | --------------------------------------- | -------- | --- | --- | ----- | ---------- | --- | ---- | ----- |
|                |                                         | 22       |     | 11  | 12 22 | 12         |     | 12   | 22 22 |
| 0,whereM†      | denotestheMoore–PenrosepseudoinverseofM |          |     |     |       |            |     | .    |       |
|                | 22                                      |          |     |     |       |            |     | 22   |       |
8.3.3 ProjectionandFinsler’sLemmas
InanalysisandsynthesisofcontrolsystemsusingLMIs,afewresults,listedbelow,
canbeusedtotestthesolvabilityoftheLMIsandfurthertofindsolutions.Thefirst
isaquitestraightforwardone.
8.3.3.1 Lemma1
Theinequality,withthesymmetricvariableX,
|     |     | ⎡   |     |     |     | ⎤   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     | P   | P   | P   |     |     |     |     |
|     |     | ⎢   | 11  | 12  | 13  | ⎥   |     |     |     |
+X
|     |     | ⎣   | PT  | P   | P   | ⎦<0 |     |     | (8.26) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ |
|     |     |     | 12  | 22  | 23  |     |     |     |        |
|     |     |     | PT  | PT  | P   |     |     |     |        |
|     |     |     | 13  | 23  | 33  |     |     |     |        |
hasasolutionifandonly
|     |     |     | (cid:2) |     | (cid:3) |     |     |     |     |
| --- | --- | --- | ------- | --- | ------- | --- | --- | --- | --- |
P 11 P 13
|     |     |     |     |     | <0  |     |     |     | (8.27) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------ |
PT P
13 33
and,furthermore,anyXsatisfyingthefollowinginequalityisasolution:
|     |     |      |         |     | (cid:2) | (cid:3) | (cid:2) | (cid:3) |     |
| --- | --- | ---- | ------- | --- | ------- | ------- | ------- | ------- | --- |
|     |     |      | (cid:4) |     | (cid:5) |         | −1      |         |     |
|     |     |      |         |     | P       | P       | P       |         |     |
|     |     | X<−P | + PT    | P   | 11      | 13      |         | 12      |     |
|     |     | 22   | 12      | 23  | PT      |         | PT      |         |     |
P 33
|     |     |     |     |     | 13  |     |     | 23  |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
It can be shown that the above lemma holds by first interchanging Rows 1 and
2aswellasColumns1and2of(8.26),andthenapplyingtheSchurComplement
Formula.

8.3 AFewMorePropertiesConcerningLMI 101
8.3.3.2 Lemma2
Consider the LMI below, with symmetric P , P and P and the unstructured
|     |     | 11  | 22  | 33  |     |
| --- | --- | --- | --- | --- | --- |
variableX,
|     | ⎡       |       | ⎤      |     |        |
| --- | ------- | ----- | ------ | --- | ------ |
|     | P       | P +XT | P      |     |        |
|     | 11      | 12    | 13     |     |        |
|     | ⎣ PT +X | P     | P ⎦ <0 |     | (8.28) |
|     |         | 22    | 23     |     |        |
12
|     | PT  | PT  | P   |     |     |
| --- | --- | --- | --- | --- | --- |
|     | 13  | 23  | 33  |     |     |
TheLMI(8.28)hasasolutionXifandonlyif
|     | (cid:2) (cid:3) | (cid:2) |           | (cid:3) |     |
| --- | --------------- | ------- | --------- | ------- | --- |
|     | P 11 P 13       |         | P 22 P 23 |         |     |
|     |                 | <0 and  |           | <0      |     |
|     | PT P            |         | PT P      |         |     |
|     | 13 33           |         | 23 33     |         |     |
Furthermore,whentheabovetwoinequalitieshold,asolutionisgivenby
|     | X=P | −1PT  | −PT |     |        |
| --- | --- | ----- | --- | --- | ------ |
|     |     | 23 P  |     |     | (8.29) |
|     |     | 33 13 | 12  |     |        |
Thenecessaryconditionisstraightforwardbythefactthatallleadingminorsof
a negative (positive) definite matrix are negative (positive) definite and by certain
interchangeofrowsandcolumns.Toshowthesufficiencypart,itisobviousthatthe
LMI(8.28)isequivalenttothefollowingLMI,bytheSchurcomplement:
(cid:30) (cid:31)
| (cid:2) |         | (cid:3) |         |         |        |
| ------- | ------- | ------- | ------- | ------- | ------ |
|         | +XT     | P T     | (cid:4) | (cid:5) |        |
| P       | 11 P 12 |         | −1      |         |        |
|         |         | − 1 3   | P P     | P <0    | (8.30) |
| P T     | +X P    | T       | 33 31   | 32      |        |
| 1 2     | 22      | P       |         |         |        |
2 3
The matrix X defined in (8.29) simply cancels the off-diagonal terms in the left-
handsidematrixabovewhichleadstotheinequality(8.30)duetothenegativeness
propertyof(8.28).
8.3.3.3 Lemma3(ProjectionLemma)
For matrices A, B and a symmetric matrix P, the LMI below with unstructured
variableX
|     | ATXB+BTXTA+P |     | <0  |     | (8.31) |
| --- | ------------ | --- | --- | --- | ------ |
hasasolutionifandonlyif
| Ax=0orBx=0 |     | imply xTPx<0orx=0 |     |     | (8.32) |
| ---------- | --- | ----------------- | --- | --- | ------ |
Further, let A⊥ and B⊥ be matrices whose columns form a basis of ker(A) and
ker(B),i.e.theorthogonalcomplementsofAandB,respectively,(8.32)isequiva-
lentto
|     | AT      |       | TPB⊥<0 |     |        |
| --- | ------- | ----- | ------ | --- | ------ |
|     | ⊥ PA⊥<0 | and B | ⊥      |     | (8.33) |
Aproofcanbefoundin,forexample,[36].

| 102 |     |     |     |     |     | 8 LMIApproach |     |
| --- | --- | --- | --- | --- | --- | ------------- | --- |
8.3.3.4 Lemma4(Finsler’sLemma)
Itcanalsobeshownthat(8.33)isequivalenttothefollowingtwoinequalities,for
someσ:
P −σATA<0
−σBTB
|     |     |     |     | P   | <0  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
ThisresultissometimesreferredtoasFinsler’sLemma[15,36].
| 8.3.4 | TheS-Procedure |     |     | forQuadraticFunctions |     |     |     |
| ----- | -------------- | --- | --- | --------------------- | --- | --- | --- |
Many control problems can be formulated as constrained optimization problems
with the cost as well as constraint inequalities in quadratic forms. Some of such
problemsmaybere-formulatedasasingleLMI,byso-calledtheS-procedure.
| LetF   | ,F ,...,F     |       | bequadraticfunctionsofthevariablevectorx, |           |                      |           |        |
| ------ | ------------- | ----- | ----------------------------------------- | --------- | -------------------- | --------- | ------ |
|        | 0 1           | p     |                                           |           |                      |           |        |
|        |               | F     | (x)=xTT                                   | x+2uTx+v  | ,                    | i=0,...,p |        |
|        |               | i     |                                           | i         | i i                  |           |        |
| whereT | issymmetric.F |       | ,F                                        | ,...,F    | arerequiredtosatisfy |           |        |
|        | i             |       | 0                                         | 1         | p                    |           |        |
|        | F             | (x)≥0 | forallx                                   | suchthatF | (x)≥0,               | i=1,...,p | (8.34) |
|        |               | 0     |                                           |           | i                    |           |        |
≥0,
Obviously, a sufficient condition for (8.34) to be true is that there exist τ 1
≥0suchthat
...,τ
p
(cid:14)p
|     |     |     |          |     | (x)− | (x)≥0 |        |
| --- | --- | --- | -------- | --- | ---- | ----- | ------ |
|     |     |     | forallx, | F   | τ F  |       | (8.35) |
|     |     |     |          | 0   | i    | i     |        |
i=1
=1
The vice versa is not true, except when p and with the condition that F is
1
strictlypositiveforsomex.
(8.35)canbewrittenintheformofanLMIas
|     |     |     | (cid:2) | (cid:3) | (cid:2) | (cid:3) |     |
| --- | --- | --- | ------- | ------- | ------- | ------- | --- |
(cid:14)p
|     |     |     | T   | u   | T     | u    |     |
| --- | --- | --- | --- | --- | ----- | ---- | --- |
|     |     |     | 0   | 0 − | τ i   | i ≥0 |     |
|     |     |     | uT  |     | i uT  |      |     |
|     |     |     |     | v 0 |       | v i  |     |
|     |     |     | 0   |     | i=1 i |      |     |
Similarresultsexistwhenthecostinequalityin(8.34)isstrict.
8.3.5 DualizationLemma
|      | beanon-singularsymmetricmatrixin(cid:18)n×nandletU |     |     |     |     | andV         |     |
| ---- | -------------------------------------------------- | --- | --- | --- | --- | ------------ | --- |
| LetP |                                                    |     |     |     |     | betwocomple- |     |
mentarysubspaceswhose(direct)sumforms(cid:18)n.Then
|     | xTPx<0 |     | forallx∈U\O |     | xTPx≥0 | forallx∈V |     |
| --- | ------ | --- | ----------- | --- | ------ | --------- | --- |
and

8.3 AFewMorePropertiesConcerningLMI 103
isequivalentto
xTP −1x>0 forallx∈U ⊥ \O and xTP −1x≤0 forallx∈V ⊥.
The aboveis calledthe “DualizationLemma” andmay in some cases lead to a
simplerprocedureofLMIsolutions.

Part II
| Introduction | to Robust | Control |
| ------------ | --------- | ------- |
Toolbox v3

Chapter 9
Building Uncertain Models
Inthischapterweshowhowtobuilduncertainsystemmodelsusingthefunctions
of Robust Control Toolbox®3. Building such models is an important step in the
designofcontrolsystemswhoseplantspossesssometypeofuncertainty.Thecor-
responding functions of Robust Control Toolbox®3 allow to facilitate the process
ofbuildingdifferentuncertaintymodelsandtoanalyzeeasilythepropertiesofsuch
models.Firstwedescribehowtobuildmodelsofopen-loopandclosed-looplinear
time-invariant systems (LTI models) and how to investigate their basic properties.
ThenwepresentvariousfunctionsofRobustControlToolbox®3thatallowtocreate
modelsofsystemswithstructured(real)uncertainties.Theusageofthesefunctions
isillustratedforthesimplecaseofasecondordermass–damper–springsystem.Itis
shownhowtoinvestigateseveralpropertiesofuncertainmodelsinthetimedomain
andfrequencydomain.Finally,weshowhowtobuildmodelsofsystemswithun-
structured(complex)uncertainty.Creationofmodelswithadditiveormultiplicative
uncertaintyisconsideredindetail.
The presentation in this and the next three chapters of Part II is based to some
extentontheinformationgivenintheRobustControlToolbox®3User’sGuide[12]
anditspreviouseditions.
9.1 LTIModels
In this section we describe how to create and manipulate models of linear time-
invariantsystems(LTImodels)inMATLAB®.
CreationofLTImodelsisdonebythefollowingcommands:
• ss—State-spacemodels(SSobjects)
• tf—Transferfunctionmatrices(TFobjects)
• zpk—Zero-pole-gainmodels(ZPKobjects)
• frd—Frequencyresponsedatamodels(FRDobjects)
Furtheronweshowhowtocreatemodelsofmultivariablesystemsbyusingthe
commandsssandtf.
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 107
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_9,©Springer-VerlagLondon2013

108 9 BuildingUncertainModels
Creation of a state-space model of time-invariant continuous-time system is il-
lustratedbythefollowingexample.
Example9.1 Letusconsideratwo-input,two-outputsystemdescribedinthestate-
spacebytheequations
x˙=Ax+Bu
y=Cx+Du
where
|     | ⎡       | ⎤       | ⎡       | ⎤       |
| --- | ------- | ------- | ------- | ------- |
|     | −1      | 0 5     |         | 5 0     |
| A=⎣ |         | −4 ⎦    | B=⎣−4   | ⎦       |
|     | 2       | 1 ,     |         | 1       |
|     | −6 −3   | −2      |         | 0 6     |
|     | (cid:2) | (cid:3) | (cid:2) | (cid:3) |
|     | −1 0    | −4      | 3       | −2      |
| C=  |         | , D=    |         |         |
−4
|     | 2 3 | 6   |     | 1   |
| --- | --- | --- | --- | --- |
Thissystemiscompletelycontrollableandcompletelyobservablesothatitsstate-
spacemodelrepresentsaminimalrealization.
AfterenteringthematricesA,B,C,andDinMATLAB®,thestate-spacemodel
isobtainedbythecommandline
Gss = ss(A,B,C,D)
Enteringtheline
Gss
producesthefollowingresult:
a =
x1 x2 x3
x1 -1 0 5
x2 2 1 -4
x3 -6 -3 -2
b =
u1 u2
x1 5 0
x2 -4 1
x3 0 6
c =
x1 x2 x3
y1 -1 0 -4
y2 2 3 6

9.1 LTIModels 109
d =
u1 u2
|                 | y1    | 3 -2 |        |     |     |     |
| --------------- | ----- | ---- | ------ | --- | --- | --- |
|                 | y2 -4 | 1    |        |     |     |     |
| Continuous-time |       |      | model. |     |     |     |
TodisplaythestatematrixAofthemodelweentertheline
A = Gss.A
Inasimilarwayitispossibletodisplayothermatricesofthestate-spacemodel.
The state-space model is converted to a transfer function matrix model by the
commandline
| Gtf | = tf(Gss) |     |     |     |     |     |
| --- | --------- | --- | --- | --- | --- | --- |
Asaresultoneobtains
| Transfer |     | function  | from  | input | 1 to output... |     |
| -------- | --- | --------- | ----- | ----- | -------------- | --- |
|          | 3   | s^3 + s^2 | + 118 | s     | - 80           |     |
#1: ------------------------
|     | s^3 | + 2 s^2 | + 17   | s -   | 14      |     |
| --- | --- | ------- | ------ | ----- | ------- | --- |
|     | -4  | s^3 -   | 10 s^2 | - 172 | s + 144 |     |
#2: -----------------------------
|          |     | s^3 +    | 2 s^2  | + 17  | s - 14         |     |
| -------- | --- | -------- | ------ | ----- | -------------- | --- |
| Transfer |     | function | from   | input | 2 to output... |     |
|          | -2  | s^3 -    | 28 s^2 | - 52  | s + 109        |     |
#1: ----------------------------
|     |     | s^3 + 2 | s^2 + | 17 s  | - 14 |     |
| --- | --- | ------- | ----- | ----- | ---- | --- |
|     | s^3 | + 41    | s^2 - | 4 s + | 46   |     |
#2: -----------------------
|     | s^3 | + 2 s^2 | + 17 | s - | 14  |     |
| --- | --- | ------- | ---- | --- | --- | --- |
Itfollowsfromtheresultobtainedthatthetransferfunctionmatrixofthesystem
is
|     |     | ⎡   |                    |     |                   | ⎤   |
| --- | --- | --- | ------------------ | --- | ----------------- | --- |
|     |     |     | 3s3+s2+118s−80     |     | −2s3−28s2−52s+109 |     |
|     |     | G=⎣ | s3+2s2+17s−14      |     | s3+2s2+17s−14     | ⎦   |
|     |     |     | −4s3−10s2−172s+144 |     | s3+41s2−4s+46     |     |
|     |     |     | s3+2s2+17s−14      |     | s3+2s2+17s−14     |     |
Thesystemisnotstrictlypropersincethedegreeofnumeratorpolynomialsisequal
tothedegreeofdenominatorpolynomials.
Todeterminethepolesandtransmissionzeroswemayusethestate-spacemodel
implementingthecommandspoleandzero.Asaresultweobtain

110 9 BuildingUncertainModels
p = pole(Gss)
p =
-1.3681 + 4.1404i
-1.3681 - 4.1404i
0.7363
z = zero(Gss)
z =
-0.9087 +11.1357i
-0.9087 -11.1357i
2.2174
Notethatthetransmissionzerosarenotnecessarilythezerosofthepolynomials
inthenumeratorsoftransferfunctionmatrixelements.
The commands pole and zero may be used also to determine the poles and
zerosfromthetransferfunctionmatrixmodel.However,inthiscaseweobtain
p = pole(Gtf)
p =
-1.3681 + 4.1404i
-1.3681 - 4.1404i
0.7363
-1.3681 + 4.1404i
-1.3681 - 4.1404i
0.7363
z = zero(Gtf)
z =
-0.9087 +11.1357i
-0.9087 -11.1357i
-1.3681 + 4.1404i
-1.3681 - 4.1404i
2.2174
0.7363
i.e.,thepolesandzerosoftheoriginalsystemarerepeatedtwice.Inthiscaseinstead
of finding the poles and zeros of the third order system the commands pole and
zero determine the poles and zeros of the state-space realization of sixth order
thatisobtainedasanintermediateresultinthepolesandzeroscomputation.(The

| 9.1 LTIModels |     |     |     |     |     |     |     | 111 |
| ------------- | --- | --- | --- | --- | --- | --- | --- | --- |
computation of these quantities is done in the state-space.) This fact is confirmed
executingthecommandline
G = ss(Gtf)
whichproducesastate-spacerealizationfromthetransferfunctionmatrixcomputed
previously.Theresultofthiscommandis
a =
|     | x1  | x2     |      | x3  | x4  | x5    |     | x6  |
| --- | --- | ------ | ---- | --- | --- | ----- | --- | --- |
| x1  | -2  | -2.125 | 1.75 |     | 0   | 0     |     | 0   |
| x2  | 8   | 0      |      | 0   | 0   | 0     |     | 0   |
| x3  | 0   | 1      |      | 0   | 0   | 0     |     | 0   |
| x4  | 0   | 0      |      | 0   | -2  | -4.25 | 3.5 |     |
| x5  | 0   | 0      |      | 0   | 4   | 0     |     | 0   |
| x6  | 0   | 0      |      | 0   | 0   | 1     |     | 0   |
b =
| u1  | u2  |     |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| x1  | 4 0 |     |     |     |     |     |     |     |
| x2  | 0 0 |     |     |     |     |     |     |     |
| x3  | 0 0 |     |     |     |     |     |     |     |
| x4  | 0 8 |     |     |     |     |     |     |     |
| x5  | 0 0 |     |     |     |     |     |     |     |
| x6  | 0 0 |     |     |     |     |     |     |     |
c =
|     | x1    | x2    |        | x3   | x4    |         | x5  | x6    |
| --- | ----- | ----- | ------ | ---- | ----- | ------- | --- | ----- |
| y1  | -1.25 | 2.094 | -1.188 |      | -3    | -0.5625 |     | 2.531 |
| y2  | -0.5  | -3.25 |        | 2.75 | 4.875 | -0.6562 |     | 1.875 |
d =
| u1              | u2   |        |     |     |     |     |     |     |
| --------------- | ---- | ------ | --- | --- | --- | --- | --- | --- |
| y1              | 3 -2 |        |     |     |     |     |     |     |
| y2 -4           | 1    |        |     |     |     |     |     |     |
| Continuous-time |      | model. |     |     |     |     |     |     |
Itisseenthataftertheinverseconversionfromtransferfunctionmatrixtostate-
spacemodelweobtainasixthorderrealization.Thisrealizationisobviouslynon-
minimal.
The minimal state-space realization may be obtained in the given case by the
command
G = ss(Gtf,’min’)
Theresultis

112 9 BuildingUncertainModels
a =
|           | x1    |         | x2    | x3       |
| --------- | ----- | ------- | ----- | -------- |
| x1 -1.784 |       |         | -5.23 | 2.632    |
| x2        | 3.298 | -0.3631 |       | -0.01393 |
| x3 0.2271 |       |         | 1.286 | 0.147    |
b =
|            | u1    |          | u2    |     |
| ---------- | ----- | -------- | ----- | --- |
| x1 0.6277  |       |          | 6.158 |     |
| x2         | 2.925 | -0.03289 |       |     |
| x3 -0.1801 |       | 0.2784   |       |     |
c =
|           | x1  | x2     |       | x3  |
| --------- | --- | ------ | ----- | --- |
| y1 -4.016 |     | -0.691 | 2.544 |     |
| y2 6.238  |     | -1.907 | 1.88  |     |
d =
| u1    | u2  |     |     |     |
| ----- | --- | --- | --- | --- |
| y1 3  | -2  |     |     |     |
| y2 -4 | 1   |     |     |     |
Tocreateastate-spacemodelofthediscrete-timesystem
|     |     |     | x =Ax | +Bu , |
| --- | --- | --- | ----- | ----- |
|     |     |     | k+1   | k k   |
|     |     |     | y =Cx | +Du , |
|     |     |     | k     | k k   |
onemayuseagainthecommandsssettinginadditionthesamplingperiodT :
s
Gd = ss(A,B,C,D,Ts)
The discretization of a continuous-time state-space model G for a given sampling
periodT maybedonebythecommandc2d.
s
Gd = c2d(G,Ts)
Consider now how to obtain a model of a multivariable system described by a
transferfunctionmatrix.
Example9.2 Givenisatwo-inputtwo-outputfifthordersystemwithtransferfunc-
tionmatrix
(cid:30) (cid:31)
|     |     |                  | 6   | −0.05  |
| --- | --- | ---------------- | --- | ------ |
|     |     | (0.9s+1)(0.1s+1) |     | 0.1s+1 |
G=
|     |     |     | 0.07   | 5                 |
| --- | --- | --- | ------ | ----------------- |
|     |     |     | 0.3s+1 | (1.8s−1)(0.06s+1) |

9.1 LTIModels 113
Toenterthismatrixweusethecommandlines
s = tf(’s’);
| g11 | = 6/((0.9*s    | + 1)*(0.1*s       | + 1)); |
| --- | -------------- | ----------------- | ------ |
| g12 | = -0.05/(0.1*s | +                 | 1);    |
| g21 | = 0.07/(0.3*s  | + 1);             |        |
| g22 | = 5/((1.8*s    | - 1)*(0.06*s+1)); |        |
| G   | = [g11 g12;    | g21 g22]          |        |
Asaresultweobtain
| Transfer | function | from | input 1 to output... |
| -------- | -------- | ---- | -------------------- |
6
#1: ----------------
|     | 0.09 s^2 | + s + 1 |     |
| --- | -------- | ------- | --- |
0.07
#2: ---------
|          | 0.3 s +  | 1    |                      |
| -------- | -------- | ---- | -------------------- |
| Transfer | function | from | input 2 to output... |
-0.05
#1: ---------
|     | 0.1 s + | 1   |     |
| --- | ------- | --- | --- |
5
#2: ----------------------
|     | 0.108 s^2 | + 1.74 | s - 1 |
| --- | --------- | ------ | ----- |
A state-space realization of this transfer function matrix may be obtained as
showninExample9.1alwaystryingtoobtainaminimalrealization.
Thesingularvalueplotofthesystemfrequencyresponseisobtainedbythecom-
mand sigma. (The same command is used for SS and TF models.) To obtain the
| singularvaluesintherange10 |     | −2–103 | rad/sweenterthecommandline |
| -------------------------- | --- | ------ | -------------------------- |
| sigma(G,{10^(-2)           |     | 10^3}) |                            |
The system singular values are shown in Fig. 9.1. It is seen that below the fre-
quency1rad/sthesystemgainremainsconstant.
GiventwosystemswithtransferfunctionmatricesG andG
1 2 ,thetransfermatrix
of their series connection (provided that the first system has the same number of
outputsastheinputsofsecondsystem)isfoundbythecommandline
G = G2*G1
TheparallelconnectionoftwosystemsG andG withequalnumberofinputsand
1 2
equalnumberofoutputsisfoundbythecommandline
| G   | = G1 + G2 |     |     |
| --- | --------- | --- | --- |

114 9 BuildingUncertainModels
Fig.9.1 Systemsingularvalueplot
Coprimefactorizationofatransferfunctionmatrixmaybedonebythecommand
ncfmr.
TheH ∞ systemnormmaybeobtainedusingthesingularvalueplotofthefre-
quencyresponse.However,thismayleadtoerrorsincaseoflightlydampedsystems
sothatitisbettertousethefunctionnorm(G,’inf’),whichperformsthecom-
putationofH ∞-normofGinthestatespace.
Example9.3 Considerthe2×2transferfunctionmatrix
⎡ ⎤
10(s+1) 1
G(s)=⎣s2+0.2s+100 s+1 ⎦
s+2 5(s+1)
s2+0.1s+10 (s+2)(s+3)
The singular values of G(jω) are shown in Fig. 9.2. From the largest singular
value we obtain the result that its maximum is about 34 dB which corresponds to
H ∞ normequalto50.12.Moreaccuratecomputationofthenormmaybedoneby
thecommandline
norm(G,’inf’)
whichgives
ans =
50.2471

9.1 LTIModels 115
Fig.9.2 LargestandsmallestsingularvaluesofG(jω)
Fig.9.3 Multivariablefeedbacksystem
Consider now the block-diagram of a multivariable feedback system shown in
Fig.9.3.ThesystemconsistsofplantGandcontrollerKandhasreferencer,sensor
noisen,inputdisturbanced ,andoutputdisturbanced.Allsignalsareassumedto
i
bevectorsignalsandthetransferfunctionmatriceshaveappropriatedimensions.
Iftheclosed-loopsystemisinternallystable,itsatisfiesthefollowingequations:
| y=T (r−n)+GS  | +S        |       |
| ------------- | --------- | ----- |
| o             | i d i o d | (9.1) |
| r−y=S (r−d)+T | n−GS d    | (9.2) |
| o             | o i i     |       |
| u=KS (r−n)−KS | d−T d     | (9.3) |
o o i i
| =KS (r−n)−KS | d+S     |       |
| ------------ | ------- | ----- |
| u g o        | o i d i | (9.4) |

116 9 BuildingUncertainModels
wherewemakeuseofthefollowingnotation.TheinputlooptransfermatrixL i and
theoutputlooptransfermatrixL aredefined,respectively,as
o
| L =KG, | L   | =GK |
| ------ | --- | --- |
| i      | o   |     |
Theinputsensitivitymatrixisdefinedasthetransferfunctionmatrixfromd tou :
i g
|     | =(I +L −1 |     |
| --- | --------- | --- |
| S   | i i )     |     |
Theoutputsensitivitymatrixisdefinedasthetransferfunctionmatrixfromd toy:
|     | =(I +L −1 |     |
| --- | --------- | --- |
| S o | o )       |     |
Theinputandoutputcomplementarysensitivitymatrixaredefinedas
−1
| T =I −S | =L (I +L | )   |
| ------- | -------- | --- |
| i       | i i      | i   |
−1
| T =I −S | =L (I +L | )   |
| ------- | -------- | --- |
| o       | o o      | o   |
respectively.
Thesensitivitytransfermatricesarecalledalsosensitivityfunctions.
Thecomputationofthesetransferfunctionmatricesandcorrespondingfrequency
responsesisillustratedbythefollowingexample.
Example9.4 Consideratwo-channelsystem(i.e.,asystemwithtwoinputsandtwo
outputs)withastructureshowninFig.9.3.Theplantisoffifthorderwithtwoinputs
andtwooutputsandhasatransferfunctionmatrix
| (cid:30)            |                   | (cid:31) |
| ------------------- | ----------------- | -------- |
| 6                   |                   | −0.05    |
| G= (0.9s+1)(0.1s+1) |                   | 0.1s+1   |
| 0.07                |                   | 5        |
| 0.3s+1              | (1.8s−1)(0.06s+1) |          |
(HowtoenterthistransferfunctionmatrixwasshowninExample9.2.)
Thesystemcontrollerhasthetransferfunctionmatrix
| (cid:30) |     | (cid:31) |
| -------- | --- | -------- |
7(s+1)
0
0.3s+1
K=
18(s+2)
0
s+1
The closed-loop input and output sensitivity functions and input and output loop
transfermatricesarefoundbythecommandlines
looptransfer = loopsens(G,K);
Si = looptransfer.Si;
Ti = looptransfer.Ti;
So = looptransfer.So;
To = looptransfer.To;
Li = looptransfer.Li;
Lo = looptransfer.Lo;
Itshouldbetakenintoaccountthatthecommandloopsensdoesnotproduce
thetransfermatricesthemselvesbuttheirrealizationsinthestate-space.Ifnecessary,
thecorrespondingtransfermatricesmaybeobtainedfromtheserealizationsbythe
commandtf.

9.1 LTIModels 117
Fig.9.4 Outputlooptransferfunctions
Usingthecommandline
poles = looptransfer.Poles
onefindstheclosed-loppolesandusingthecommandline
stab = looptransfer.Stable
one checks the closed-loop system stability (stab = 1 means that the system is
stableandstab = 0meansthatthesystemisunstable).
ThesingularvalueplotsofoutputlooptransfermatrixL areshowninFig.9.4.
o
Thesingularvalueplotsofinputsensitivityandcomplementarysensitivityfunc-
tions are shown in Fig. 9.5. In the low frequency range the singular values of the
matrixS (jω)arebelow−30dB,whichmeansthattheinputdisturbanced isat-
i i
tenuatedmorethan30timesatplantinput.
It should be noted that in the multivariable case the sensitivity functions with
respecttotheinputandoutputaregenerallydifferent(S (cid:3)=S ,L (cid:3)=L ).
o i o i
The singular value plots of output sensitivity and complementary sensitivity
functions are shown in Fig. 9.6. It is seen that for frequencies above 1000 rad/s
the singular values of matrix T (jω) are below −40 dB, i.e., the noise n in this
o
frequencyrangeissuppressedmorethan100timesatplantoutput.
Itisinstructivetoseealsothesensitivityoftheplantinputtosensornoise.Ac-
cordingto(9.4)thissensitivityisdeterminedbythesingularvaluesofK(jω)S (jω)
o
whichareshowninFig.9.7.Itisseenthatthemaximumofthesensitivityismore
than30dBforafrequencycloseto40rad/sanditisnotlessthan25dBforfrequen-
ciesgreaterthan100rad/s.Thismeansthatwhilethesensornoisesaresuppressed

118 9 BuildingUncertainModels
Fig.9.5 Inputsensitivityandcomplementarysensitivity
morethan100timesatplantoutput,theyareamplified18timesatplantinput.The
amplificationofsystemnoisesatplantinputisundesirablesinceitmayleadtosat-
urationofactuatorsandintroducesnonlineareffectinclosed-loopsystembehavior.
Considernowhowtoobtainthetransientresponsesoftheclosed-loopsystem.
Example9.5 LetusconsideragainthesystemdescribedinExample9.4.Thetran-
sientresponseofthefirstoutputy duetothestepreferencer isobtainedaccording
1 1
to(9.2)bythecommandlines
| tfin = 1;                           |          |             |
| ----------------------------------- | -------- | ----------- |
| time = 0:tfin/500:tfin;             |          |             |
| nstep = size(time,2);               |          |             |
| ref1(1:nstep)                       | = 1.0;   |             |
| ref2(1:nstep)                       | = 0.0;   |             |
| ref = [ref1’                        | ref2’];  |             |
| [y,t] = lsim(To(1:2,1:2),ref,time); |          |             |
| plot(t,y(:,1),’r-’)                 |          | grid        |
| title(’From                         | ref 1    | to outp 1’) |
| xlabel(’Time                        | (secs)’) |             |
ylabel(’y_1’)

9.1 LTIModels 119
Fig.9.6 Outputsensitivityandcomplementarysensitivity
In y(:,2) one obtains the transient response of the second output y due to
2
the first reference. Setting ref1(1:nstep) = 0.0; ref2(1:nstep) =
1.0;oneobtainsthetransientresponsesduetothesecondreference.
Theclosed-looptransientresponsesduetostepreferencesareshowninFig.9.8.
Itisseenthatthereissomeinfluencebetweenthechannels(i.e.,theyarenotfully
decoupled),duetothepresenceofoff-diagonalelementsintheplanttransfermatrix
andthediagonalstructureofthecontrollertransfermatrix.Theovershootofthefirst
outputdoesnotexceed50%.
Sincetherelationshipbetweentheinputdisturbancesandclosed-systemoutputs
is given by y =GS d the transient response of the first output due to step input
i i
| disturbanced 1          | isobtainedbythecommands |     |
| ----------------------- | ----------------------- | --- |
| time = 0:tfin/500:tfin; |                         |     |
| nstep = size(time,2);   |                         |     |
| dist1(1:nstep)          | = 1.0;                  |     |
| dist2(1:nstep)          | = 0.0;                  |     |
| dist = [dist1’          | dist2’];                |     |
sys = G*Si;
| [y,t] = lsim(sys(1:2,1:2),dist,time); |        |               |
| ------------------------------------- | ------ | ------------- |
| plot(t,y(:,1),’r-’)                   |        | grid          |
| title(’From                           | dist 1 | to output 1’) |

120 9 BuildingUncertainModels
Fig.9.7 Sensitivitytonoiseatplantinput
Fig.9.8 Transientresponsestoreference

9.2 StructuredUncertaintyModels 121
Fig.9.9 Transientresponsesduetoinputdisturbances
xlabel(’Time (secs)’)
ylabel(’y_1’)
Thetransientresponseofthesecondoutputduetothefirstinputdisturbanced is
1
obtainediny(:,2).
Similarlyonemayobtainthetransientresponsesduetotheoutputdisturbances.
The closed-loop transient responses due to input and output disturbances are
showninFigs.9.9and9.10,respectively.
9.2 Structured UncertaintyModels
Inthissectionweshallconsiderhowtobuildmodelswithparametric(real)uncer-
tainty by implementing various ways to describe such models available in Robust
Control Toolbox®3. In our presentation we shall use a simple, second order, me-
chanicalsystem,namelyamass–damper–springsystem.Themass–damper–spring
systemisacommoncontrolexperimentaldevicefrequentlyseeninanundergradu-
ateteachinglaboratory.
The one-degree-of-freedom (1DOF) mass–damper–spring system is depicted in
Fig.9.11.
Thedynamicsofsuchasystemcanbedescribedbythefollowingsecondorder
differentialequation,byNewton’sSecondLaw,
mx¨+cx˙+kx=u (9.5)

122 9 BuildingUncertainModels
Fig.9.10 Transientresponsesduetooutputdisturbances
Fig.9.11
Mass–damper–springsystem
Fig.9.12 Blockdiagramof
themass–damper–spring
system
where x is the displacement of the mass block from the equilibrium position and
u=F istheforceactingonthemass,withmthemass,cthedamperconstantand
kthespringconstant.
AblockdiagramofsuchasystemisshowninFig.9.12,settingy=x.

9.2 StructuredUncertaintyModels 123
| =x,x | =dx/dt, |     |     |     |     |
| ---- | ------- | --- | --- | --- | --- |
Denoting x 1 2 the system (9.5) may be described in the state-
spaceform
|     |     | x˙=Ax+Bu |     |     | (9.6) |
| --- | --- | -------- | --- | --- | ----- |
y=Cx+Du
(9.7)
where
| (cid:2) | (cid:3) | (cid:2) | (cid:3) |                 |     |
| ------- | ------- | ------- | ------- | --------------- | --- |
|         |         |         |         | (cid:4) (cid:5) |     |
| 0       | 1       | 0       |         |                 |     |
| A=      | ,       | B=      | , C=    | 1 0 ,           | D=0 |
| −k      | −c      | 1       |         |                 |     |
| m       | m       | m       |         |                 |     |
Thetransferfunctionofthissystemisgivenby
|     |     | y(s) | 1   |     |     |
| --- | --- | ---- | --- | --- | --- |
=
(9.8)
|     |     | u(s) ms2+cs+k |     |     |     |
| --- | --- | ------------- | --- | --- | --- |
In a realistic system, the three physical parameters m, c, and k are not known
exactly. However, it can be assumed that their values are within certain, known
intervals.Thatis,
| m=m(1+p |          | c=c(1+p |          | k=k(1+p |         |
| ------- | -------- | ------- | -------- | ------- | ------- |
|         | m δ m ), |         | c δ c ), |         | k δ k ) |
wherem=3,c=1,k=2arecallednominalvaluesofm,c,andk.Thequantities
p ,p ,andp ,andδ ,δ ,andδ representthepossible(relative)perturbationson
| m c k | m c | k   |     |     |     |
| ----- | --- | --- | --- | --- | --- |
thesethreeparameters.Inthepresentcase,weletp =0.4,p =0.2,p =0.3and
|     |     |     | m   | c   | k   |
| --- | --- | --- | --- | --- | --- |
−1≤δ ≤1.
m ,δ c ,δ k Note that this represents up to 40 % uncertainty in the mass,
20 % uncertainty in the damping coefficient and 30 % uncertainty in the spring
stiffness.
Thecommandlinesforbuildinguncertainmodelsofmass-damper-springsystem
andaccessingtheirpropertiesmaybefoundintheM-filemds_models.m.
9.2.1 UncertainRealParameters
ThesimplestwaytodescribeuncertainrealparameterinRobustControlToolbox®3
istousethefunctionureal.Thesyntaxofthisfunctionis
| p = ureal(’Name’,NominalValue,’Property1’,Value1, |     |     |     |     | ... |
| ------------------------------------------------- | --- | --- | --- | --- | --- |
’Property2’,Value2,...)
The uncertain real parameter will have a name, set by ’Name’ and a nominal
valuesetbyNominalValue.
The maximum deviation from NominalValue may be set in three different
manners(byusingthecorresponding’Property’):
• PlusMinus:theabsolutedeviationfromNominalValue
• Range:theintervalcontainingNominalValue
•
Percentage:thepercentagedeviationfromNominalValue

| 124 |     |     |     | 9 BuildingUncertainModels |
| --- | --- | --- | --- | ------------------------- |
TheModepropertyspecifieswhichoneofthesethreedescriptionsremainsun-
changed if the NominalValue is changed. The possible values of Mode are
’Range’,’Percentage’and’PlusMinus’,thedefaultvalueofModebeing
’PlusMinus’withvalue[−11].
ThepropertyAutoSimplifyofurealspecifieshowtosimplifyexpressions,
containinguncertainparametersandisusefulincaseswhensomeparametersappear
severaltimes.Itsdefaultvalueisbasicwhichmeansthatelementarymethodsfor
algebraic simplification are implemented. Other possible values are off (without
simplification) and full (model-reduction methods are applied to the uncertain
object).
Usingthefunctionurealtheuncertainparametersofthemass-damper-spring
systemmaybesetbythefollowinglines:
| m = ureal(’m’,3,’Percentage’,[-40, |     |     | 40]) |     |
| ---------------------------------- | --- | --- | ---- | --- |
c = ureal(’c’,1,’Range’,[0.8, 1.2])
| k = ureal(’k’,2,’PlusMinus’,[-0.6, |     |     | 0.6]) |     |
| ---------------------------------- | --- | --- | ----- | --- |
Asaresultthefollowinginformationisdisplayed:
| Uncertain | Real Parameter: |     | Name m, NominalValue | 3,  |
| --------- | --------------- | --- | -------------------- | --- |
variability = [-40 40]%
| Uncertain | Real Parameter: |     | Name c, NominalValue | 1,  |
| --------- | --------------- | --- | -------------------- | --- |
Range [0.8 1.2]
| Uncertain | Real Parameter: |     | Name k, NominalValue | 2,  |
| --------- | --------------- | --- | -------------------- | --- |
variability = [-0.6 0.6]
9.2.2 UncertainState-SpaceSystems
Oncetheuncertainparametersareset,thereareseveralwaystoobtaintheuncertain
systemdescription.
First, it is possible to use the state-space description (9.6), (9.7). Entering the
lines
| A = [  | 0 1    |     |     |     |
| ------ | ------ | --- | --- | --- |
| -k/m   | -c/m]; |     |     |     |
| B = [0 | 1/m]’; |     |     |     |
| C = [1 | 0];    |     |     |     |
D = 0;
| uss1 = | ss(A,B,C,D) |     |     |     |
| ------ | ----------- | --- | --- | --- |
weobtainanobjectuss1fromtheclassuss—uncertainstatespace.Itshouldbe
noted that in the case of uncertain parameters the resulting system is always from
theclassussnomatterwhichfunctionisusedtobuildthesystem.Inthegivencase
weobtain
| USS: 2   | States, 1 | Output, | 1 Input, Continuous | System       |
| -------- | --------- | ------- | ------------------- | ------------ |
| c: real, | nominal   | = 1,    | range = [0.8 1.2],  | 1 occurrence |

9.2 StructuredUncertaintyModels 125
| k: real, nominal | = 2, | variability | = [-0.6 | 0.6], |
| ---------------- | ---- | ----------- | ------- | ----- |
1 occurrence
| m: real, nominal | = 3, | variability | = [-40 | 40]%, |
| ---------------- | ---- | ----------- | ------ | ----- |
3 occurrences
Thisresultshowsthattheparametermappearsinthesystemuss1threetimes
whichmeansthatthestate-spacerealizationobtaineddoesnotcontaintheminimum
possiblenumberoftheparameterm.Theusageofthecommandline
simplify(uss1,’full’)
doesnothelpinthegivencasetoproduceamodelinwhichtheparametermappears
againthreetimes.
Another possibility to obtain the uncertain state-space description is to use the
transferfunction(9.8).Enteringtheline
| uss2 = tf(1,[m,c,k]) |     |     |     |     |
| -------------------- | --- | --- | --- | --- |
weobtaintheuncertainobjectuss2.Hereweusetheextendedcapabilitiesofthe
functiontftoworkwithuncertainparameters.Inthegivencaseweobtain
| USS: 2 States,   | 1 Output, | 1 Input,     | Continuous | System       |
| ---------------- | --------- | ------------ | ---------- | ------------ |
| c: real, nominal | = 1,      | range = [0.8 | 1.2],      | 1 occurrence |
| k: real, nominal | = 2,      | variability  | = [-0.6    | 0.6],        |
1 occurrence
| m: real, nominal | = 3, | variability | = [-40 | 40]%, |
| ---------------- | ---- | ----------- | ------ | ----- |
1 occurrence
Notethattheparametermappearsinthesystemuss2onlyonce.
It is possible also to build the uncertain system describing directly the block-
diagrampresentedinFig.9.12byusingthefunctionfeedback.
s = tf(’s’);
g1 = (1/s)/m;
| int2 = 1/s;                            |     |     |     |     |
| -------------------------------------- | --- | --- | --- | --- |
| uss3 = feedback(int2*feedback(g1,c),k) |     |     |     |     |
Theresultisagainanobjectofclassuss:
| USS: 2 States,   | 1 Output, | 1 Input,     | Continuous | System       |
| ---------------- | --------- | ------------ | ---------- | ------------ |
| c: real, nominal | = 1,      | range = [0.8 | 1.2],      | 1 occurrence |
| k: real, nominal | = 2,      | variability  | = [-0.6    | 0.6],        |
1 occurrence
| m: real, nominal | = 3, | variability | = [-40 | 40]%, |
| ---------------- | ---- | ----------- | ------ | ----- |
1 occurrence
Herethethreeuncertainparametersparticipateonlyonce.
| 9.2.3 Propertiesof | UncertainSystems |     |     |     |
| ------------------ | ---------------- | --- | --- | --- |
Thepropertiesofuncertainobjectuss1maybeseenbyenteringtheline
get(uss1)

126 9 BuildingUncertainModels
whichgives
|     | a: [2x2 | umat] |
| --- | ------- | ----- |
|     | b: [2x1 | umat] |
|     | c: [1   | 0]    |
d: 0
| StateName: | {2x1 | cell} |
| ---------- | ---- | ----- |
Ts: 0
| InputName:   | {’’} |         |
| ------------ | ---- | ------- |
| OutputName:  | {’’} |         |
| InputGroup:  | [1x1 | struct] |
| OutputGroup: | [1x1 | struct] |
Name: ’’
| NominalValue: | [1x1 | ss]       |
| ------------- | ---- | --------- |
| Uncertainty:  | [1x1 | atomlist] |
Notes: {}
| UserData: | []  |     |
| --------- | --- | --- |
Thecommand
uss1.Uncertainty
produces
| c: [1x1 | ureal] |     |
| ------- | ------ | --- |
| k: [1x1 | ureal] |     |
| m: [1x1 | ureal] |     |
andthecommand
uss1.NominalValue
producesthenominalstate-spacedescription
a =
|            | x1      | x2  |
| ---------- | ------- | --- |
| x1         | 0       | 1   |
| x2 -0.6667 | -0.3333 |     |
b =
u1
| x1  | 0   |     |
| --- | --- | --- |
x2 0.3333
c =
| x1   | x2  |     |
| ---- | --- | --- |
| y1 1 | 0   |     |
d =
u1

9.2 StructuredUncertaintyModels 127
y1 0
Continuous-time model.
Theuncertainelementsofuncertainobjectmaybesubstitutedbyspecificvalues
usingthefunctionusubs.Thecommandline
B = usubs(A,name1,value1,name2,value2,...)
instantiatestheuncertainelementsname1,name2,... ofAtothevaluesvalue1,
value2,... .Inparticular,valueissetto‘NominalValue’or‘Random’inorder
tousethenominalvalueorarandominstanceofaparticularelement.Forinstance,
thenominalstate-spacedescriptionofuss1maybeobtainedby
usubs(uss1,’m’,3,’c’,1,’k’,2)
Another useful command implemented on uncertain objects is the command
usamplewhichrandomlysamplestheuncertainsystemataspecifiednumberof
points.Thecommandline
B = usample(A,n)
picksnrandomsamplesoftheuncertaintyinAandreturnsthesesamplesinanarray
Bofsize[size(A) n].
Itisinterestingtoseethefrequencyresponsesofthemass-damper-springsystem
for different values of the parameters m, c, and k. For this aim we may use the
extendedcapabilitiesofthefunctionbodeinMATLAB®7.Forobjectsoftheclass
ussthisfunctionplotsafamilyoffrequencyresponsesfor20randomvaluesofthe
uncertainelementsaswellasforthenominalvalues.Inthegivencaseweobtain
w = logspace(-1,1,200);
figure(1)
bode(uss1,w)
title(’Bode plot of uncertain system’)
grid
TheresultisshowninFig.9.13.
Thissamplingisdonealsowhenthefunctionsbodemag,impulse,nyquist
andsteparecalledonaussobject.Thecommandline
step(uss1), grid
producesthestepresponsesofthemass–damper–springsystemfor20randomval-
uesoftheuncertainelementsaswellasforthenominalvalues.Thesestepresponses
areshowninFig.9.14.
Thecommandlines
frres = frd(uss2,w)
nyquist(frres), grid
produce the Nyquist diagram of the uncertain system uss2, shown in Fig. 9.15.
The uncertain system uss2 is sampled at 20 values, as well as its nominal value,
andtheNyquistplotsofthese21systemsaredrawn.

128 9 BuildingUncertainModels
Fig.9.13 Bodeplotofuncertainsystem
Fig.9.14 Stepresponsesofuncertainsystem

9.2 StructuredUncertaintyModels 129
Fig.9.15 Nyquistdiagramofuncertainsystem
Sometimesitisnecessarytoanalyzethebehaviorofanuncertainsystemforuni-
formlyspacedvaluesofitsuncertainrealparameters.Insuchacaseitisappropriate
tousethecommandgridureal.Thecommandline
B = gridureal(A,n)
substitutes n uniformly spaced samples of the uncertain real parameters in uncer-
tain object A. The size of array B is equal to [size(A) n]. The n samples are
generated by uniformly griding each ureal parameter in A across its range. If A
includesuncertainobjectsotherthanureal,thenBisanuncertainobject.
Thecommandline
[B,SampleValues] = gridureal(A,names1,n1,names2,n2,...)
takesn1samplesoftheuncertainrealparameterslistedinnames1,andn2samples
oftheuncertainrealparameterslistedinnames2andsoon.size(B)willequal
[size(A) n1 n2 ...].
As an example consider how to obtain the step response of the mass-damper-
spring system for a grid of 50 values altogether of the uncertain parameters m, c
andk.Theline
step(gridureal(uss3,50)), grid
producesthestepresponseoftheuncertainsystemuss3foragridof50valuesof
theparametersm,c,andk,showninFig.9.16.

130 9 BuildingUncertainModels
Fig.9.16 Stepresponseforagridof50valuesofuncertainparameters
9.2.4 OtherFunctionstoBuildUncertainModels
Therearesomeadditionalfunctionsthatmaybeusefulinbuildinguncertainmodels.
Thecommanducomplexcreatesuncertaincomplexparameter.Thesyntaxof
thiscommandresemblesthesyntaxofcommandureal.
B = ucomplex(’Name’,NominalValue,’Property1’,Value1,...
’Property2’,Value2,...)
Heretheuncertainty(maximumdeviation)isspecifiedintwodifferentmanners:
by the property Radius (radius of disc centered at NominalValue), or by the
propertyPercentage(discsizeispercentageofmagnitudeofNominalValue).
Uncertain matrices (class umat) are built from uncertain parameters using
MATLAB® matrixbuildingsyntax.Thesematricescanbeadded,subtracted,mul-
tiplied, inverted, transposed, etc., resulting in uncertain matrices. The rows and
columnsofanuncertainmatrixarereferencedinthesamemannerthatMATLAB®
references rows and columns of an array, using parentheses, and integer indices.
Similarly to the case of real uncertain systems, specific values may be substituted
foranyoftheuncertainparameterswithinaumatusingthecommandusubs.The
commandusamplegeneratesarandomsampleoftheuncertainmatrix,substitut-
ingrandomsamples(withintheirranges)foreachoftheuncertainparameters.
Uncertaincomplexmatricesarebuiltwiththecommanducomplexm.
The command frd to compute frequency responses works also for objects of
classuss.Inthiscaseoneobtainsobjectofclassufrd—uncertainfrequencyre-

9.2 StructuredUncertaintyModels 131
Fig.9.17 Decompositionof
uncertainobject
sponse.Asanexample,thefrequencyresponseofthesystemuss1maybeobtained
bythelines
w = logspace(-1,1,200);
freqs = frd(uss1,w)
Theresultis
UFRD: 1 Output, 1 Input, Continuous System, 200 Frequency
points
c: real, nominal = 1, range = [0.8 1.2], 1 occurrence
k: real, nominal = 2, variability = [-0.6 0.6],
1 occurrence
m: real, nominal = 3, variability = [-40 40]%,
3 occurrences
Nowtheline
bode(freqs)
reproducestheBodeplot,showninFig.9.13.
Uncertain state-space system may be included in Uncertain State Space block
and used in Simulink® to simulate and linearize uncertain systems. The reader is
referredto[12,Chap.5]formoreinformationandexamplesontherepresentation
andanalysisofuncertainsystemsinSimulink®.
9.2.5 DecomposingUncertainObjects
Eachuncertainobject(umat,uss,ufrd)mayberepresentedasalinearfractional
transformationofnon-uncertainpartandamatrixcontainingtheuncertainparame-
ters.Usingthecommandlftdataanuncertainobjectmaybedecomposedintoa
nominalpartandanormalizeduncertaintymatrixwithH ∞ norm,equalto1.Fora
givenuncertainobjectusysthecommandline
[Gnom,Delta,Blkstruct,Normunc] = lftdata(usys)
producesa nominalsystem G and an uncertaintymatrix Δ connectedin a lin-
nom
ear fractional transformation (Fig. 9.17). The variable Blkstruct returns n×1
structure,whereBlkstruct(i)describestheithnormalizeduncertainelement.
ThevariableNormuncreturnsanarrayofnormalizeduncertainelements.
Letusdecomposetheuncertainsystemuss2:
[Gnom,Delta,Blkstruct,Normunc] = lftdata(uss2)

| 132 |     |     | 9 BuildingUncertainModels |
| --- | --- | --- | ------------------------- |
The variable Gnom is obtained as a state-space description of class ss, since it
doesnotcontainuncertainparameters,andDeltaisofclassumatcontainingthe
uncertainelementsm,candk.
9.3 BuildingUncertainModelsUsingiconnectand sysic
Theclassiconnectisusedtobuildcomplexinterconnectionsofuncertainmatri-
cesandsystems.Theiconnectobjectshavethreefieldsthatshouldbesetbythe
user.
• Input:symboliccolumnvector,representstheinputvariables;
•
Output:symboliccolumnvector,representstheoutputvariables;
• Equation: cell-array of equality constraints (created using the command
equate)
describing the relations between input, output and intermediate vari-
ables.
Initially, an empty object of class iconnect is created, and then the fields
Input,Output,andEquationarespecified.
Theinput,output,andintermediatevariablesshouldbeobjectsofclassicsig-
nal.Theyaresymbolicvectorsrepresentingthesignalsintheinterconnection.For
instance,thecommand
icsignal(4)
createsafourelementcolumnvectorforusebyiconnect.
Let us describe the mass–damper–spring system interconnection, shown in
Fig. 9.12, by using iconnect assuming that the uncertain parameters m, c and
k are already defined. For intermediate variables we choose x and x˙. The input,
output,andintermediatevariablesarecreatedbyusingicsignal.
u = icsignal(1)
x = icsignal(1)
| xdot = icsignal(1)    |             |                |                    |
| --------------------- | ----------- | -------------- | ------------------ |
| iconnect1             | = iconnect; |                |                    |
| iconnect1.Input       | = u;        |                |                    |
| iconnect1.Output      | =           | x;             |                    |
| iconnect1.Equation{1} |             | = equate(x,    | tf(1,[1,0])*xdot); |
| iconnect1.Equation{2} |             | = equate(xdot, | tf(1,[m,0])*       |
(u-k*x-c*xdot));
Withget(iconnect1)onemayseethepropertiesofthesystemobtained:
| Equation: | {[1x1          | icsignal] [1x1 | icsignal]} |
| --------- | -------------- | -------------- | ---------- |
| Input:    | [1x1 icsignal] |                |            |
| Output:   | [1x1 icsignal] |                |            |
| System:   | [1x1 uss]      |                |            |
Asaresultofthecommand
iconnect1.System

9.3 BuildingUncertainModelsUsingiconnectandsysic 133
weseethatsystemiconnect1isoftheclassuss:
USS: 2 States, 1 Output, 1 Input, Continuous System
c: real, nominal = 1, range = [0.8 1.2], 1 occurrence
k: real, nominal = 2, variability = [-0.6 0.6],
1 occurrence
m: real, nominal = 3, variability = [-40 40]%,
1 occurrence
Asanalternativeofthecommandiconnecttobuildcomplexinterconnections
of uncertain systems, one may use the command sysic. In order to implement
thiscommand,itisnecessarytoenterintotheworkspaceofMATLAB®thefollow-
ingvariables:systemnames,inputvar,andoutputvar.Thesevariablesare
characterstrings(char’s)withthefollowingmeaning.
• systemnamesisacharcontainingthenamesofsystemsthatshouldbecon-
nected.Theyhavetobeseparatedbyspaceswithnoadditionalpunctuation.The
systemsspecifiedinthecharshouldalreadyexistintheworkspace.
• inputvarisachar,specifyingtheexternalinputstotheinterconnection(the
names are formal, i.e., it is not necessary that these variables exist). The char
shouldhavetheformofacolumnvector(i.e.,enclosedinsquarebrackets[ ]).
The dimension of each input in the list may be set in braces { }, for instance
U1{3}.
• outputvarisachar,containingthesystemoutputsoractuallytheequations,
used to produce the output variables (they have no names); the outputs are ob-
tainedaslinearcombinationsofexternalinputsandsubsystemoutputsdescribed
insystemnames.Formultivariablesubsystems,argumentswithinparentheses
specifywhichsubsystemoutputsaretobeusedandinwhatorder.Forinstance,
theexpressionG(2:3,5)specifiesoutput2,3,and5fromthesubsystemG.
Foreachofthesubsystems,specifiedinsystemnames,itisnecessarytodefine
aseparatevariabledescribingitsinputsinawayvalidforoutputvar.Thenames
ofthesevariablesshouldbeginwithinput_to_andtofinishwiththesubsystem
name.
Thenthecommand
SysOutName = sysic
reads the subsystem names specified in systemnames, the interconnection
descriptions, and computes the description of the resulting system with name
SysOutName.Alsoacheckofthesignalnumberisdone.
Forthemass–damper–springsystem,descriptionwithsysicmaybeobtained
as follows (it is assumed that the uncertain parametersm, c and k already exist in
theworkspace).
m1 = inv(m);
int1 = 1/s;
int2 = tf(1,[1,0]);
systemnames = ’int1 int2 c k m1’;

134 9 BuildingUncertainModels
inputvar = ’[u]’;
outputvar = ’[int2]’;
input_to_int1 = ’[m1]’;
input_to_int2 = ’[int1]’;
input_to_c = ’[int1]’;
input_to_k = ’[int2]’;
input_to_m1 = ’[u-c-k]’;
uss4 = sysic
Notethattoobtain 1 weusethefunctioninv,sincemcontainsuncertaintyand
m
the direct division 1 leads to an error. Also, two different but equivalent ways to
m
definetheintegratorsint1andint2areimplemented.
Thesystemuss4obtainedisalsoofclassuss.
Theinterconnectionsbuiltwithsysicarecomponentwiseminimalinthesense
that the state dimension of the interconnection equals the sum of the state dimen-
sionsofthecomponents.Thismakessysicappropriateforbuildingcomplexun-
certaintymodels.
9.4 Unstructured UncertaintyModels
The unstructured (complex) uncertainty models are built using the function
ultidyn. The uncertain linear, time-invariant dynamics object ultidyn rep-
resentsanunknownlinearsystemwhoseonlyknownattributeisamagnitudebound
onitsfrequencyresponse.Thesyntaxofthisfunctionis
H = ultidyn(’Name’,ioSize,’Property1’,Value1, ...
’Property2’,Value2,...)
The uncertain dynamic object will have a name, set by ’Name’ and size ioSize,
[number-of-outputs number-of-inputs]. The property Type specifies whether the
knownattributesaboutthefrequencyresponsearerelatedtogainorphaseandhas
value ’GainBounded’ or ’PositiveReal’, respectively. The default value
is’GainBounded’.ThepropertyBoundisasinglenumber,which,alongwith
Type, completely specifies what is known about the uncertain system frequency
response.Specifically,ifΔisanultidynobject,andifγ denotesthevalueofthe
Boundproperty,thentheobjectrepresentsthesetofallstable,linear,time-invariant
systemswhosefrequencyresponsesatisfiestheconditions:
– If Type is ’GainBounded’, σ [Δ(ω)] ≤ γ for all frequencies, where
max
σ [Δ(ω)] is the maximum singular value of Δ(ω). When Type is ’Gain-
max
Bounded’,thedefaultvalueforBound(i.e.,γ)is1.
– If Type is ’PositiveReal’, Δ(ω) + Δ ∗ (ω) ≥ γ for all frequencies,
∗
where Δ (ω) denotes the Hermitian conjugate matrix of Δ(ω). When Type
isPositiveReal,thedefaultvalueforBound(i.e.,γ)is0.

9.4 UnstructuredUncertaintyModels 135
Fig.9.18 Plantwithadditive
uncertainty
ThepropertySampleStateDimisapositiveinteger,definingthestatedimen-
sionofrandomsamplesoftheuncertainobjectwhensampledwithusample.The
defaultvalueis1.
The property AutoSimplify of ultidyn is similar to the property Auto-
Simplifyofthefunctionureal.
Forinstance,thecommandline
uns = ultidyn(’uns’,[3 2],’Type’,’GainBounded’,’Bound’,1.8)
creates a ultidyn object with internal name uns, dimension 3-by-2 (three out-
puts,twoinputs),normboundedby1.8.
Objects of class ultidyn may be used together with uss objects to create
uncertain systems by using interconnect or sysic functions along with ba-
sicsysteminterconnectionfunctionsdefinedinControlSystemToolbox(append,
blkdiag,series,parallel,feedback,lft,andstack).
9.4.1 ModelswithAdditiveUncertainty
The following example illustrates the using of Robust Control Toolbox®3 com-
mandstoobtainamodelofSISOsystemwithadditiveuncertainty.
Example9.6 Considerafirstorderplantwithuncertaintyinthegainandtimecon-
stant:
K 0.7 1.3
G(s)= , 0.8≤K≤1.2, ≤T ≤
Ts+1 15 15
Thenominalmodelistakenas
1
G (s)=
n 1 s+1
15
Themodelwithadditiveuncertaintyischosenas
G(s)=G (s)+Δ (s)W (s)
n a a
where
(cid:18) (cid:18)
(cid:18)
Δ (jω)
(cid:18)≤1
a
Theblock-diagramoftheplantwithadditiveuncertaintyisshowninFig.9.18.

| 136 |     |     |     |     | 9 BuildingUncertainModels |     |
| --- | --- | --- | --- | --- | ------------------------- | --- |
To determine the weighting transfer function W a (s) we compute the error fre-
quency response G(jω)−G (jω) for different values of parameters K and T.
n
Thisisdonewithcommands
| omega = | logspace(-1,3,100); |     |     |     |     |     |
| ------- | ------------------- | --- | --- | --- | --- | --- |
%
| K0 = 1.0; | T0 = 1/15;         |      |     |     |     |     |
| --------- | ------------------ | ---- | --- | --- | --- | --- |
| Gnom =    | tf([K0],[T0        | 1]); |     |     |     |     |
| Gnom_frd  | = frd(Gnom,omega); |      |     |     |     |     |
figure(1)
hold off
| for K = | 0.8*K0:0.08*K0:1.2*K0     |      |     |     |     |     |
| ------- | ------------------------- | ---- | --- | --- | --- | --- |
| for     | T = 0.7*T0:0.06*T0:1.3*T0 |      |     |     |     |     |
|         | G = tf([K],[T             | 1]); |     |     |     |     |
G_frd = frd(G,omega);
|     | diff = G_frd | - Gnom_frd; |     |     |     |     |
| --- | ------------ | ----------- | --- | --- | --- | --- |
bodemag(diff,’c--’,omega)
hold on
end
end
grid
| temp1 = | ’Approximation | of            | uncertain | transfer     | function’; |         |
| ------- | -------------- | ------------- | --------- | ------------ | ---------- | ------- |
| temp2 = | ’ by additive  | uncertainty’; |           | title([temp1 |            | temp2]) |
legend(’|Wa(j\omega)|’,’|G(j\omega)-G_{nom}(j\omega)|’,3)
Thecomputationofthefrequencyresponsesisdonebythecommandfrd.
TheerrorfrequencyresponsesareshowninFig.9.19.
Wehave
|     | (cid:18)         | (cid:18)          | (cid:18)  |        | (cid:18) (cid:18) | (cid:18) |
| --- | ---------------- | ----------------- | --------- | ------ | ----------------- | -------- |
|     | (cid:18) G(jω)−G | (cid:18)=(cid:18) |           |        | (cid:18)≤(cid:18) | (cid:18) |
|     |                  | n (jω)            | W a (jω)Δ | a (jω) | W a               | (jω)     |
sothat|W (jω)|representsanupperboundontheerrorfrequencyresponse.Bythe
a
commands
| ord = | 2;  |     |     |     |     |     |
| ----- | --- | --- | --- | --- | --- | --- |
wfit
onefindsasufficientlyaccuratesecondorderapproximationofthisbound.Bythe
commands
| [freq,resp_db]          | =                     | ginput(20); |     | % pick     | 20 points     |             |
| ----------------------- | --------------------- | ----------- | --- | ---------- | ------------- | ----------- |
| for i =                 | 1:20                  |             |     | % Converts | the           | logarithmic |
| resp(i)                 | = 10^(resp_db(i)/20); |             |     | % response | to            | magnitude   |
| end                     |                       |             |     | % response |               |             |
| sys = frd(resp,freq);   |                       |             |     | % creates  | frd           | object      |
| W = fitmagfrd(sys,ord); |                       |             |     | % fits     | the frequency |             |
% response
| Wtf = tf(W); |     |     |     | % converting |      | into transfer |
| ------------ | --- | --- | --- | ------------ | ---- | ------------- |
|              |     |     |     | % function   | form |               |
storedinthefilewfit.m,onefindsastableandminimum-phaseapproximationof
the transfer function for a given logarithmic frequency response. For this aim we

9.4 UnstructuredUncertaintyModels 137
Fig.9.19 Approximationwithadditiveuncertainty
use20datapointsoftheupperbound,positioningthecursorusingamouse.Data
pointsareenteredbypressingtheleftmousebutton.
Asaresultweobtain
| Transfer | function:  |           |     |
| -------- | ---------- | --------- | --- |
| 0.0121   | s^2 + 11.4 | s + 56.95 |     |
---------------------------
| s^2 | + 36.25 s | + 283.7 |     |
| --- | --------- | ------- | --- |
Asadisadvantageofthismodelonemaynotethefactthattopresenttheuncer-
taintyinafirstordermodelitisnecessarytouseaweightedtransferfunctionofa
secondordersystem.
| ThefrequencyresponseofW |     | isalsoshowninFig.9.19. |     |
| ----------------------- | --- | ---------------------- | --- |
a
Themodelwithadditiveuncertaintyisobtainedbythecommandlines
| Delta_a  | = ultidyn(’Delta_a’,[1 |     | 1]); |
| -------- | ---------------------- | --- | ---- |
| G = Gnom | + Wa*Delta_a           |     |      |
InthegivencasethecomplexscalaruncertaintyΔ issetbythefunctionultidyn.
a

| 138 |     |     | 9 BuildingUncertainModels |
| --- | --- | --- | ------------------------- |
Fig.9.20 Plantwith
multiplicativeuncertainty
9.4.2 ModelswithMultiplicativeUncertainty
ThefollowingexampleillustrateshowtoobtainamodelofSISOplantwithmulti-
plicativeuncertainty.
| Example9.7 | ConsidertheuncertainplantpresentedinExample9.6. |     |     |
| ---------- | ----------------------------------------------- | --- | --- |
Themodelwithmultiplicativeuncertaintyischosenas
|     |        | (cid:4) | (cid:5)  |
| --- | ------ | ------- | -------- |
|     | G(s)=G | (s) 1+W | (s)Δ (s) |
|     |        | n       | m m      |
where
|     |     | (cid:18) (cid:18)   |     |
| --- | --- | ------------------- | --- |
|     |     | (cid:18) (cid:18)≤1 |     |
Δ (jω)
m
The block-diagram of the plant with multiplicative uncertainty is shown in
Fig.9.20.
Inthegivencaseweconstructthemagnitudefrequencyresponsesoftherelative
error
|     |     | |G(jω)−G | (jω)| |
| --- | --- | -------- | ----- |
n
|G (jω)|
n
whichisdonebythefollowingcommandlines:
| omega = | logspace(-1,3,100); |     |     |
| ------- | ------------------- | --- | --- |
%
| K0 = 1.0; | T0 = 1/15;         |     |     |
| --------- | ------------------ | --- | --- |
| Gnom =    | tf([K0],[T0 1]);   |     |     |
| Gnom_frd  | = frd(Gnom,omega); |     |     |
figure(1)
hold off
| for K = | 0.8*K0:0.08*K0:1.2*K0     |                       |     |
| ------- | ------------------------- | --------------------- | --- |
| for     | T = 0.7*T0:0.06*T0:1.3*T0 |                       |     |
|         | G = tf([K],[T             | 1]);                  |     |
|         | G_frd = frd(G,omega);     |                       |     |
|         | reldiff = (G_frd          | - Gnom_frd)/Gnom_frd; |     |
bodemag(reldiff,’c--’,omega)
|     | hold on |     |     |
| --- | ------- | --- | --- |
end
end
grid
| temp1 = | ’Approximation      | of uncertain  | transfer function’; |
| ------- | ------------------- | ------------- | ------------------- |
| temp2 = | ’ by multiplicative | uncertainty’; |                     |

9.4 UnstructuredUncertaintyModels 139
Fig.9.21 Approximationwithmultiplicativeuncertainty
title([temp1 temp2]);
legend(’|Wm(j\omega)|’,...
’|(G(j\omega)-G_{nom}(j\omega))/G_{nom}(j\omega)|’,3)
ThefrequencyresponsesobtainedareshowninFig.9.21.
Since
|G(jω)−G
n
(jω)|
≤
(cid:18)
(cid:18) W (jω)
(cid:18)
(cid:18)
|G (jω)| m
n
determiningW (jω)isequivalenttofindingoftheupperboundofthemagnitude
m
responseofrelativeerror.Thisisdonebythecommands
ord = 1;
wfit
Wm = Wtf
using again the file wfit.m with approximation order equal to 1. After execut-
ingthesecommandswefindastable,minimum-phaseapproximationoftheupper
bound:
Transfer function:
0.7351 s + 4.288
----------------
s + 20.65
ThefrequencyresponseofW isshowninFig.9.21.
m

| 140 |     |     | 9 BuildingUncertainModels |     |
| --- | --- | --- | ------------------------- | --- |
Fig.9.22 Frequencyresponsesoftheuncertainmodel
Obtainingthemodelwithmultiplicativeuncertaintyisdonebythecommands
| Delta_m     | = ultidyn(’Delta_m’,[1 |     | 1]); |     |
| ----------- | ---------------------- | --- | ---- | --- |
| G = Gnom*(1 | + Wm*Delta_m)          |     |      |     |
whichresultsinsecondorderuncertainstate-spacemodel
| USS: 2   | States, 1 | Output, 1 | Input, Continuous | System |
| -------- | --------- | --------- | ----------------- | ------ |
| Delta_m: | 1x1 LTI,  | max. gain | = 1, 1 occurrence |        |
thefrequencyresponsesoftheuncertainmodelareobtainedbythecommandline
bode(Gnom,’r--’,G,’b-’,omega)
andareshowninFig.9.22.
9.4.3 UnmodeledDynamics
Considerthesetofplants
|     |     | G(s)=G | (s)f(s) |     |
| --- | --- | ------ | ------- | --- |
n
whereG (s)isafixed(andknown)transferfunction.Wedesiretoneglecttheterm
n
f(s)(whichmaybeafixedtransferfunctionorbelongstoanuncertaintyset)andto
representG(s)bymultiplicativeuncertaintywithanominalmodelG intheform
|     |        | (cid:6) | (cid:7)      | n   |
| --- | ------ | ------- | ------------ | --- |
|     | G(s)=G | 1+W     |              |     |
|     |        | n (s)   | m (s)Δ m (s) |     |
(jω)≤1.
whereΔ
m

9.4 UnstructuredUncertaintyModels 141
Since
G(s)−G (s)
n =f(s)−1
G (s)
n
thenthemagnitudefrequencyresponseoftherelativeuncertaintyduetotheneglect
ofthedynamicsoff(s),is
|G−G
n
|
=
(cid:18)
(cid:18) f(jω)−1
(cid:18)
(cid:18)
|G |
n
Fromthisexpressiononeobtainsthat
(cid:18) (cid:18)
(cid:18)
(cid:18) W m (jω)
(cid:18)
(cid:18)=max
(cid:18)
(cid:18) (cid:18)
G−G
n
(cid:18)
(cid:18) (cid:18) =max
(cid:18)
(cid:18) f(jω)−1
(cid:18)
(cid:18)
G
n
This procedure is illustrated by the following example, in which the neglect time
delayisrepresentedbyamultiplicativeuncertainty.
Example9.8 GivenistheplantG=G (s)e −τs,where0≤τ ≤0.1andG (s)does
n n
notdependonτ.Ourdesireistorepresenttheplantbyamultiplicativeuncertainty
andnominalmodelG (s).Forthisaimfirstwecomputethemagnituderesponseof
n
therelativeerror
$
(cid:18) (cid:18) (cid:18) (cid:18) (cid:6) (cid:7)
(cid:18) f(jω)−1 (cid:18)=(cid:18) e −jωτ −1 (cid:18)= cos(ωτ)−1 2+sin(ωτ)2
forvaluesofτ between0and0.1.Thisisdonebythecommands
omega = logspace(-1,3,200);
figure(1)
hold off
for tau = 0:0.01:0.1;
for i = 1:200
om = omega(i);
pert(i) = sqrt((cos(om*tau)-1)^2 + sin(om*tau)^2);
end
magg = frd(pert,omega);
bodemag(magg,’c--’)
hold on
end
grid
temp1 = ’Approximation of uncertain time delay’;
temp2 = ’ by multiplicative uncertainty’;
title([temp1 temp2])
legend(’|Wm(j\omega)|’, ...
’|(G(j\omega)-G_{nom}(j\omega))/G_{nom}(j\omega)|’,2)
The frequency responses obtained are shown in Fig. 9.23. After that we find a
stable and minimum-phase approximation of the multiplicative uncertainty as in
Example9.7usingthecommands
ord = 2;
wfit
Wm = Wtf

142 9 BuildingUncertainModels
Fig.9.23 Approximationofuncertaintimedelay
Asaresult,fortheweightingtransferfunctionW (s)weobtain
m
Transfer function:
2 s^2 + 54 s + 1.1
------------------
s^2 + 37 s + 485
9.4.4 MultivariablePlantswithUnstructured Uncertainty
Obtainingmodelsofmultivariableplantswithunstructureduncertaintymaybedone
usingthemethodsconsideredpreviouslyinthissection,findingforeachelementof
thetransferfunctionmatrixSISOmodelwithadditiveormultiplicativeuncertainty.
Thescalarmodelsobtainedarethencombinedinatransfermatrixinordertodeter-
minetheuncertaintymodelofthemultivariableplant.
Consider for example the model of two-input, two-output uncertain plant with
transferfunctionmatrix
(cid:2) (cid:3)
g g
G= 11 12
g g
21 22
where g , g , g , g are scalar transfer function containing uncertainty. These
11 12 21 22
transferfunctionsarerepresentedbythecorrespondingmodelsapproximatingsep-
aratelythemaximumerrorofeachelement.

9.5 Exercises 143
Ifeachelementisrepresentedbymultiplicativeuncertaintymodel,themodelof
thewholesystemisobtainedas
(cid:2) (cid:3)
|     | (1+W  |                 | (1+W      |
| --- | ----- | --------------- | --------- |
|     | g n11 | 11 Δ 11 ) g n12 | 12 Δ 12 ) |
G=
|     | g (1+W | Δ ) g     | (1+W Δ ) |
| --- | ------ | --------- | -------- |
|     | n21    | 21 11 n22 | 22 22    |
where g n11 , g n12 , g n21 , g n22 are nominal transfer functions, W 11 , W 12 , W 21 , W 22
are the weighting functions obtainedafter approximationand Δ , Δ , Δ , Δ
11 12 21 22
arecomplexscalaruncertaintiesofclassultidyn.
Notethattheuncertaintyinmodelobtainedischaracterizedbyacertainstructure
independentlyonthefactthatintheindividualelementstheuncertaintyisunstruc-
tured.
Finally, it is necessary to point out that models with mixed uncertainty (struc-
tured and unstructured) may be created form the corresponding objects by using
interconnectorsysicfunctions.
9.5 Exercises
Exercise9.1 Foratwo-channelsystemwithplantandcontrollertransfermatrices
|     | (cid:30) | (cid:31) | (cid:30) (cid:31) |
| --- | -------- | -------- | ----------------- |
|     | 1        | 0        | s − 1             |
|     | s−       |          | + 1               |
| G=  | 1        | , K=     | s 1               |
|     | 0        | 1        | 0 1               |
s+1
obtainthesensitivitymatricesS ,S ,complementarysensitivitymatricesT ,T and
i o i o
loop transfer matrices L , L and compute the singular value plots of the corre-
i o
spondingfrequencyresponses.
Exercise9.2 Forthesystemwithplantandcontrollertransfermatrices
| (cid:30) |     |     | (cid:31) |
| -------- | --- | --- | -------- |
−0.08
|     | 2              | 0.02   |        |
| --- | -------------- | ------ | ------ |
|     | 0.015s2+0.8s+1 | 0.3s+1 | 0.4s+1 |
G=
|     | 0.04   | 1             | −0.03 |
| --- | ------ | ------------- | ----- |
|     | 0.1s+1 | 0.04s2+1.2s+1 | s+1   |
| ⎡   |        | ⎤             |       |
20(0.3s+1)
0
| ⎢   | 0.1s+1 | ⎥               |     |
| --- | ------ | --------------- | --- |
| K=⎢ |        | 30 (0 .5 s+ 1)⎥ |     |
| ⎣   | 0      | s+ ⎦            |     |
0 .2 1
|     | s+1    | −0.4   |     |
| --- | ------ | ------ | --- |
|     | 0.2s+1 | 0.5s+1 |     |
obtaintheclosed-looptransientresponsesduetostepreferencer andstepinputand
outputdisturbancesd i ,d.
Exercise9.3 Forthesysteminthepreviousproblemanalyzetheinfluenceofcon-
troller elements K and K gains on the closed-loop frequency responses and
11 22
transient responses. What is the influence of these gains on the magnitude of the
steady-stateerrorsinbothchannels?

| 144                                           |     |     | 9 BuildingUncertainModels |     |
| --------------------------------------------- | --- | --- | ------------------------- | --- |
| Exercise9.4 Buildanuncertainmodelforthesystem |     |     |                           |     |
(cid:30) (cid:31)
K
10s+1
G=
1
Ts+1
where the nominal values of the parameters K, T are 5 and 0.5, respectively, and
| theuncertaintyinK                                           | is±30%,andinT—±10%. |          |     |     |
| ----------------------------------------------------------- | ------------------- | -------- | --- | --- |
| Exercise9.5 Forthesystem,describedbythedifferentialequation |                     |          |     |     |
|                                                             | a x¨+2a x˙+a        | x=b u˙+b | u   |     |
|                                                             | 0 0                 | 1 0      | 1   |     |
wherethenominalvaluesoftheparametersa ,a ,b ,b are0.9,2,0.2,1,respec-
|     |     | 0 1 | 0 1 |     |
| --- | --- | --- | --- | --- |
tively,andallparametershaveuncertaintyof±30%,buildanuncertainstate-space
| model(classuss).Notetherepeatedparametera        |     | 0   | .   |     |
| ------------------------------------------------ | --- | --- | --- | --- |
| Exercise9.6 FortheSISOsystemwithtransferfunction |     |     |     |     |
K
W(s)=
T2s2+2ξTs+1
[10,12], [0.1,0.15]
| where K changes | in the range | T changes | in the range | and |
| --------------- | ------------ | --------- | ------------ | --- |
ξ changesintherange[0.3,0.4],findamodelwithadditiveuncertainty.
Exercise 9.7 For the system from the previous exercise find a model with multi-
plicativeuncertainty.
Exercise9.8 Forthetwo-channelplantwithnominaltransferfunctionmatrix
|     | (cid:30) |     | (cid:31) |     |
| --- | -------- | --- | -------- | --- |
10 1
s+1
|     | G(s)= s2+0.4s+16 |     |     |     |
| --- | ---------------- | --- | --- | --- |
1 5
s+2 (s+2)(s+3)
anduncertaindelaysinthefirstandsecondinputintherange[0,0.2],findamodel
withunstructureduncertainty.

Chapter 10
Robust Stability and Performance
Thischapterisdevotedtotheimportantsubjectofrobuststabilityandrobustperfor-
manceanalysisusingMATLAB®.Firstweshowhowtoimplementfunctionsfrom
RobustControlToolbox®3toanalyzetherobuststabilityofsystemswithunstruc-
tured, structured and mixed uncertainty. Then we consider the implementation of
the function robustperf to analyzethe robust performanceof closed-loopsys-
tems and show how to interpret the results obtained by this function. Similarly to
robuststabilitymargin,weusethenotionofperformancemarginthatshowstheun-
certainty level, up to which the system possess specified performance. Finally, we
considerhowtodeterminethesocalled“worst-case”gain,whichisdeterminedas
thelargestvalueofthefrequencyresponsemaximumforthealloweduncertainty.
10.1 Robust StabilityAnalysis
For the aim of robust stability analysis, it is convenient to represent the uncertain
controlsystembytheM–Δloop,showninFig.10.1.Inthisloopthetransferfunc-
tionofthenominalpart(denotedby M)isseparatedfromuncertainpart(denoted
by Δ). In the simpler case of unstructured Δ it is possible to use the small-gain
theorem (see Sect. 3.1 of Part I). In the general case of structured Δ(s) the robust
stabilityanalysisisdonebyusingthestructuredsingularvalueμ,(seeSect.3.3of
PartI).
Exceptsomesimplecases,thestructuredsingularvalueμ,whichisafrequency
function, cannot be computed exactly. However, there exist efficient algorithms to
determine upper and lower bounds of μ. That is why the conclusions about sys-
temrobuststabilityshouldbedrawnintermsofthesebounds.Specifically,letthe
maximumsalongfrequencyoftheupperandlowerboundofthestructuredsingular
valuesbedenotedrespectivelybyβ andβ .Then
u l
• The uncertainsystemunder considerationis guaranteedstable for all structured
uncertainmatricesΔwith(cid:5)Δ(s)(cid:5) ∞<1/β
u
.
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 145
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_10,©Springer-VerlagLondon2013

| 146 |     |     | 10 RobustStabilityandPerformance |     |
| --- | --- | --- | -------------------------------- | --- |
Fig.10.1 M–Δloopfor
robuststabilityanalysis
| •   |     |     | (cid:5)Δ(s)(cid:5) | =1/β |
| --- | --- | --- | ------------------ | ---- |
There exists a specific structured transfer matrix Δ with ∞ l that
destabilizesthesystem.
Inaddition,forthecaseofnormalizeduncertainty
(cid:5)Δ(cid:5) ≤1
∞
itfollowsthat
• Ifβ <1,thesystemisrobustlystablewithrespecttothemodeleduncertainty.
u
•
Ifβ l >1,therobuststabilityisnotachieved.
• Ifβ <1andβ >1,itisnotpossibletodrawwithcertaintyaconclusionabout
| l   | u   |     |     |     |
| --- | --- | --- | --- | --- |
stability;itispossiblethatthesystemisnotrobustlystable.
ThemaintoolinRobustControlToolbox®3forrobuststabilityanalysis,based
on computing of structured singular value, is the command robuststab. This
commandmaybeusedforstabilityanalysisofsystemswithunstructured,structured
ormixeduncertainty.Thecommandrobuststabdoesnotrequirethesystemto
bepresentedinsomespecialform(forinstance,asanM–Δloop).Itssyntaxis
| [stabmarg,destabunc,report]      |     | = robuststab(sys,opt) |                       |     |
| -------------------------------- | --- | --------------------- | --------------------- | --- |
| [stabmarg,destabunc,report,info] |     |                       | = robuststab(sys,opt) |     |
Inputarguments:
– sys:modeloftheuncertainsystemunderinvestigation,maybeofclassussor
| classufrd. | sys classuss, |                     |     |                    |
| ---------- | ------------- | ------------------- | --- | ------------------ |
| of         | If is of      | the computationsare |     | done for appropri- |
ately chosen by the command robuststab frequency values. If it is of class
ufrd,theassociatedwithsysfrequencyvectorisused;
– opt:optionalinputarguments.Itrepresentsanobject,createdbythecommand
| opt = robopt(’name1’,value1,’name2’,value2,...). |     |     |     | Some of |
| ------------------------------------------------ | --- | --- | --- | ------- |
themostfrequentlyusedpropertiesare
•
Display:displaysprogressofcomputations;defaultis’off’;
• Sensitivity:computestheinfluenceofindividualuncertaintiesonthesta-
bilitymargin;defaultis’on’.
Outputarguments:
– stabmarg:structurewiththefollowingfields:
•
UpperBound:upperboundonstabilitymargin;
• LowerBound:lowerboundonstabilitymargin;
• DestabilizingFrequency:
|     |     | frequency | at which system | instability oc- |
| --- | --- | --------- | --------------- | --------------- |
curs.Correspondstotheupperboundofstabilitymargin;

10.1 RobustStabilityAnalysis 147
– destabunc:structurecontainingacombinationofuncertainparametervalues
closest to their nominal values that cause system instability—it corresponds to
theupperboundofstabilitymargin;
– report:variablecontainingtextdescriptionofrobustnessanalysisresults;
– info:structurewithseveralfields:
• Frequency:frequencyvectorusedinthecomputations;
• MussvBnds:frdobjectcontainingthecomputedvaluesoftheupperbound
(MussvBnds(1,1)) and lower bound (MussvBnds(1,2)) of the struc-
turedsingularvalue;
• Sensitivity: structure with number of fields equal to the number of un-
certain elements. In each field is stored a number, indicating the influence of
thecorrespondinguncertainelementonthestabilitymargin.Forinstance,the
number40meansthatiftheuncertaintyrangeisincreasedwith25%,thesta-
bilitymarginwilldecrease10%(25%of40).
Consider in some detail how to interpret the results obtained by command
robuststab. If the uncertain system sys is of class uss, the command
robuststab checks the stability of the nominal system. In case the system is
unstable, to UpperBound and to LowerBound is assigned the value −∞. If,
however,sysisofclassufrd,suchacheckisnotdoneassumingthatthenominal
systemisstable.
Therobuststabilityanalysisdonebythecommandrobuststabisbasedonthe
computationofboundsonthestructuredsingularvalue,decomposingtheuncertain
systembeforethatintoM–Δformwith(cid:5)Δ(s)(cid:5)
∞
≤1,i.e.,theresultsfromanalysis
pertaintonormalizeduncertainty.
Theresultsofstabilityanalysisareobtainedintermsofupperandlowerbounds
ofthestabilitymargin.Rememberthatinthegivencasethestabilitymarginisde-
fined as the reciprocal value of the maximum of structured singular values with
respect to the frequency. Hence, the upper bound of stability margin is equal to
the reciprocal value of the maximum along frequency of the lower bound of the
structured singular value (i.e., UpperBound=1/β ) and the lower bound of the
l
stabilitymarginisobtainedinthesamewayfromtheupperboundofthestructured
singularvalue(LowerBound=1/β ).
u
Takingintoaccountthestabilityconditions,derivedbytheboundsofstructured
singularvalue,itispossibletodrawthefollowingconclusions.
• IfLowerBound>1,theuncertainsystemisrobustlystablewithrespecttomod-
eleduncertainty.
• IfUpperBound<1,thesystemdoesnotachieverobuststability.
• IfLowerBound<1andUpperBound>1,itisnotpossibletodrawadefinite
conclusionaboutstability;thesystemmaynotberobustlystable.
LetforinstanceLowerBound=1.2andUpperBound=1.3.Apartfromthe
factthatthesystemisrobustlystableforthegivenuncertaintylevel,inthiscaseit
isguaranteedthat
• Thesystemremainsstableforuncertaintylevelssmallerthan120%ofthegiven
one.

148 10 RobustStabilityandPerformance
• Thereexistatleastonecollectionofuncertaintyvalueswithlevel130%of the
givenonewhichcausesinstability.(Oneofthesedestabilizingsetsisincludedin
thestructuredestabunc.)
Apart by robuststab, the robust stability analysis may be done also by the
commandmussvwhichcalculatesupperandlowerboundonthestructuredsingu-
larvaluesμ (M)asafunctionoffrequency.Inordertoimplementthiscommand,
Δ
theuncertainsystemshouldbedecomposedinanM–Δloop(Fig.10.1)withnor-
malizeduncertainty(cid:5)Δ(s)(cid:5)
∞
≤1.Thebasicsyntaxofmussvis
bounds = mussv(M,BlkStructure)
Descriptionofarguments:
– M:modeloftheknownpartoftheuncertainsystemthatmaybeofclassfrd(this
is usual in implementing the function mussv) or a complex matrix. If it is of
classfrd,thestructuredsingularvalueboundsarecalculatedfortheassociated
withMfrequencyvector;
– BlkStructure: inputargument,specifyingtheblock-structure of theuncer-
tainty matrix Δ(s). It represents a matrix with two columns and as many rows
asthenumberofuncertainsystemblocks.Eachrowcontainsinformationwhich
specifiesthecorrespondinguncertaintyblock.
• Scalar real parameter (uncertain element of class ureal) is described by
[-1 0],andntimesrepeatedscalarrealparameter—by[-n 0];
• Scalar complex block (1×1 element of class ultidyn or element of class
ucomplex)issetby[1 0],andntimesrepeatedelement—by[n 0];
• n×mfullcomplexblock(n×melementofclassultidyn)isspecifiedby
[n m].
– bounds:outputargument.IfMisofclassfrd,thenboundsisafrdobject,
containingthecomputedvaluesoftheupperbound(bounds(1,1))andlower
bound(bounds(1,2))ofthestructuredsingularvalueofMwithrespecttothe
uncertaintystructurespecifiedbyBlkStructure.
To represent the uncertain system in the form required by mussv one usually
implementsthefunctionlftdata,
[M,Delta,BlkStruct] = lftdata(sys)
which determines the M-Delta decomposition (with normalized uncertain ele-
ments)oftheuncertainsystemwithmodelsys.TheoutputargumentBlkStruct
describestheblock-diagonalstructureofDeltaanditisintheformthatallowsits
directuseasaninputargumentofthefunctionmussv(avoidinginthiswaytospec-
ifytheblock-structureoftheuncertainty,asalreadydescribed).Also,itisnecessary
totakeintoaccountthatintherobuststabilityanalysisitisnecessarytotakeonly
thepartofMthatisconnectedtoDelta.
Note that the functions lftdata and mussv are used by the command
robuststabthatfacilitatestherobuststabilityanalysis.
Thecommandsrobuststabandmussvmaybeimplementedintheanalysis
ofcontinuous-timeaswellasdiscrete-timesystems.Thetypeofthesystemisnot

10.1 RobustStabilityAnalysis 149
Fig.10.2 Magnituderesponsesofweightingfilters
necessary to be indicated by the user since this information is stored in uss and
ufrdmodels.
Example10.1 Considerafifthordertwochannelsystemwithtwoinputs,twoout-
putsandnominaltransferfunction
| (cid:30)         |     | (cid:31) |
| ---------------- | --- | -------- |
|                  | 6   | −0.05    |
| (0.9s+1)(0.1s+1) |     | 0.1s+1   |
G =
| nom | 0.07                     | 5   |
| --- | ------------------------ | --- |
|     | 0.3s+1 (1.8s−1)(0.06s+1) |     |
(ThistransferfunctionwasusedalreadyinExamples9.2and9.4.)Thesystemhas
an uncertainty at the first input that consists of 20 % error in the low-frequency
range, increases to 100 % at 35 rad/s, and reaches 1000 % in the high-frequency
range. The uncertainty at the second input is 25 % in the low-frequency range,
100 % at 40 rad/s and increases to 1000 % in the high-frequency range. These
uncertaintiesmayberepresentedasinputmultiplicativeuncertaintiesbyusingun-
certainultydinobjectsandappropriateweightingfilters,createdbythefunction
makeweight.
W1 = makeweight(0.20,35,10);
W2 = makeweight(0.25,40,10);
ThemagnituderesponsesofweightingfiltersareshowninFig.10.2.
Next, the model with input multiplicative uncertainty is obtained by the com-
mandlines

| 150 |     |     | 10 RobustStabilityandPerformance |     |
| --- | --- | --- | -------------------------------- | --- |
Fig.10.3 Closed-loopsystemwithinputmultiplicativeuncertainty
| Delta1 | = ultidyn(’Delta1’,[1 | 1]); |     |     |
| ------ | --------------------- | ---- | --- | --- |
| Delta2 | = ultidyn(’Delta2’,[1 | 1]); |     |     |
W = blkdiag(W1,W2);
| Delta            | = blkdiag(Delta1,Delta2); |     |     |     |
| ---------------- | ------------------------- | --- | --- | --- |
| G = Gnom*(eye(2) | + Delta*W)                |     |     |     |
Asaresultweobtainaneighthorderuncertainobject,
| USS: 8  | States, 2 Outputs, | 2 Inputs, | Continuous      | System |
| ------- | ------------------ | --------- | --------------- | ------ |
| Delta1: | 1x1 LTI, max.      | gain =    | 1, 1 occurrence |        |
| Delta2: | 1x1 LTI, max.      | gain =    | 1, 1 occurrence |        |
Therobuststabilityoftheclosed-loopsystemwillbeanalyzedforthecontroller
|     |     | ⎡      | ⎤    |     |
| --- | --- | ------ | ---- | --- |
|     |     | 2(s+1) | −s   |     |
|     |     | s      | 3s+1 |     |
|     | K=⎣ |        | ⎦    |     |
−5(s+1) 4(0.7s+1)
|     |     | 0.8s+1 | s   |     |
| --- | --- | ------ | --- | --- |
Theblock-diagramoftheclosed-loopsystemisshowninFig.10.3.
SincetheplanthasunstructureduncertaintiesΔ and Δ itisinstructivetosee
1 2
what result will produce the small gain theorem if we assume as unstructured the
plantuncertaintymatrix
|     |     | (cid:2) | (cid:3) |     |
| --- | --- | ------- | ------- | --- |
|     |     | Δ       | 0       |     |
Δ= 1
0 Δ
2
ForthisaimwepresentthesystemasanM–Δloop,showninFig.10.1with
|     | M=−W(I | +KG) −1KG=−WT |     |     |
| --- | ------ | ------------- | --- | --- |
i
where
|     |     | (cid:2) | (cid:3) |     |
| --- | --- | ------- | ------- | --- |
|     |     | W 1     | 0       |     |
W =
0 W
2
and T i is the input complementary sensitivity. Now according to the results pre-
sentedinSect.3.1ofPartI,theconditionforrobuststability,basedonsmall-gain
theorem,is
(cid:5)WT (cid:5) ∞<1
i

10.1 RobustStabilityAnalysis 151
Theinputsensitivityisdeterminedbythecommandlines
looptransfer = loopsens(G,K);
Ti = looptransfer.Ti;
The H ∞-norm of the transfer function matrix WT
i
(the nominal transfer function
matrixisusedinthecomputations)isdeterminedas
[PeakNorm,freq] = norm(W*Ti.Nominal,’inf’)
Asaresultoneobtains
PeakNorm =
1.2353
freq =
4.8763
This result shows that the closed-loop system does not achieve robust stability as-
sumingthattheuncertainmatrixΔisunstructured.However,thematrixΔactually
hasablock-diagonalstructurewhichaffectsverymuchtherobustnessoftheclosed-
loop system. Further on, taking into account the structure of Δ, we show that the
closed-loopsysteminfactachievesrobuststabilityevenforlargerinputmultiplica-
tiveuncertaintiesthanthegivenones.
The robust stability analysis is done by the function robuststab with input
argument the uncertain frequency response corresponding to the output comple-
mentarysensitivity.
omega = logspace(-1,2,200);
To_g = ufrd(To,omega);
opt = robopt(’Display’,’on’);
[stabmarg,destabunc,report,info] = robuststab(To_g,opt);
Asaresultweobtain
stabmarg =
UpperBound: 2.020374929266748
LowerBound: 2.020373919079788
DestabilizingFrequency: 3.696912707195026
Itfollowsthat
• forthegivenstructureandlevelofuncertaintytheclosed-loopsystemisrobustly
stable(thelowerboundofstabilitymarginsatisfiesLowerBound>1);
• thesystemremainsstableforuncertaintylevelssmallerthan202.03%fromthe
givenone;
• thereexistsuncertaintywithlevel202.03%fromthegivenonewhichdestabilizes
thesystem.

152 10 RobustStabilityandPerformance
Theseconclusionsabouttherobuststabilityofthesystemarecontainedinthevari-
able report. It contains also an information about the influence of the uncertain
elementsonthestabilitymargin.TheinfluenceoftheuncertaintyΔ isstronger.
2
report =
Assuming nominal UFRD system is stable ...
Uncertain System is robustly stable to modeled uncertainty.
-- It can tolerate up to 202% of the modeled uncertainty.
-- A destabilizing combination of 202% of the modeled
uncertainty exists, causing an instability at 3.7 rad/s.
-- Sensitivity with respect to uncertain element ...
’Delta1’ is 63%. Increasing ’Delta1’ by 25% leads
to a 16% decrease in the margin.
’Delta2’ is 90%. Increasing ’Delta2’ by 25% leads
to a 23% decrease in the margin.
Inthiswayweseethattakingintoaccounttheblock-diagonalstructureoftheuncer-
taintyΔwillleadustotheconclusionthattheclosed-loopsystemachievesrobust
stabilityasoppositetothecasewhenweassumedΔasunstructured.Thisconfirms
the well known fact that neglecting the uncertainty structure leads to pessimistic
conclusionsaboutthesystemstability.
Thecommandlines
destabunc.Delta1
destabunc.Delta2
producethestate-spacerealizationsoftheperturbationsΔ andΔ thatdestabilize
1 2
theclosed-loopsystem.Thecorrespondingtransferfunctionsare
tf(destabunc.Delta1)
Transfer function:
-10.56 s^2 + 14.35 s + 6.374e-015
---------------------------------
s^3 + 6.587 s^2 + 20.77 s + 18.57
and
tf(destabunc.Delta2)
Transfer function:
-10.56 s^2 + 9.88 s + 2.194e-015
---------------------------------
s^3 + 6.164 s^2 + 18.56 s + 12.78
IftheseperturbationsaresubstitutedinthetransferfunctionmatrixT itispossible
o
tofindthepolesoftheclosed-loopsystem:
pole(usubs(To,destabunc))

10.1 RobustStabilityAnalysis 153
Asaresultweobtain
ans =
1.0e+002 *
-4.117820048554725
-3.552895319158590
| -0.090818247953519 | + 0.087226740827892i |     |
| ------------------ | -------------------- | --- |
| -0.090818247953519 | - 0.087226740827892i |     |
-0.100000000000026
-0.088879355942136
| -0.021603036018368 | + 0.048364783432694i |     |
| ------------------ | -------------------- | --- |
| -0.021603036018368 | - 0.048364783432694i |     |
| 0.000000000000000  | + 0.036969127071950i |     |
| 0.000000000000000  | - 0.036969127071950i |     |
| -0.046004083820114 | + 0.016746382352412i |     |
| -0.046004083820114 | - 0.016746382352412i |     |
-0.033451309908770
| -0.003583579386419 | + 0.000780496584728i |     |
| ------------------ | -------------------- | --- |
| -0.003583579386419 | - 0.000780496584728i |     |
-0.010671435327352
-0.009480508626777
-0.006893138594670
Weseethatthedestabilizingpoleswhichcorrespondtothedestabilizingperturba-
tionsare±j3.697.InFig.10.4weshowthefrequencyresponsesoftheupperand
lowerboundsofthestructuredsingularvalueμobtainedbythecommandlines
semilogx(info.MussvBnds(1,1),’r-’,info.MussvBnds(1,2),
’b--’)
grid
| title(’Robust stability’) |           |     |
| ------------------------- | --------- | --- |
| xlabel(’Frequency         | (rad/s)’) |     |
ylabel(’mu’)
| legend(’\mu-upper | bound’,’\mu-lower | bound’,2) |
| ----------------- | ----------------- | --------- |
Consider now the robust stability of the given system by using the command
mussv. For this aim we decompose the output sensitivity function T into M–Δ
o
loop.
[M,Delta,BlockStructure] = lftdata(To);
TodothestabilityanalysisitisnecessarytotakeonlythepartofMthatisconnected
toΔ,
| size_Delta = size(Delta); |     |     |
| ------------------------- | --- | --- |
M11 = M(1:size_Delta(2),1:size_Delta(1));

154 10 RobustStabilityandPerformance
Fig.10.4 Robuststability
The frequency response of M11 is determined for the frequency vector used by
robuststab:
omega = info.Frequency;
M11_g = frd(M11,omega);
Now we are in position to calculate the upper and lower bounds on μ using the
functionmussv.
rbounds = mussv(M11_g,BlockStructure);
The bounds obtained are the same as the bounds determined in case of using the
functionrobuststabthatareshowninFig.10.4.
10.2 Robust PerformanceAnalysis
For the aim of robust performance analysis the closed-loop system is represented
by the block-diagram, shown in Fig. 10.5. The known system part M includes
the model of the nominal control system, weighting functions to represent the un-
certainty and weighting functions used to specify performance requirements. The
unknown part represents a set of transfer function matrices Δ with given block-
diagonal structure, corresponding to the uncertainty structure of the system under
consideration.Theinputvectorvcontainsallexogenoussignalstothesystem:refer-
ences,disturbances,andsensornoises.Theoutputvectorzincludessignalshaving

10.2 RobustPerformanceAnalysis 155
Fig.10.5 Block-diagramfor
robustperformanceanalysis
the meaning of “errors” which characterize the system performance: for instance,
theweighted(byweightingtransferfunctions)trackingerrors,controlactionsand
soon.
LetT (s)denotesthetransferfunctionmatrixfromv toz.Itisappropriateasa
zv
systemperformanceindextousethequantity
(cid:24) (cid:24)
(cid:24) (cid:24)
T (s) (10.1)
zv ∞
Smallervaluesofthisindexmeanssmaller“errors”zduetothe“worst”inputsig-
nalsvandhencebettersystemperformance.
Theproblemof robustperformanceanalysismaybereducedtotheproblemof
robust stability analysis of the closed-loop which consists of the block M and the
extendeduncertaintyblock
(cid:2) (cid:3)
Δ 0
Δ = (10.2)
P 0 Δ
F
In(10.2)Δ isafictitiouscomplex(unstructured)uncertainblockwithsizen ×n
F v z
wheren andn arethesizeofvectorsvandz,respectively.Therobustperformance
v z
analysis of the system is done by using the structured singular value of M with
respecttotheextendeduncertaintyΔ (seeSect.6.1ofPartI).
P
Since it is only possible to calculate upper and lower bounds of the structured
singular value, the conclusions about robust performance should be drawn on the
basis of these bounds. Let the maxima with respect to the frequency of the upper
and lower bounds of the structured singular value μ (M) be denoted by β and
ΔP u
β ,respectively.Then
l
• ForalluncertaintymatricesΔwiththegivenstructuresatisfying(cid:5)Δ(cid:5) ∞<1/β
u
,
theclosed-loopsystemisstableand(cid:5)T zv (s)(cid:5) ∞ ≤β u .
• ThereexistsaspecificmatrixΔwiththegivenstructuresatisfying(cid:5)Δ(cid:5)
∞
=1/β
l
forwhicheither(cid:5)T zv (s)(cid:5) ∞ ≥β l orthesystemisunstable.
Customary, the weighting transfer functions, used to specify the performance
requirements,arechosensothatwhenthecondition
(cid:24) (cid:24)
(cid:24) (cid:24)
T (s) <1 (10.3)
zv ∞
isfulfilled,thecontrolsystemhasthedesiredperformance.
It is said that a given uncertain system achieves robust performance if for the
uncertaintyallowedthesystemisstableandcondition(10.3)issatisfied.

156 10 RobustStabilityandPerformance
Fig.10.6 Robustperformancemargin
Foraperformancerequirement(10.3)andnormalizeduncertainty
(cid:5)Δ(cid:5)
∞
≤1
thefollowingconclusionshold.
• If β <1 the system achieves robust performance for the modeled uncertainty
u
(thisincludesalsorobuststability).
• Ifβ >1therobustperformanceisnotachieved.
l
Clearly, if β <1 and β >1 it is not possible to draw a definite conclusion
l u
whetherthesystemachievesrobustperformance.
In the analysis of robust performance, similarly to robust stability margin, one
may introduce the notion of performance margin. It shows the uncertainty level,
uptowhichthesystempossessesspecifiedperformance.Theperformancemargin
pm is equal to the reciprocal value of the maximum with respect to frequency of
thestructuredsingularvalueμ (M),i.e.,pm=1/β.Theupperboundpm and
ΔP u
lowerboundpm ofthestabilitymarginareobtainedbyβ andβ ,respectively:
l l u
1 1
pm = , pm =
u l
β β
l u
Determination of performance margin is illustrated in Fig. 10.6. In the figure, an
exemplary performance degradation curve of uncertain control system is shown.
With increasing the size of uncertainty, the value of performance index increases

10.2 RobustPerformanceAnalysis 157
monotonicallyandforaspecificuncertaintylevelthesystemlosesstability.Given
are also the upper bound and lower bound of the performance degradation curve
thatare obtainedbyusing thestructured singularvalue.The pointsof intersection
ofthesecurveswiththehyperboley=1/xhaveabscissasequaltotheperformance
marginpmanditsboundspm andpm ,andordinatesβ,β andβ ,respectively.
l u u l
The robust performance analysis is done by the command robustperf. The
resultsofthiscommandareobtainedintermsoftheupperandlowerboundsofthe
performancemargin.Thesyntaxofthiscommand,theinputandoutputarguments
aresimilartothecommandrobuststabforrobuststabilityanalysis.
[perfmarg,perfmargunc,report] = robustperf(sys,opt)
[perfmarg,perfmargunc,report,info] = robustperf(sys,opt)
Inputarguments.
– sys:modeloftheuncertainsystem(extendedbytheweightingtransferfunctions
used to specify the performance requirements, i.e., T (s)). If sys is of class
zv
uss,thecomputationsaredoneforfrequencyvaluesappropriatelychosenbythe
functionrobustperf.Ifitisofclassufrd,theassociatedwithsysfrequency
vectorisused.Thesystemmaybeeithercontinuous-timeordiscrete-time;
– opt:optionalinputargumentcreatedbycommandroboptinthesamewayas
forrobuststab.
Outputarguments.
– perfmarg:structurewiththefollowingfields.
• UpperBound:upperboundofperformancemargin;
• LowerBound:lowerboundofperformancemargin;
• CriticalFrequency: frequency value corresponding to the upper bound
ofperformancemargin;
– perfmargunc:acombinationofuncertainelementvaluescorrespondingtoup-
perboundofperformancemargin;
– report:chararraywithtextdescriptionoftheresultsfromrobustperformance
analysis;
– info:structurewithseveralfields.
• Frequency:frequencyvectorusedinthecomputations;
• MussvBnds:frdobjectcontainingthecomputedvaluesoftheupperbound
(MussvBnds(1,1)) and lower bound (MussvBnds(1,2)) of the struc-
turedsingularvaluecorrespondingtothecaseofrobustperformance;
• Sensitivity: structure containing information for the influence of uncer-
tainelementsontheperformancemargin.
The robust performance analysis by the command robustperf is based on
the calculation of the structured singular value bounds determined for normalized
uncertainty(cid:5)Δ(s)(cid:5)
∞
≤1.
Letforinstancetheperformancemarginboundsare LowerBound=1.25 and
UpperBound=1.30. In this case it is guaranteed that for uncertainty level less
than125%ofthegivenone(i.e.,1.25normalizedunits),theclosed-loopsystemis

158 10 RobustStabilityandPerformance
stableandthevalueofperformanceindex(H
∞-normofsys)islessorequalto0.8.
Also, there exists at least one combination of uncertainty values with level 130 %
ofthegivenone,forwhicheithertheperformanceindexisgreaterorequalto0.769
(i.e., 1/1.30) or the closed-loop system is unstable. (One of these combinations is
includedinthestructureperfmargunc.)
For a performance requirement (10.3) one may derive the following conclu-
sions:ifLowerBound>1,thesystemachievesrobustperformanceforthemod-
eled uncertainty; if UpperBound<1 the robust performance is not achieved; if
LowerBound<1 and UpperBound>1 it is not possible to draw conclusions
withcertainty.
Inadditiontorobustperf,therobustperformanceanalysismaybedonecom-
putingwiththecommandmussvtheupperandlowerboundofthestructuredsin-
gular value μ (M) as a function of frequency. This approach, however, is not
ΔP
recommended.
Example10.2 ConsiderthecontrolsystemdescribedinExample10.1andletGde-
notestheplanttransferfunctionmatrixandK—thecontrollertransferfunctionma-
trix.Lettherequirementstosystemperformancearetoensurereference(r)tracking
withadmissibleerror(e)andlimitedcontrol(u)magnitudeinthepresenceofdis-
turbance d. According to the first requirement, the output sensitivity function S
o
e r d
connecting with and shouldbesufficientlysmallinthelow-frequencyrange
(r andd arelow-frequencysignals).Accordingtothesecondrequirementthetrans-
ferfunctionmatrixKS connectinguwithr andd shouldbesufficientlysmall.To
o
takeintoaccountbothrequirementsitisappropriatetouseasasystemperformance
indexthequantity
| (cid:24)(cid:2) | (cid:3)(cid:24) |        |
| --------------- | --------------- | ------ |
| (cid:24)        | (cid:24)        |        |
| (cid:24) W      | p S o (cid:24)  |        |
| (cid:24)        | (cid:24)        | (10.4) |
W KS
| u   | o ∞ |     |
| --- | --- | --- |
whereW p andW u areweightingtransferfunctionmatrices.Let
(cid:2) (cid:3)
0.04(s+10)
w 0
| W = p , | w =         |     |
| ------- | ----------- | --- |
| p 0 w   | p (s+0.005) |     |
p
and
(cid:2) (cid:3)
−2(0.01s+1)
| w 0     | 4.0.10 |     |
| ------- | ------ | --- |
| W = u , | w =    |     |
u u (0.005s+1)
0 w u
arechosensothatwhenthecondition
| (cid:24)(cid:2) | (cid:3)(cid:24) |        |
| --------------- | --------------- | ------ |
| (cid:24)        | (cid:24)        |        |
| (cid:24) W S    | (cid:24)        |        |
| (cid:24) p      | o (cid:24) <1   | (10.5) |
W KS
| u   | o ∞ |     |
| --- | --- | --- |
is fulfilled, the control system has desired performance, i.e., desired accuracy of
referencetrackingandlimitedmagnitudeofcontrolactionareachieved.
Theproblemistoanalyzethesystemrobustperformancetakingintoaccountthe
plantuncertainty.

10.2 RobustPerformanceAnalysis 159
Fig.10.7 Block-diagramoftheclosed-loopsystemwithperformancerequirements
Theblock-diagramoftheclosed-loopsystemincludingtheweightingfunctions
| W andW | isshowninFig.10.7.Inthegivencase |     |     |
| ------ | -------------------------------- | --- | --- |
| p      | u                                |     |     |
(cid:2) (cid:3)
W p S o
T =
|     |     | zv  | W KS |
| --- | --- | --- | ---- |
u o
the output vector z containing the weighted “errors” and the input vector v being
thedifferencev=r−d.
Thesystemmodelisbuiltbythecommandsysicsavingthetransferfunction
| matrixT      | zv (s)intothevariableclpofclassuss: |     |         |
| ------------ | ----------------------------------- | --- | ------- |
| wp = 0.04*(s | + 10)/(s                            | +   | 0.005); |
Wp = blkdiag(wp,wp);
wu = 4.0*10^(-2)*(0.01*s+1)/(0.005*s+1);
Wu = blkdiag(wu,wu);
| systemnames | = ’          | G K Wp Wu  | ’;  |
| ----------- | ------------ | ---------- | --- |
| inputvar    | = ’[ ref{2}; | dist{2}    | ]’; |
| outputvar   | = ’[ Wp;     | Wu ]’;     |     |
| input_to_G  | = ’[         | K ]’;      |     |
| input_to_K  | = ’[         | ref-G-dist | ]’; |
| input_to_Wp | = ’[         | ref-G-dist | ]’; |
| input_to_Wu | = ’[         | K ]’;      |     |
clp = sysic;
Forthesystemwithnominalplantmodel
norm(clp.Nom,’inf’)
ans =
0.8081
condition(10.5)issatisfiedandhencetheclosed-loopsystemachievesnominalper-
formance.

| 160 |     |     |     |     |     | 10 RobustStabilityandPerformance |     |     |
| --- | --- | --- | --- | --- | --- | -------------------------------- | --- | --- |
Thesystemrobustperformanceisanalyzedbythecommandrobustperfset-
tingappropriatefrequencyvector:
| omega = | logspace(-1,2,200); |     |     |     |     |     |     |     |
| ------- | ------------------- | --- | --- | --- | --- | --- | --- | --- |
| clp_g = | ufrd(clp,omega);    |     |     |     |     |     |     |     |
opt = robopt(’Display’,’on’);
| [perfmarg,perfmargunc,report,info] |     |     |     |     | =   | robustperf(clp_g,opt) |     |     |
| ---------------------------------- | --- | --- | --- | --- | --- | --------------------- | --- | --- |
Asaresultoneobtains
| perfmarg           | =   |             |     |                    |     |     |     |     |
| ------------------ | --- | ----------- | --- | ------------------ | --- | --- | --- | --- |
|                    |     | UpperBound: |     | 1.007341638920202  |     |     |     |     |
|                    |     | LowerBound: |     | 1.007047914437433  |     |     |     |     |
| CriticalFrequency: |     |             |     | 15.885651294280526 |     |     |     |     |
SinceLowerBound>1theperformancerequirement(10.5)issatisfiedforthe
givenuncertainty,i.e.,thesystemachievesrobustperformance.
Itfollowsfromtheresultobtainedthatforuncertaintylevelslessthan100.70%
of the givenone the value of the performanceindex(10.4) is less than or equalto
1/1.0070=0.9930.
Also, the analysis gives a combination of uncertainties with level 100.73 % of
1/1.0073=
| thegivenoneforwhichthevalueof(10.4)is |     |     |     |     | greaterthanorequalto |     |     |     |
| ------------------------------------- | --- | --- | --- | --- | -------------------- | --- | --- | --- |
0.9928.
Partoftheconclusionsdrawnaboutthesystemrobustperformancearecontained
in the variable report. It contains also information about the influence of the
uncertain elements on the performance margin. The influence of the uncertainty
Δ isstronger:
2
| report    | =      |          |     |          |             |     |        |     |
| --------- | ------ | -------- | --- | -------- | ----------- | --- | ------ | --- |
| Uncertain | System | achieves |     | a robust | performance |     | margin | of  |
1.007.
| -- A model     |     | uncertainty    | exists     |         | of size      | 101%    | resulting | in a    |
| -------------- | --- | -------------- | ---------- | ------- | ------------ | ------- | --------- | ------- |
| performance    |     | margin         | of         | 0.993   | at 15.9      | rad/s.  |           |         |
| causing        |     | an instability |            | at 15.9 | rad/s.       |         |           |         |
| -- Sensitivity |     | with           | respect    | to      | uncertain    | element | ...       |         |
| ’Delta1’       |     | is 30%.        | Increasing |         | ’Delta1’     | by      | 25% leads | to a    |
|                |     |                |            |         | 8% decrease  |         | in the    | margin. |
| ’Delta2’       |     | is 44%.        | Increasing |         | ’Delta2’     | by      | 25% leads | to a    |
|                |     |                |            |         | 11% decrease |         | in the    | margin. |
InFig.10.8weshowthefrequencyresponsesoftheupperandlowerboundsof
μobtainedbythecommandlines
semilogx(info.MussvBnds(1,1),’r-’,info.MussvBnds(1,2),
’b--’)
grid
| title(’Robust     |     | performance’) |     |     |     |     |     |     |
| ----------------- | --- | ------------- | --- | --- | --- | --- | --- | --- |
| xlabel(’Frequency |     | (rad/s)’)     |     |     |     |     |     |     |

10.2 RobustPerformanceAnalysis 161
Fig.10.8 Upperandlowerboundsofμ
ylabel(’mu’)
| legend(’\mu-upper | bound’,’\mu-lower | bound’,2) |
| ----------------- | ----------------- | --------- |
Themaximaofupperandlowerboundsofstructuredsingularvalueswithrespect
tofrequencyarefoundbythelines
| [pkl,pklidx] =  | max(info.MussvBnds(1,2).ResponseData(:)); |     |
| --------------- | ----------------------------------------- | --- |
| [pku,pkuidx] =  | max(info.MussvBnds(1,1).ResponseData(:)); |     |
| pkmu.UpperBound | = pku;                                    |     |
| pkmu.LowerBound | = pkl;                                    |     |
andareequalto
pkmu =
| UpperBound: | 0.9930 |     |
| ----------- | ------ | --- |
| LowerBound: | 0.9927 |     |
The output variable perfmargunc contains a combination of uncertain ele-
mentvaluescorrespondingtotheupperboundofperformancemargin.Substitution
ofthesevaluesintheclosed-looptransferfunctionmatrixallowstofindtheworst-
caseperformanceforthegivenlevelofuncertainty.InFig.10.9weshowthesingular
valueplotscorrespondingtoclosed-looptransferfunctionmatrixT (s)forrandom
zv
valueandworst-caseuncertainties,obtainedbythecommandlines

162 10 RobustStabilityandPerformance
Fig.10.9 Worst-caseperformance
omega = logspace(-1,3,500);
sigma(clp,’b-’,usubs(clp,perfmargunc),’r-’,omega)
Theworst-caseperformancedoesnotexceedthevalue0.9930,asexpected.
Toillustratetheinfluenceofuncertaintyontheclosed-loopsystem,inFig.10.10
we show the singular value plots of output complementary sensitivity for random
valueandworst-caseuncertainelements.
InFig.10.11weshowthemagnitudefrequencyresponseoftheinverseweighting
function W
−1
and the singular value plot of the output sensitivity S for random
p o
values of uncertainties. In order to satisfy condition (10.5), it is necessary that the
magnituderesponsesofS toliebelowthemagnituderesponseW
−1
inthewhole
o p
frequencyrange.
InFig.10.12theinversecontrolactionweightingfunctionW
−1andthesingular
u
value plot of KS , which shows the sensitivity of control action to references and
o
disturbances. As in the case of output sensitivity, condition (10.5) means that the
magnituderesponsesofKS shouldliebelowtheresponseofW
−1.
o u
Finally,weobtainthetransientresponseswithrespecttotheunitstepfirstrefer-
encefor30randomvaluesofuncertaintiesbyusingthecommandlines
tfin = 5;
nsample = 30;
[To30,samples] = usample(To,nsample);
time = 0:tfin/500:tfin;
nstep = size(time,2);

10.2 RobustPerformanceAnalysis 163
Fig.10.10 Singularvaluesofoutputcomplementarysensitivity
Fig.10.11 Singularvalueplotofoutputsensitivity

| 164 |     |     | 10 RobustStabilityandPerformance |     |
| --- | --- | --- | -------------------------------- | --- |
Fig.10.12 Sensitivityofcontroltodisturbances
| ref1(1:nstep)  | = 1.0;                 |     |     |     |
| -------------- | ---------------------- | --- | --- | --- |
| ref2(1:nstep)  | = 0.0;                 |     |     |     |
| ref = [ref1’   | ref2’];                |     |     |     |
| nsample =      | 30;                    |     |     |     |
| [To30,samples] | = usample(To,nsample); |     |     |     |
figure(4)
subplot(2,2,1)
hold off
| for i = 1:nsample |                                   |     |     |     |
| ----------------- | --------------------------------- | --- | --- | --- |
| [y,t]             | = lsim(To30(1:2,1:2,i),ref,time); |     |     |     |
plot(t,y(:,1),’r-’)
| hold on |     |     |     |     |
| ------- | --- | --- | --- | --- |
end
grid
| title(’From | inp 1 | to outp 1’) | xlabel(’Time | (secs)’) |
| ----------- | ----- | ----------- | ------------ | -------- |
ylabel(’y_1’)
figure(4)
subplot(2,2,3)
hold off
| for i = 1:nsample |                                   |     |     |     |
| ----------------- | --------------------------------- | --- | --- | --- |
| [y,t]             | = lsim(To30(1:2,1:2,i),ref,time); |     |     |     |
plot(t,y(:,2),’b-’)
| hold on |     |     |     |     |
| ------- | --- | --- | --- | --- |

10.3 Worst-CaseGain 165
Fig.10.13 Transientresponsesoftheuncertainsystem
end
grid
title(’From inp 1 to outp 2’)
xlabel(’Time (secs)’)
ylabel(’y_2’)
In a similar way the transient responses are found with respect to the unit step
reference at the second input. The transient responses to references are shown in
Fig.10.13.
10.3 Worst-Case Gain
The system performance may be assessed approximately by the maximum of the
frequency response of the largest singular value (H ∞ norm) of the sensitivity or
complementary sensitivity transfer function matrix. For uncertain systems, it is of
interesttodeterminethelargestvalueofthismaximumforthealloweduncertainty.
Thisvalue,representingthelargestpossiblegaininthefrequencydomain,isdefined
asthe“worst-case”gain.
In Robust Control Toolbox®3 the worst-case gain of uncertain systems may be
determinedbythecommandwcgain.Itcalculatesupperandlowerboundsonthe
worst gain and determines the uncertainty corresponding to this gain. The syntax,
input,andoutputargumentsofwcgainare

166 10 RobustStabilityandPerformance
[maxgain,wcunc] = wcgain(sys)
[maxgain,wcunc,info] = wcgain(sys)
– sys:modeloftheuncertainsystemunderinvestigationthatmaybeofcalssuss
orofclassufrd.Ifsysisofclassussthecomputationsaredoneforappropri-
atelychosenbythefunctionwcgainfrequencyvaluesanifitisofclassufrd
theassociatedwithsysfrequencyvectorisused;
– maxgain:structurewithfollowingfields.
• LowerBound:lowerboundontheworst-casegain;
• UpperBound:upperboundontheworst-casegain;
• CriticalFrequency:frequencyvaluecorrespondingtoLowerBound;
– wcunc: structure containing a combination of uncertain element values which
maximizethesystemgain—itcorrespondstothelowerboundoftheworst-case
gain;
– info:structurewiththefollowingfields.
• Frequency: frequency vector for which the uncertain system analysis is
done;
• Sensitivity:structurecontaininginformationfortheinfluenceoftheun-
certain elements on the worst-case gain. For instance, if in the given field is
stored the number 20, this means that if the uncertainty range of the corre-
spondingelementisincreasedby25%thenthevalueoftheworst-casegainis
increasedby5%(25%of20).
Thecommandwcgainmaybeusedforworst-casegainanalysisofcontinuous-
timeaswellasdiscrete-timesystems.Thesystemtypeisnotnecessarytobeindi-
catedbytheusersincethisinformationiscontainedinussandufrdmodels.
Example 10.3 Consider the uncertain control system described in Example 10.1.
Ourtaskistodeterminetheworst-casegainfortheallowableplantuncertainty.
To determine the worst-case gain we shall make use of the function wcgain
withoutputargumenttheoutputcomplementarysensitivityT .Thisisdonebythe
o
commandline
[maxgain,wcunc,info] = wcgain(To);
Asaresultoneobtains
maxgain =
LowerBound: 4.6934
UpperBound: 4.6943
CriticalFrequency: 3.9226
wcunc =
Delta1: [1x1 ss]
Delta2: [1x1 ss]

10.3 Worst-CaseGain 167
The peak of the maximum singular value of the output complementary sensitivity
is equal to 4.6934 (13.43 dB) and is obtained for the uncertain element transfer
functions
tf(wcunc.Delta1)
| Transfer   | function: |                |     |
| ---------- | --------- | -------------- | --- |
| -5.547 s^2 | + 4.932   | s + 1.095e-015 |     |
---------------------------------
| s^3 + 6.436 | s^2 + | 20.32 s + 13.68 |     |
| ----------- | ----- | --------------- | --- |
tf(wcunc.Delta2)
| Transfer   | function: |               |     |
| ---------- | --------- | ------------- | --- |
| -5.547 s^2 | + 9.875   | s - 8.77e-015 |     |
---------------------------------
| s^3 + 7.327 | s^2 + | 25.26 s + 27.39 |     |
| ----------- | ----- | --------------- | --- |
Theseconduncertaintyhasstrongerinfluenceontheworst-casegain;
info.Sensitivity
ans =
| Delta1: | 30.1655 |     |     |
| ------- | ------- | --- | --- |
| Delta2: | 80.2187 |     |     |
Considerthepropertiesoftheclosed-loopsystemwithnominalandworst-case
gain.
The nominal and worst-case gain of the output complementary sensitivity are
obtainedbythecommands
| Twc = usubs(To,wcunc); |                     |     |     |
| ---------------------- | ------------------- | --- | --- |
| omega =                | logspace(-1,3,100); |     |     |
sigma(Twc,’r-’,To.Nominal,’b--’,omega)
| legend(’Worst-case |     | gain’,’Nominal | system’,3) |
| ------------------ | --- | -------------- | ---------- |
andareshowninFig.10.14.
Thestepresponsesofthenominalandworst-casegainsystemsareobtainedby
thelines
| step(Twc,’r-’,To.Nominal,’b--’), |     |                | grid       |
| -------------------------------- | --- | -------------- | ---------- |
| legend(’Worst-case               |     | gain’,’Nominal | system’,4) |
ThestepresponsesareshowninFig.10.15.Itisseenfromthefigurethattheplant
uncertaintymayleadtosignificantdeteriorationofsystembehavior.Fortheworst-
casegainthetransientresponsesareveryoscillatorywithmuchlargersettlingtime.

168 10 RobustStabilityandPerformance
Fig.10.14 Closed-loopsingularvaluesfornominalandworst-casegain
Fig.10.15 Stepresponsesofthenominalandworst-casegainsystems

10.3 Worst-CaseGain 169
Fig.10.16 Randomandworst-casesingularvalueplots
Considernowthepropertiesoftheclosed-loopsystemwithrandomuncertainty
valuesandsystemwithworst-casegain.
Thesingularvalueplotsoftheoutputcomplementarysensitivityforsystemswith
randomuncertaintyvaluesandwithworst-casegainareobtainedbythelines
| sigma(Twc,’r-’,To,’b--’,omega), | grid             |            |
| ------------------------------- | ---------------- | ---------- |
| title(’Worst-case               | gain’)           |            |
| legend(’Worst-case              | gain’,’Uncertain | system’,3) |
These singular plots are shown in Fig. 10.16. The worst-case gain produces the
largestpickofthemaximumsingularvalueasexpected.
The step responses of systems with random uncertainty values and with worst-
casegainareobtainedbythecommandlines
| step(Twc,’r-’,To,’b--’), | grid             |            |
| ------------------------ | ---------------- | ---------- |
| legend(’Worst-case       | gain’,’Uncertain | system’,4) |
andareshowninFig.10.17.Thestepresponsesdeterminedfortheworst-casegain
havetheworstperformance.
Similarresultsareobtainedifinsteadofthecomplementarysensitivityfunction
oneusesasaninputargumenttowcgainthesensitivityfunctionoftheclosed-loop
system.

| 170       |                                      |     | 10  | RobustStabilityandPerformance |     |
| --------- | ------------------------------------ | --- | --- | ----------------------------- | --- |
| Fig.10.17 | Randomandworst-casegainstepresponses |     |     |                               |     |
10.4 Exercises
Exercise10.1 Givenisatwo-input/two-outputplantwithtransferfunctionmatrix
|     |     | (cid:30) | (cid:31) |     |     |
| --- | --- | -------- | -------- | --- | --- |
|     |     | k1       | k2       |     |     |
|     |     | T1s+1    | T2s+1    |     |     |
G=
|             |                                                      | k3      | k4    |            |     |
| ----------- | ---------------------------------------------------- | ------- | ----- | ---------- | --- |
|             |                                                      | T3s+1   | T4s−1 |            |     |
|             |                                                      | =7.2,   | =0.9, | =−3, =1.2, | =2, |
| The nominal | parameter values                                     | are k 1 | T 1   | k 2 T 2    | k 3 |
| T =3,k      | =5andT =0.7,therelativeparameteruncertaintybeing45%. |         |       |            |     |
| 3           | 4 4                                                  |         |       |            |     |
Thecontrollertransfermatrixis
|     |     | (cid:30) | (cid:31) |     |     |
| --- | --- | -------- | -------- | --- | --- |
10(s+1)
0
K= 0.3s+1
15(s+2)
0
s+1
Analyze the robust stability of the closed-loop system using the function
robuststab.

10.4 Exercises 171
Exercise10.2 Givenisatwo-input/two-outputplantwithnominaltransferfunction
matrix
(cid:2) (cid:3)
1 −s+2 2s+1
G=
s2+2s+4 −3 −s+2
andcontroller
(cid:2) (cid:3)
2(s+2)(s2+2s+4) −s+2 −2s−1
K=
s(s+1)(s2+2s+7) 3 −s+2
Theplanthasinputuncertaintiesthatdonotexceed2%inthelowfrequencyrange,
increasing gradually to 100 % at frequency 10 rad/s and reaching 200 % in high
frequencyrange.
Construct a plant model with input multiplicative uncertainty and analyze the
robuststabilityoftheclosed-loopsystem.
Exercise 10.3 For the systems presented in Exercises 10.1 and 10.2, analyze the
closed-looprobustperformanceusingthefunctionrobustperf.
Exercise 10.4 Given is a plant with uncertain parameters and input uncertainty
whosetransferfunctionis
k
G=
Ts+1
The gain k and time constant T have nominal values 1 and 2, respectively, and
relativeuncertainty25%.Theinputplantuncertaintyis5%inthelowfrequency
range,increasinggraduallyto100%atfrequency2.5rad/sandreaching500%in
thehighfrequencyrange.
Thecontrollertransferfunctionis
k (T s+1)
K= c c
T s
c
wherek =0.15,T =0.4.
c c
(a) Construct a plant model representing the input uncertainty as a multiplicative
uncertainty.
(b) Determinetheworstcasegainoftheclosed-loopsystembyusingthefunction
wcgain;
(c) Obtainthemagnituderesponsesandtransientresponsesoftheclosed-loopsys-
temforthenominalgainandworst-casegain.
(d) Obtainthemagnituderesponsesandtransientresponsesoftheclosed-loopsys-
tem for certain number of random uncertainty values and compare them with
thecorrespondingresponsesfortheworst-casegain.

172 10 RobustStabilityandPerformance
Exercise10.5 ForthesystemdescribedinExercise10.2
(a) Determine the worst closed-loop performance using the command wcgain
withtheoutputsensitivityasaninputargument.
(b) Obtain the singular value plot of the output sensitivity and the transient re-
sponsesoftheclosed-loopsysteminthenominalandworstcase.

Chapter 11
H
∞ Design
In this chapter we present two important techniques for H ∞ design of linear con-
trol systems, namely the Loop Shaping Design and the mixed sensitivity design.
It is shown how to use the corresponding functions loopsyn and mixsyn from
Robust Control Toolbox®3 that allows the controller design to be done easily. We
describe also some more sophisticated design methods implemented by the func-
tionhinfsynthatmayproducebetternominalperformanceandrobustnessofthe
closed-loop system. It is demonstrated in examples that the H ∞ design does not
always ensure robust stability and robust performance of the closed-loop system
whichisthemaindisadvantageofthisimportantdesignmethod.
11.1 H ∞ Loop-Shaping Design
Consider the block-diagram shown in Fig. 11.1. The connection of plant G and
controllerKisdrivenbythereferencesr,outputdisturbancesd,andsensornoisen.
Here,y aretheoutputsthathavetobemanipulatedanduarethecontrolsignals.In
termsofthesensitivityfunctionS(s)=(I+L(s)) −1andcomplementarysensitivity
function T(s)=L(s)(I +L(s)) −1=I −S(s),where L(s)=G(s)K(s), wehave
thefollowingimportantrelationships:
y(s)=T(s)r(s)+S(s)d(s)−T(s)n(s) (11.1)
(cid:4) (cid:5)
u(s)=K(s)S(s) r(s)−n(s)−d(s) (11.2)
andtheserelationshipsdeterminethefollowinggoalswithrespecttotheclosed-loop
system,inadditiontotherequirementthatK(s)shouldstabilizeG(s).
1. Fordisturbanceattenuationσ¯(S(jω))shouldbemadesmall.
2. Fornoisesuppressionσ¯(T(jω))shouldbemadesmall.
3. Forgoodreferencetrackingweshouldhaveσ¯(T(jω))≈σ(T(jω))≈1.
4. Forcontrolenergysavingσ¯(R(jω)),whereR(s)=K(s)S(s),shouldbemade
small.
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 173
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_11,©Springer-VerlagLondon2013

174 11 H∞Design
Fig.11.1 Closed-loop
system
If the unstructured uncertainty in the plant model G is represented by additive
perturbation,i.e.,G (s)=G(s)+Δ (s)thenthesizeofthesmallestdestabilizing
p a
additiveperturbationis
| (cid:6) | (cid:7) |     |
| ------- | ------- | --- |
1
| σ¯ Δ (jω) | =         |     |
| --------- | --------- | --- |
| a         | σ¯(R(jω)) |     |
Forrobuststabilityinthepresenceofadditiveperturbationσ¯(R(jω))shouldbe
5.
madesmall.
If the uncertainty is modeled by output multiplicative perturbation such that
(s)=(I +Δ
G p m (s))G(s) then the size of the smallest destabilizing multiplica-
tiveperturbationis
| (cid:6) | (cid:7) |     |
| ------- | ------- | --- |
1
| σ¯  | =   |     |
| --- | --- | --- |
Δ m (jω)
σ¯(T(jω))
Thatiswhy
6. For robust stability in presence of output multiplicative perturbation σ¯(T(jω))
shouldbemadesmall.
The requirements 1 to 6 cannot be satisfied simultaneously. For this reason the
designoffeedbacksystemsisatrade-offbetweenconflictinggoalsinthefrequency
domain.Fortunately,itispossibletofindacompromiseduetothedifferentrequire-
mentsinthedifferentfrequencyranges.Forinstance,thedisturbanceattenuationis
usuallyachievedinthelowfrequencyrangewhilethenoisesuppressionistobemet
inthehighfrequencyrange.
Setting of desired attenuation in the requirement 1 above, for example, may be
specifiedas
| (cid:6) | (cid:7) (cid:18) (cid:18) |     |
| ------- | ------------------------- | --- |
≤(cid:18) −1(jω) (cid:18)
| σ¯ S(jω) | W   | (11.3) |
| -------- | --- | ------ |
1
−1(jω)|isthedesiredfactorofdisturbanceattenuation.MakingW
where|W (jω)
1 1
dependent on the frequency ω allows to set different attenuation for different fre-
quencyranges.
The stability margins of the closed-loop system are set by singular values in-
equalitiesas
| (cid:6) | (cid:7) (cid:18) (cid:18) |        |
| ------- | ------------------------- | ------ |
| σ¯      | ≤(cid:18) −1(jω) (cid:18) |        |
| R(jω)   | W                         | (11.4) |
2
or
(cid:18) (cid:18)
(cid:6) (cid:7)
| σ¯    | ≤(cid:18) −1(jω) (cid:18) |        |
| ----- | ------------------------- | ------ |
| T(jω) | W                         | (11.5) |
3

11.1 H∞Loop-ShapingDesign 175
Fig.11.2 SpecifyingthedesiredsingularvaluesofL,S,andT
where|W (jω)|and|W (jω)|arethelargestadditiveandmultiplicativeplantper-
| 2   |     | 3   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- |
turbations,respectively.
Usually,theeffectofallplantuncertaintiesisrepresentedbyaunique,fictitious,
multiplicativeuncertaintyΔ sothatthedesignrequirementsarewrittenas
m
|     | 1         | (cid:18)  | (cid:18)  | (cid:6)   | (cid:7) (cid:18) | (cid:18) |
| --- | --------- | --------- | --------- | --------- | ---------------- | -------- |
|     |           | ≤(cid:18) | (cid:18); |           | ≤(cid:18) −1(jω) | (cid:18) |
|     |           | W 1       | (jω)      | σ i T(jω) | W                |          |
|     | σ (S(jω)) |           |           |           | 3                |          |
i
Theseconditionsareequivalentto
|     |          | (cid:18)  | (cid:18)  | (cid:6)  | (cid:7) (cid:18) | (cid:18) |
| --- | -------- | --------- | --------- | -------- | ---------------- | -------- |
|     | 1        | ≤(cid:18) | (cid:18); |          | ≤(cid:18) −1(jω) | (cid:18) |
|     |          | W         | (jω)      | σ¯ T(jω) | W                |          |
|     | σ(S(jω)) | 1         |           |          | 3                |          |
asisshowninFig.11.2.Notethatabovetheaxis0dB
|     |     | (cid:6) |     | (cid:7) |     |     |
| --- | --- | ------- | --- | ------- | --- | --- |
1
|     |     | σ   | L(jω) | ≈   |     |     |
| --- | --- | --- | ----- | --- | --- | --- |
σ¯(S(jω))
whilebelowthisaxisitisfulfilledthat
|     |     | (cid:6) |       | (cid:7) (cid:6) | (cid:7) |     |
| --- | --- | ------- | ----- | --------------- | ------- | --- |
|     |     | σ¯      | L(jω) | ≈σ¯ T(jω)       |         |     |
It follows from Fig. 11.2 that the controller transfer function matrix K(s) should
|               |         |               |           | σ¯(L(jω)) |     | σ(L(jω))  |
| ------------- | ------- | ------------- | --------- | --------- | --- | --------- |
| be determined | so that | the frequency | responses |           | and | avoid the |
hatchedzones.Forgoodperformanceσ(L(jω))shouldlieabovetheperformance
boundandforrobuststabilityσ¯(L(jω))shouldliebelowtherobustnessboundary.
TheideaofLoop-ShapingDesignistoshapethesingularvaluesofL(s)bysuitable
choiceofK(s)guaranteeingatthesametimethestabilityoftheclosed-loopsystem.
In Robust Control Toolbox®3, the Loop-Shaping Design is done by the func-
tionloopsyn.Thisfunctionallowstodesignastabilizingcontrollerforwhichthe

176 11 H∞Design
open-loop frequency responses are optimized so that to match closely the desired
frequencyresponsesG (seeFig.11.2).Thebasicsyntaxofthefunctionloopsyn
d
forLoop-ShapingDesignis
K = loopsyn(G,Gd)
where G is the plant transfer matrix, G d corresponds to the desired frequency re-
sponsesoftheopen-loopsystemL=GK andK istheoptimalcontroller.Thecon-
trollerK hasthepropertythatitshapestheopen-loopL=GK inasuchwaythat
itmatchesascloseaspossiblethefrequencyresponsesofG d undertheconstraint
thatthecontrollershouldstabilizetheclosed-loopsystem.
ThedesiredfrequencyresponsesG d shouldsatisfythefollowingconditions.
• Robuststability.Thedesiredloop G shouldhavelowgain(assmallaspossi-
d
ble)inthehighfrequencyrangewherethemodelissoinaccuratethatitsphase
responsesarecompletelyinaccuratewitherrorsapproaching±180 ◦
.
• Performance.ThedesiredloopG shouldhavehighgain(asgreataspossible)
d
inthelow-frequencyrange,wherethemodelisadequate,inordertoachievehigh
accuracyinsteadystateandgooddisturbanceattenuation.
• Crossoverfrequencyandroll-off.ThedesiredfrequencyresponsesG should
d
havecrossoverfrequencyω betweenthefrequencyrangesdescribedaboveand
c
shouldhaveroll-off−20or−40dB/decadebelowthecrossoverfrequency,which
allowsthedesignertokeepthefrequencydelaylessthan−180 ◦
insidetheband-
width(0<ω<ω ).
c
OtherconsiderationsthatmayaffectthechoiceofG d arethepolesandzerosof
theplantGwhicharelocatedintheright-halfofthecomplexplane.Thesepolesand
zerosimposefundamentallimitationsonthecrossoverfrequencyω .Forinstance,
c
thecrossoverfrequencyω c shouldbegreaterthanthemoduleofeachunstablepole
andlessthanthemoduleofeachunstablezero,i.e.,
| |p       | |<ω       | |z | |
| -------- | --------- | ---- |
| max      | i c < min | i    |
| Re(pi)>0 | Re(zi)>0  |      |
IftheserequirementsarenotfulfilledintheselectionofG ,thefunctionloopsyn
d
willcomputecontrollerK,buttheopenloopL=GK
willhaveapoorfittoG ,so
d
thattheperformancerequirementsarenotsatisfied.
Example11.1 Givenasystemoffourthordertwo-input,two-outputplantwithout-
putmultiplicativeuncertainty,thetransferfunctionmatrixis
| G=(I | +ΔW)G |     |
| ---- | ----- | --- |
2 nom
where
| (cid:30) | (cid:31) |     |
| -------- | -------- | --- |
| 12       | − 0.05   |     |
| 0.2s+1   | 0.1s+1   |     |
G =
| nom 0.1        | 5             |     |
| -------------- | ------------- | --- |
| (cid:2) 0.3s+1 | (cid:3)0.7s−1 |     |
| Δ              | 0             |     |
| Δ= 1           | , |Δ |<1,|Δ   | |<1 |
|                | 1             | 2   |
| 0 Δ            | 2             |     |

| 11.1 H∞Loop-ShapingDesign |     |     | 177 |
| ------------------------- | --- | --- | --- |
and
(cid:2) (cid:3)
= w 1 0
W
0 w
2
is the matrix of weighting functions determined by the model errors in the two
channels. The uncertainty in the first output is 10 % in the low frequency range
increasesto100%atω=20rad/sandreaches1000%inthehighfrequencyrange.
Theuncertaintyinthesecondoutputis20%inthelowfrequencyrange,100%at
ω=25rad/sand1000%inthehighfrequencyrange.
Theuncertainplantmodelisobtainedbythecommandlines
s = tf(’s’);
| g11 = 12/(0.2*s    | + 1);              |     |     |
| ------------------ | ------------------ | --- | --- |
| g12 = -0.05/(0.1*s | + 1);              |     |     |
| g21 = 0.1/(0.3*s   | + 1);              |     |     |
| g22 = 5/(0.7*s     | - 1);              |     |     |
| Gnom =             | [g11 g12;g21 g22]; |     |     |
w1 = makeweight(0.1,20,10);
w2 = makeweight(0.2,25,10);
W = blkdiag(w1,w2);
| Delta_1     | = ultidyn(’Delta_1’,[1    | 1]); |     |
| ----------- | ------------------------- | ---- | --- |
| Delta_2     | = ultidyn(’Delta_2’,[1    | 1]); |     |
| Delta =     | blkdiag(Delta_1,Delta_2); |      |     |
| G = (eye(2) | + Delta*W)*Gnom;          |      |     |
TheplantsingularvaluesareshowninFig.11.3.Itisseenthatafterthefrequencyof
20rad/sthereisasignificantuncertaintyintheplantwhichmayreachupto20dB
atfrequencieslargerthan100rad/s.Hence,thecontrollershouldbedesignedsothat
theopen-loopsystemhasgainthatissmallerthan−20dBforω>100rad/s.
Therequirementstothesingularvaluesoftheopen-looptransferfunctionmatrix
are.
| •   |     | −20 | −20 |
| --- | --- | --- | --- |
Robustness requirements: Roll-off dB/decade and a gain of dB at
frequency100rad/s,
•
Performancerequirements:Maximize1/σ(S)inthehighfrequencyrange.
Bothrequirementsmaybesatisfiedtakingthedesiredopen-looptransferfunction
matrixas
G (s)=10/s
d
(NotethatthecoefficientinthenumeratorofG (s)isexactlyequaltothecrossover
d
| frequencyω | c .)                                  |     |     |
| ---------- | ------------------------------------- | --- | --- |
| TheH ∞     | Loop-ShapingDesignisdonebythecommands |     |     |
Gd = 10/s;
| [K,cls,gam] | = loopsyn(Gnom,Gd); |     |     |
| ----------- | ------------------- | --- | --- |
The desired frequency responses and the obtained responses of the open-loop
systemareshowninFig.11.4.Theyareproducedbythecommandlines

178 11 H∞Design
Fig.11.3 Plantsingularvalues
Fig.11.4 Designresultsobtainedbyloopsyn

11.2 MixedSensitivityDesign 179
looptransfer = loopsens(Gnom,K);
L = looptransfer.Lo;
sigma(L,’r-’,Gd,’b--’,Gd/gam,’k-.’,Gd*gam,’k-.’,omega)
It is seen that both singular values of L=GK are close to the desired frequency
responseG .Thenumber±gam,dB(i.e.,20log10(gam))showstheaccuracywith
d
whichtheopen-loopfrequencyresponsesmatchthedesiredfrequencyresponses,
σ¯(GK),dB≥|G |−gam,dB, ω<ω
d c
and
σ¯(GK),dB≤|G |+gam,dB, ω>ω
d c
Inthegivencasewehave
gam =
1.6097
Thequantities1/σ (S),characterizingtheperformance,andthequantitiesσ (T),
i i
characterizingsystemrobustness,areobtainedbythecommandlines
omega = logspace(-1,3,100);
I = eye(size(L));
sigma(I+L,’r-’,T,’b--’,omega);
grid
legend(’1/\sigma(S) performance’,’\sigma(T) robustness’)
(Notethatthequantities1/σ (S)arethesingularvaluesofthematrixS
−1=I+L.)
i
TheresultsareshowninFig.11.5.
The controller singular values are shown in Fig. 11.6. The controller is of 10th
orderandhasanintegratingeffectinthelowfrequencyrange.
The sensitivity function and complementary sensitivity function of the closed-
loopuncertainsystemareshowninFigs.11.7and11.8,respectively.
The transient responses of the closed-loop uncertain system to unit step inputs
areshowninFig.11.9.Clearly,themutualinteractionbetweentwochannelsisvery
small(i.e.,thechannelsare decoupled),whichis dueto theclosenessofbothsin-
gularvaluesofL=GK tothedesiredfrequencyresponseG ,whichisadiagonal
d
matrix.
11.2 MixedSensitivity Design
AnotheropportunityforLoop-ShapingDesignistheH ∞ mixedsensitivitydesign,
whichisdonebythecommand
K = mixsyn(G,W1,[],W3)

180 11 H∞Design
Fig.11.5 Robustnessandperformanceoftheclosed-loopsystem
Fig.11.6 Controllersingularvalueplot

11.2 MixedSensitivityDesign 181
Fig.11.7 Sensitivityoftheuncertainsystem
Fig.11.8 Complementarysensitivityoftheuncertainsystem

| 182 |     |     | 11 H∞Design |
| --- | --- | --- | ----------- |
Fig.11.9 Transientresponsesoftheclosed-loopsystem
Inthisdesign,therequirementsforrobuststabilityandperformance,setby(11.3)
and(11.5),arecombinedinasinglerequirementwithrespecttotheH ∞closed-loop
norm
(cid:5)T (cid:5)
zr ∞<1
where(seeFig.11.10)
|     | (cid:2) | (cid:3) |     |
| --- | ------- | ------- | --- |
|     | d=ef    | W 1 S   |     |
T zr
|     |     | W T |     |
| --- | --- | --- | --- |
3
Thequantity(cid:5)T (cid:5)
zr ∞iscalledmixedsensitivitycostfunction,sinceit“penalizes”si-
multaneouslysensitivityS(s)andcomplementarysensitivityT(s).Themixedsen-
sitivitydesignisachievedwhenthefunctionW 1 hasthedesiredshapeforfrequen-
−1
cies ω<ω and the function W has the desired shape for frequencies ω>ω .
| c   | 3   |          | c   |
| --- | --- | -------- | --- |
|     | W   | W mixsyn |     |
In choosing the weighting functions 1 and 3 for a design it is nec-
essary toensure thatthecrossover frequencyfor the magnituderesponse of W at
1
0dBisbelowthecrossoverfrequencyofthemagnituderesponseofW −1 at0dB,
3
as is shown in Fig. 11.2. This allows to obtain a “gap” for the desired loop shape
−1.Inthe
| G topassbetweentheperformanceboundW |     | androbustnessboundW |     |
| ----------------------------------- | --- | ------------------- | --- |
| d                                   |     | 1                   | 3   |
oppositecasetheperformanceandrobustnessrequirementswillnotbesatisfied.
Thefunctionmixsynmaybeimplementedinthemoregeneralform
[K,cl,gam] = mixsyn(G,W1,W2,W3)

11.2 MixedSensitivityDesign 183
MixedsensitivityH∞design
Fig.11.10
which makes it possible to find a controller K minimizing the H norm of the
∞
weightedmixedsensitivity
(cid:24)⎡ ⎤(cid:24)
(cid:24) (cid:24)
(cid:24) W S (cid:24)
(cid:24)⎣ 1 ⎦(cid:24)
W R
(cid:24) 2 (cid:24)
(cid:24) (cid:24)
W 3 T
∞
TheinclusionofthetermW R allowsto“penalize”thecontrolactionu(t)sothat
2
tominimizethecontrolenergy.TheweightingfunctionsW 1 ,W 2 ,W 3 maybescalar
variables,matriceswithappropriatedimensionsoremptyvariables.
The matrices S, R, and T obtained on the basis of the computed K satisfy the
inequalities
|     | (cid:6) (cid:7) | (cid:6) (cid:7)   |
| --- | --------------- | ----------------- |
|     | σ¯ ≤γσ          | −1(jω)            |
|     | S(jω)           | W                 |
|     | (cid:6) (cid:7) | (cid:6) 1 (cid:7) |
|     | σ¯ ≤γσ          | −1(jω)            |
|     | R(jω)           | W                 |
|     | (cid:6) (cid:7) | (cid:6) 2 (cid:7) |
−1(jω)
|     | σ¯ T(jω) ≤γσ | W   |
| --- | ------------ | --- |
3
| =gam.Ifγ | <1isfulfilledthen(cid:5)T | (cid:5) |
| -------- | ------------------------- | ------- |
| whereγ   |                           | zr ∞<1. |
The weighting functions W ,W , and W are used to “shape” the closed-
1 2 3
loop transfer functions S,R, and T, respectively, which is different from shap-
H
ing the open-loop frequency response in ∞ Loop-Shaping Design, discussed in
Sect.11.1.
Example11.2 ConsiderthesystemwithmultiplicativeuncertaintygiveninExam-
ple11.1.Theperformanceandrobuststabilityboundsarespecifiedbytheweighting
functions
|     | s+10   | s+10     |
| --- | ------ | -------- |
|     | =      | =        |
|     | W 1 ,  | W 3      |
|     | 2s+0.3 | 0.05s+20 |

| 184 |     |     |     | 11 H∞Design |
| --- | --- | --- | --- | ----------- |
ThedesignofH
|     | ∞ mixedsensitivityoptimalcontrollerisdonebythecommand |     |     |     |
| --- | ----------------------------------------------------- | --- | --- | --- |
lines
| W1 =           | (s + 10)/(2*s    | + 0.3);                  |     |     |
| -------------- | ---------------- | ------------------------ | --- | --- |
| W3 =           | (s + 10)/(0.05*s | + 20);                   |     |     |
| [K_h,cl_h,gam] |                  | = mixsyn(Gnom,W1,[],W3); |     |     |
Thedesignresultsareanalyzedwiththeaidofthecommandlines
| looptransfer | =   | loopsens(Gnom,K_h); |     |     |
| ------------ | --- | ------------------- | --- | --- |
L = looptransfer.Lo;
T = looptransfer.To;
I = eye(size(L));
figure(1)
| omega | = logspace(-1,3,100); |     |     |     |
| ----- | --------------------- | --- | --- | --- |
sigma(I+L,’b-’,W1/gam,’r--’,T,’b-.’,gam/W3,’r.’,omega)
grid
| legend(’1/\sigma(S) |               | performance’, | ...         |     |
| ------------------- | ------------- | ------------- | ----------- | --- |
|                     | ’\sigma(W1)   | performance   | bound’, ... |     |
|                     | ’\sigma(T)    | robustness’,  | ...         |     |
|                     | ’\sigma(1/W3) | robustness    | bound’,3)   |     |
figure(2)
| omega | = logspace(-1,3,100); |     |     |     |
| ----- | --------------------- | --- | --- | --- |
sigma(L,’b-’,W1/gam,’r--’,gam/W3,’r.’,omega)
grid
| legend(’\sigma(L)’,’\sigma(W1) |               |            | performance | bound’, ... |
| ------------------------------ | ------------- | ---------- | ----------- | ----------- |
|                                | ’\sigma(1/W3) | robustness | bound’,3)   |             |
InFig.11.11weshowthesingularvaluesofS andT andtheperformanceandro-
bustness bounds W 1 and 1/W 3 , respectively. It is seen that the minimum singular
−1
valueof S liesbelowthemagnituderesponseof W andthemaximumsingular
1
value of T is below the magnitude response of 1/W . This means that the perfor-
3
mance and robustness requirements specified by the weighting functions W 1 and
W ,aresatisfied.Actually,wehave
3
gam =
0.7891
InFig.11.12weshowseparatelythesingularvaluesoftheopen-loopsystemL
withrespecttoperformanceboundW androbustnessbound1/W .Asaresultof
|     |     | 1   |     | 3   |
| --- | --- | --- | --- | --- |
satisfyingperformanceandrobustnessrequirements,thesmallestsingularvalueof
LliesabovetheboundW 1 inthelowfrequencyrangeandthelargestsingularvalue
| ofLisbelowthebound1/W |     | inthehighfrequencyrange. |     |     |
| --------------------- | --- | ------------------------ | --- | --- |
3
ThecontrollersingularvaluesareshowninFig.11.13.Thecontrollerisofeighth
orderandhasanintegratingeffectinthelowfrequencyrange.
The transient responses of the uncertain closed-loop system are shown in
Fig.11.14.Obviously,withthisdesignalsothemutualinfluencebetweenthechan-
nelsisverysmall.

11.2 MixedSensitivityDesign 185
Fig.11.11 Designresultsobtainedbymixsyn
Fig.11.12 Singularvaluesoftheopen-loopsystem

186 11 H∞Design
Fig.11.13 Controllersingularvalueplot
Fig.11.14 Transientresponsesoftheclosed-loopsystem

11.3 OtherVersionsofH∞Design 187
Fig.11.15 Closed-loopsystemwithmodel
Fig.11.16 StandardH∞
optimizationproblem
| 11.3 OtherVersionsof H | Design |     |     |     |
| ---------------------- | ------ | --- | --- | --- |
∞
H
11.3.1 ∞ ControlwithModels
H
∞ controlwithmodelsmaybeconsideredasangeneralizationofthemixedsen-
sitivity design. The usage of this method allows the robustness and performance
requirements to be fulfilled, including also performance requirements to specified
modelM.Theblock-diagramoftheclosed-loopsystemisshowninFig.11.15.
The closed-loop system may be represented in the form of the standard H
∞
optimizationproblemshowninFig.11.16.Theopen-loopsystemisdescribedby
| ⎡ ⎤ ⎡  |         | ⎤⎡        | ⎤   |        |
| ------ | ------- | --------- | --- | ------ |
| z −W   |         |           | r   |        |
| 1      | p M W p | W p G nom |     |        |
| ⎣z ⎦=⎣ |         | ⎦⎣d⎦      |     |        |
| 2      | 0 0     | W         | ,   | (11.6) |
u
|     | I −I | −G  |     |     |
| --- | ---- | --- | --- | --- |
| e   |      | nom | u   |     |
whichdefinestheextendedtransfermatrixP.Itmaybeshownthattheclosed-loop
systemisdescribedby
z=T w
zw
where
|     | (cid:2) (cid:3) | (cid:2) (cid:3) |     |     |
| --- | --------------- | --------------- | --- | --- |
|     | z               | r               |     |     |
| z=  | 1 ,             | w=              |     |     |
|     | z 2             | d               |     |     |

| 188 |     |     |     | 11 H∞Design |
| --- | --- | --- | --- | ----------- |
Table11.1 H∞functionstobeminimized
| Function | Description |     |     |     |
| -------- | ----------- | --- | --- | --- |
Wp(To −M) Weighteddifferencebetweentherealandidealclosed-loopsystem
| WpSo  | Weightedoutputsensitivity             |     |     |     |
| ----- | ------------------------------------- | --- | --- | --- |
| WuSiK | Weightedcontrolactionduetoreference   |     |     |     |
| WuKSo | Weightedcontrolactionduetodisturbance |     |     |     |
and
|     |     | (cid:2) |     | (cid:3) |
| --- | --- | ------- | --- | ------- |
−M)
|     | =   | W p (T o | W p S o |     |
| --- | --- | -------- | ------- | --- |
T zw (11.7)
|     |     | W S K | −W KS |     |
| --- | --- | ----- | ----- | --- |
|     |     | u i   | u o   |     |
Inthegivencasewehave
| S =(I −KG | ) −1, | S =(I −G | K) −1, | T =S G K |
| --------- | ----- | -------- | ------ | -------- |
| i         | nom   | o        | nom    | o o nom  |
and
S K=KS
|     |     | i   | o   |     |
| --- | --- | --- | --- | --- |
ThegoalistodetermineastabilizingcontrollerK thatminimizestheH normof
∞
T zw .ThefourfunctionsthathavetobeminimizedaredescribedinTable11.1.
Inthetable,W andW arefrequencydependentweightingfunctionsthatwillbe
p u
calledweightingperformancefunctionandweightingcontrolfunction,respectively.
TheroleofthefunctionW p istoensureclosenessbetweentheclosed-loopsystem
andthemodelinthedesiredlowfrequencyrangeandtheroleofthefunctionW is
u
tolimitthemagnitudeofcontrolactions.
| ThemodelM | isusuallysetinthediagonalform |     |       |     |
| --------- | ----------------------------- | --- | ----- | --- |
|           |                               | ⎡   | ⎤     |     |
|           |                               | M 0 | ... 0 |     |
1
|     |     | ⎢ M       | ... ⎥     |     |
| --- | --- | --------- | --------- | --- |
|     |     | ⎢ 0 2     | 0 ⎥       |     |
|     | M=⎢ |           | ⎥         |     |
|     |     | ⎣ . . . . | . . . . ⎦ |     |
|     |     | . .       | . .       |     |
|     |     | 0 0       | ... M r   |     |
,i=1,...,r
| sothattoachievedecouplingofthesystemoutputswiththeblocksM |     |     |     | i   |
| --------------------------------------------------------- | --- | --- | --- | --- |
usuallybeingsetassecondorderlagswithdesiredtimeconstantsanddamping.
Example 11.3 Consider the design of mass–damper–spring system described in
Sect. 9.2. The system is of second order and has three uncertain parameters m, c,
andk,whichvaryintheranges1.8≤m≤4.2,0.8≤c≤1.2,1.4≤k≤2.6.
ThedesigngoalistofindH ∞controllawu(s)=K(s)y(s)fortheconfiguration
showninFig.11.15,whichfulfillsthenominalperformancecondition
(cid:5)T (cid:5) ∞<1
zw (11.8)
wherethematrix T zw isgivenby(11.7).Thedesiredclosed-loopsystemmodelis
chosenasasecondorderlag
1
M=
T2s2+2ξTs+1

11.3 OtherVersionsofH∞Design 189
|     | =1sandξ | =0.7.Inthegivencasetheweightingperformancefunctionis |     |     |     |
| --- | ------- | ---------------------------------------------------- | --- | --- | --- |
whereT
| ascalarfunctionW |     | (s)=w | (s)andischosenas |     |     |
| ---------------- | --- | ----- | ---------------- | --- | --- |
|                  |     | p     | p                |     |     |
2s+1
(s)=0.5
|     |     |     | w p |     |     |
| --- | --- | --- | --- | --- | --- |
2s+tol
where tol=0.001. This weighting function has the purpose to ensure the gain of
the loop from r and d to the error y−y to be of order tol in the low frequency
M
range which will ensure closeness between the system and model and sufficient
disturbance attenuation at the system output. To limit the magnitude of the high
frequencycomponentsofcontrolaction,theweightingcontrolfunctionischosenas
0.05s+1
w (s)=0.5
|     |     |     | u   | 0.0001s+0.01 |     |
| --- | --- | --- | --- | ------------ | --- |
This weighted function ensures attenuation of components with frequency over
10rad/s.
The specification of model and weighting functions is done by the command
lines
| nuM = | 1;     |           |     |     |     |
| ----- | ------ | --------- | --- | --- | --- |
| dnM = | [1.0^2 | 2*0.7*1.0 |     | 1]; |     |
| gainM | = 1.0; |           |     |     |     |
M = gainM*tf(nuM,dnM);
| tol =  | 10^(-2);     |       |     |     |     |
| ------ | ------------ | ----- | --- | --- | --- |
| nuWp   | = [2         | 1];   |     |     |     |
| dnWp   | = [2         | tol]; |     |     |     |
| gainWp | = 5*10^(-1); |       |     |     |     |
Wp = gainWp*tf(nuWp,dnWp);
| nuWu   | = [0.05        |     | 1]; |     |     |
| ------ | -------------- | --- | --- | --- | --- |
| dnWu   | = [0.0001      |     | 1]; |     |     |
| gainWu | = 5.0*10^(-2); |     |     |     |     |
Wu = gainWu*tf(nuWu,dnWu);
ThematrixP oftheextendedopen-loopsystemmaybefoundfrom(11.6).How-
ever,theexpressionobtainedinthiswaycontainstwotimestheplanttransferfunc-
tion matrix G. As a consequence, the plant uncertainty will participate twice in
theclosed-loopsystemtransfermatrixwhichintroducesunnecessarypessimismin
the robustness analysis. That is why it is better to determine the transfer matrix
of the extended system from the open-loop structure obtained by the commands
interconnectorsysic.
Theopen-loopsystemstructureispresentedinFig.11.17.Thisstructureisob-
tainedbyusingthecommandsysicimplementingthefollowinglines:
| systemnames |      | = ’ G      | M Wp  | Wu ’;      |     |
| ----------- | ---- | ---------- | ----- | ---------- | --- |
| inputvar    | = ’[ | ref;       | dist; | control    | ]’; |
| outputvar   | =    | ’[ Wp;     | Wu;   | ref-G-dist | ]’; |
| input_to_G  | =    | ’[ control |       | ]’;        |     |
| input_to_M  | =    | ’[ ref     | ]’;   |            |     |

| 190       |                          |     |     |     |     | 11 H∞Design |
| --------- | ------------------------ | --- | --- | --- | --- | ----------- |
| Fig.11.17 | Open-loopsystemstructure |     |     |     |     |             |
| Fig.11.18 | Generalized              |     |     |     |     |             |
block-diagramofthe
open-loopsystem
| input_to_Wp | =        | ’[ G+dist-M | ]’; |     |     |     |
| ----------- | -------- | ----------- | --- | --- | --- | --- |
| input_to_Wu | =        | ’[ control  | ]’; |     |     |     |
| sys_ic      | = sysic; |             |     |     |     |     |
Theopen-loopsystemisobtainedinthevariablesys_icandhasthreeinputsand
threeoutputs(Fig.11.18).
H
The design is done by the function hinfsyn that computes suboptimal ∞
controllerbasedonthegivenopen-loopstructure.Sincetheuncertaintyisneglected
intheH design,thenominalvalueoftheopen-loopinterconnectionisused.
∞
H
Belowwegivethecommandsusedinthedesignof ∞ controller K followed
bythedesignresults.
| nmeas  | = 1; |     |     |     |     |     |
| ------ | ---- | --- | --- | --- | --- | --- |
| ncont  | = 1; |     |     |     |     |     |
| gmin = | 0.1; |     |     |     |     |     |
| gmax = | 10;  |     |     |     |     |     |
tol = 0.001;
| [K,clp] | = hinfsyn(sys_ic.Nominal,nmeas,ncont,gmin,gmax,tol); |     |     |     |     |     |
| ------- | ---------------------------------------------------- | --- | --- | --- | --- | --- |
get(K)
| Resetting    | value    | of Gamma | min based | on D_11, | D_12,   | D_21 terms  |
| ------------ | -------- | -------- | --------- | -------- | ------- | ----------- |
| Test bounds: |          | 0.5000   | < gamma   | <=       | 10.0000 |             |
| gamma        | hamx_eig | xinf_eig | hamy_eig  | yinf_eig |         | nrho_xy p/f |
| 10.000       | 4.8e-001 | 2.7e-008 | 5.0e-003  | 0.0e+000 |         | 0.0001 p    |

| 11.3 OtherVersionsofH∞Design |            |          |          |          | 191 |
| ---------------------------- | ---------- | -------- | -------- | -------- | --- |
| 5.250 4.8e-001               | 2.7e-008   | 5.0e-003 | 0.0e+000 | 0.0003   | p   |
| 2.875 4.8e-001               | 2.8e-008   | 5.0e-003 | 0.0e+000 | 0.0010   | p   |
| 1.688 4.8e-001               | 3.0e-008   | 5.1e-003 | 0.0e+000 | 0.0033   | p   |
| 1.094 4.8e-001               | 3.4e-008   | 5.1e-003 | 0.0e+000 | 0.0101   | p   |
| 0.797 4.8e-001               | 4.3e-008   | 5.3e-003 | 0.0e+000 | 0.0324   | p   |
| 0.648 4.8e-001               | 6.3e-008   | 5.4e-003 | 0.0e+000 | 0.1293   | p   |
| 0.574 4.8e-001               | -1.1e+001# | 5.5e-003 | 0.0e+000 | 16.6897# | f   |
| 0.611 4.8e-001               | 7.6e-008   | 5.5e-003 | 0.0e+000 | 0.2901   | p   |
| 0.593 4.8e-001               | 8.6e-008   | 5.5e-003 | 0.0e+000 | 0.6308   | p   |
| 0.583 4.8e-001               | 9.3e-008   | 5.5e-003 | 0.0e+000 | 1.3623#  | f   |
| 0.588 4.8e-001               | 9.0e-008   | 5.5e-003 | 0.0e+000 | 0.9129   | p   |
| 0.587 4.8e-001               | 9.1e-008   | 5.5e-003 | 0.0e+000 | 0.9903   | p   |
| 0.586 4.8e-001               | 9.1e-008   | 5.5e-003 | 0.0e+000 | 1.0480#  | f   |
| 0.586 4.8e-001               | 9.1e-008   | 5.5e-003 | 0.0e+000 | 1.0013#  | f   |
| Gamma value                  | achieved:  | 0.5866   |          |          |     |
Thenumberofmeasurementsandthenumberofcontrolsareequalto1.Therange
forγ-iterationischosenbetweenthenumbers0.1and10withtolerancetol=0.001.
Ateachiteration,theprogramshowsthecurrentvalueofγ andtheresultsfromfive
tests for existence of suboptimal controller. At the end of each iteration is shown
the symbol p or f which indicates whether the current value of γ is accepted or
dismissed.Thesymbol#isusedtoshowwhichofthefiveconditionsforexistenceof
H
∞ suboptimalcontrollerisviolatedfortheγ used.Whentheiterationprocedure
ends,theminimalachievablevalueofγ isgiven.Thetransferfunctionmatrixofthe
closed-loopsystemfromdisttoeissavedinthevariableclp.
The minimal achievable value of γ is 0.586 with the suboptimal controller ob-
tainedbeingofordersix,thesameastheorderoftheopen-loopsystem.Sincethe
valueoftheH ∞-normoftheclosed-loopsystemislessthan1,thecondition(11.8)
fornominalperformanceissatisfied.
ThecontrollerBodeplotisshowninFig.11.19.
Therobuststabilityanalysisoftheclosed-loopsystemisdonebythecommand
lines
| clp_ic =                    | lft(sys_ic,K); |     |     |     |     |
| --------------------------- | -------------- | --- | --- | --- | --- |
| omega = logspace(-2,2,100); |                |     |     |     |     |
| clp_g = ufrd(clp_ic,omega); |                |     |     |     |     |
opt = robopt(’Display’,’on’);
| [stabmarg,destabu,report,info] |     | = robuststab(clp_g,opt); |     |     |     |
| ------------------------------ | --- | ------------------------ | --- | --- | --- |
report
semilogx(info.MussvBnds(1,1),’r-’,info.MussvBnds(1,2),’b--’)
Theclosed-loopsystemdoesnotachieverobuststabilitysincethesmallestvalue
ofthestructuredsingularvalueisabout1.05.
Therobustperformanceanalysisisdonebythecommands
opt = robopt(’Display’,’on’);
| [perfmarg,perfmargunc,report,info] |     |     | = robustperf(clp_g,opt); |     |     |
| ---------------------------------- | --- | --- | ------------------------ | --- | --- |
report
semilogx(info.MussvBnds(1,1),’r-’,info.MussvBnds(1,2),’b--’)

| 192 |     |     |     | 11 H∞Design |
| --- | --- | --- | --- | ----------- |
Fig.11.19 FrequencyresponsesoftheH∞controller
theclosed-loopsystemdoesnotachieverobustperformancesincetheperformance
marginisonly0.6015.Thisvalueshowsthatforuncertaintygreaterthan60.15%
fromthegivenonetherobustperformanceisviolated.
Inthisway,inthegivencasetheH
∞controllerdesigneddoesnotensureneither
robuststabilitynorrobustperformanceoftheclosed-loopsystem.Sincethesmallest
valueofγ islessthan1,theclosed-loopsystemachievesonlynominalperformance.
This fact significantly limits the application of H ∞ control laws in the design of
robustsystems.
Thefrequencyresponsesandtransientresponsesoftheuncertainsystemisdone
forthesystemwithoutweightingfilters.Thissystemisobtainedinthevariablecls
afterimplementingthecommands
| systemnames | = ’          | G ’;          |            |     |
| ----------- | ------------ | ------------- | ---------- | --- |
| inputvar    | = ’[ ref;    | dist; control | ]’;        |     |
| outputvar   | = ’[ G+dist; | control;      | ref-G-dist | ]’; |
| input_to_G  | = ’[         | control ]’;   |            |     |
| sim_ic      | = sysic;     |               |            |     |
cls = lft(sim_ic,K);
ThetransferfunctionmatricesT o ,S o ,andKS o areobtainedfromthestructurecls
bythecommands
To = cls(1,1);
So = cls(1,2);

11.3 OtherVersionsofH∞Design 193
Fig.11.20 Frequencyresponsesoftheclosed-loopuncertainsystem
KSo = -cls(2,2);
The frequency responses of the uncertain system is done setting by the command
gridurealfourvaluestoeachofthethreeuncertainparameters,whichallowsto
obtainaltogether43=64responses.Themagnitudeandphasefrequencyresponses
oftheclosed-loopsystemundervariationoftheuncertainparametersareobtained
bythecommandlines
omega = logspace(-2,2,100);
T64 = gridureal(To,’c’,4,’k’,4,’m’,4);
bode(M,’r-’,T64,’b--’,omega)
andareshowntogetherwithmodelfrequencyresponsesinFig.11.20.Itisseenthat
theclosed-loopresponsesdiffersignificantlyfromthemodelresponsesaroundthe
plantresonantfrequency.
Thecomparisonbetweenthesensitivityfunctionoftheuncertainsystemandthe
inverseperformanceweightingfunctionisdonebythecommandlines
omega = logspace(-3,2,100);
S64 = gridureal(So,’c’,4,’k’,4,’m’,4);
bodemag(1/Wp,’r-’,S64,’b--’,omega)
TheresultisshowninFig.11.21.Itisseenthatforcertainvaluesoftheuncertain
parametersthemagnitudeofthesensitivityfunctionaroundtheresonantfrequency

194 11 H∞Design
Fig.11.21 Sensitivityfunctionoftheuncertainsystem
exceedssignificantlythelimitdeterminedby1/W ,whichleadstotheviolationof
p
therobustperformancecondition.
The transient responses of the closed-loop system are obtained for the nominal
plantsinceforsomevaluesoftheuncertainparametersthissystembecomesunsta-
ble.
ThetransientresponsewithrespecttothereferenceisshowninFig.11.22.The
processisaperiodicandisslowincomparisontothemodel.
ThecorrespondingcontrolactionisshowninFig.11.23.
11.3.2 Two-Degree-of-Freedom H ∞ Control
The technique of H ∞ control with model, considered above, may be extended to
the design of 2-degree-of-freedom controllers. The block-diagram of the closed-
loopsystemwith2-degree-of-freedomcontrollerisshowninFig.11.24.Thesystem
hasareference(r),outputdisturbance(d)andtwooutputerrors(z )and(z ).The
1 2
systemM istheidealmodel,towhichtheclosed-loopsystemshouldmatch.
InthegivencasethecontrollerK consistsofafeedbackcontrollerK fordistur-
y
banceattenuationandapre-filterK toachievethedesiredclosed-loopperformance
u
andisrepresentedas
K=[K K ]
r y

11.3 OtherVersionsofH∞Design 195
Fig.11.22 Transientresponseofthenominalsystemwithrespecttoreference
Fig.11.23 Controlactionofthenominalsystem

196 11 H∞Design
Fig.11.24 Closed-loopsystemwith2-degree-of-freedomcontroller
Table11.2 H∞functiontobeminimized
Function Description
Wp(SoGKr −M) Weighteddifferencebetweentherealandidealclosed-loopsystem
WpSo Weightedoutputsensitivity
WuSiKr Weightedcontrolactionduetoreference
WuKySo Weightedcontrolactionduetodisturbance
ThetransferfunctionmatricesK andK maybeobtainedasfollows.
r y
Theclosed-loopsystemmayberepresentedintheformofthestandardproblem
showninFig.11.16.Thesystemisdescribedby
⎡ ⎤ ⎡ ⎤
z 1 −W p M W p W p G ⎡ r ⎤
⎢ ⎢ z 2 ⎥ ⎥= ⎢ ⎢ 0 0 W u ⎥ ⎥⎣d⎦
⎣ ⎦ ⎣ ⎦
e I 0 0
1 u
e 0 I G
2
Theclosed-looptransferfunctionmatrixisgivenby
(cid:2) (cid:3)
W (S GK −M) W S
T = p o r p o
zw W S K W K S
u i r u y o
wheretheinputandoutputsensitivitiesareequalto
S =(I −K G) −1, S =(I −GK ) −1
i y o y
respectively. Again, the goal is to obtain a stabilizing controller K that minimizes
theH ∞ normofT zw .ThefourblocksofthematrixT zw ,whosemagnitudeshould
be minimized, have the same meaning as shown in Table 11.1. The four function
thatshouldbeminimizedaredescribedinTable11.2.
As previously, W and W are frequency dependentfilters chosen as described
p u
above.

11.3 OtherVersionsofH∞Design 197
Fig.11.25 Open-loopsystemstructure
Fig.11.26 Generalized
block-diagramofthe
open-loopsystem
Thedesignof2-degree-of-freedomcontrollerisdonetakingasinputtothecon-
troller the vector y =[rT yT]T instead of the vector y =r −y as in the case of
|     | c   |     |     | c   |
| --- | --- | --- | --- | --- |
onedegree-of-freedom.
Example11.4 Considerthemass-damper-springsystemforwhichaone-degree-of-
freedom controller with model was designed in Example 11.3. The desired model
M andtheweightingfunctionsW andW arethesameasthepreviouslyused.The
|     |     |     | p u |     |
| --- | --- | --- | --- | --- |
block-diagramoftheopen-loopsystemisgiveninFig.11.25.Thesystemstructure
isobtainedbythecommandlines
| systemnames | = ’       | G M Wp   | Wu ’;       |     |
| ----------- | --------- | -------- | ----------- | --- |
| inputvar    | = ’[ ref; | dist;    | control     | ]’; |
| outputvar   | = ’[ Wp;  | Wu;      | ref; G+dist | ]’; |
| input_to_G  | = ’[      | control  | ]’;         |     |
| input_to_M  | = ’[      | ref ]’;  |             |     |
| input_to_Wp | = ’[      | G+dist-M | ]’;         |     |
| input_to_Wu | = ’[      | control  | ]’;         |     |
| sys_ic      | = sysic;  |          |             |     |
Theopen-loopsystemhasthreeinputsandfouroutputs(Fig.11.26).Inthiscasethe
H
∞ designisdonebythecommands

198 11 H∞Design
Fig.11.27 FrequencyresponsesoftheH∞2-degree-of-freedomcontroller
nmeas = 2;
ncont = 1;
gmin = 0.1;
gmax = 10;
tol = 0.001;
[K,clp] = hinfsyn(sys_ic.Nominal,nmeas,ncont,gmin,gmax,tol);
The controller obtained is again of sixth order. The frequency responses of the
twopartsofthecontrollerareshowninFig.11.27.
The robust properties of the closed-loop system are close to the properties of
thesystemwithone-degree-of-freedomcontroller.Again,inthegivencasetheH
∞
controllerdoesnotensurerobuststabilityandrobustperformanceoftheclosed-loop
system.
Thetransientresponseoftheclosed-loopsystemisshowninFig.11.28.thetran-
sient response is significantly faster comparing to the previous example (compare
withFig.11.22).
Theclosed-loopcontrolactionhasnearly2timessmallermagnitudeincompar-
ison with the control action of the system with one-degree-of-freedom controller
(compareFigs.11.29and11.23).
Inthiswaythe2-degree-of-freedomcontrollerallowstoachievebetternominal
performanceoftheclosed-loopsystemforasmallermagnitudeofthecontrolaction.
Bothcontrollers,however,donotensurerobuststabilityandrobustperformanceof
theclosed-loopsystem.

11.3 OtherVersionsofH∞Design 199
Fig.11.28 Transientresponsesofthenominalsystemwithrespecttoreference
Fig.11.29 Controlactionofthenominalsystem

200 11 H∞Design
11.4 Exercises
Exercise11.1 Givenatwo-input,two-outputsystemwithtransferfunctionmatrix
⎡ ⎤
k1 − 0.05
G=⎣ T1s+1 0.1s+1⎦
0.1 k2
0.3s+1 T2s−1
where the coefficients k and k have nominal values 12 and 5, respectively, and
1 2
relativeuncertainty15%,andthetimeconstantsT andT havenominalvalues0.2
1 2
and0.7,respectively,andrelativeuncertainty20%.
(a) Builduncertaintymodelofthegivensystem;
(b) designaloopshapingcontrollerthatfulfillsthefollowingrequirements:
• robustnessrequirements:rolloff−20dB/decadeandattenuationof−20dB
forthefrequency100rad/s,
• performancerequirements:maximize1/σ(S)inthelowfrequencyrange;
(c) obtain the singular value plot of the open-loop system and compare with the
desiredfrequencyresponse;
(d) obtainthesingularvalueplotsofthesensitivitymatrixandcomplementarysen-
sitivityfunctionoftheuncertainclosed-loopsystem;
(e) obtainthetransientresponseoftheuncertainclosed-loopsystem.
Exercise11.2 ForthesystemfromExercise11.1dothefollowing.
(a) Design a mixed sensitivity H ∞ controller with performance and robustness
boundsspecifiedby
s+10 s+10
W = , W =
1 2s+0.3 3 0.05s+20
(b) obtainthesingularvalueplotsofthesensitivitymatrixandcomplementarysen-
sitivitymatrixandcomparethemwiththeperformanceandrobustnessbounds;
(c) obtainthesingularvalueplotsofthesensitivitymatrixandcomplementarysen-
sitivitymatrixoftheuncertainclosed-loopsystem;
(d) obtainthetransientresponsesoftheuncertainclosed-loopsystem.
Exercise11.3 Givenaplantwithtransferfunction
s−10
G=
(s+1)(s+10)
designaH ∞ 2-degree-of-freedomcontrollerminimizingtheperformanceindex
(cid:24)(cid:2) (cid:3)(cid:24)
(cid:24) (cid:24)
(cid:24) W p SG (cid:24)
(cid:24) (cid:24)
W KSG
u ∞
where
1 s+2
W = , W =
p s+0.001 u s+10

11.4 Exercises 201
Forthisaim,buildtheextendedsystemstructurebyusingthecommandsysicand
implementthefunctionhinfsynforH ∞ design.
Obtain the frequency responses of the sensitivity function and the transient re-
sponseoftheclosed-loopsystem.
Exercise11.4 Givenbelowisasystemwithplanttransferfunctionmatrix
| ⎡   |     | ⎤   |
| --- | --- | --- |
k1 − 0.05
T1s+1 0.1s+1⎦
G=⎣
0.1 k2
0.3s+1 T2s−1
where the coefficients k and k have nominal values 12 and 5, respectively, and
| 1 2 |     |     |
| --- | --- | --- |
relativeuncertainty15%andthetimeconstantsT 1 andT 2 havenominalvalues0.2
and 0.7, respectively, and relative uncertainty 20 %. (The plant is the same as in
Exercise11.1.)
(a) Builduncertainmodelofthegivensystem.
(b) DesignanH 2-degree-of-freedomcontrollerminimizingtheperformancein-
∞
dex
(cid:24)(cid:2) (cid:3)(cid:24)
| (cid:24) | (cid:24)         |     |
| -------- | ---------------- | --- |
| (cid:24) | W S(G ) (cid:24) |     |
| (cid:24) | p nom (cid:24)   |     |
W KS(G )
|     | u nom | ∞   |
| --- | ----- | --- |
where
| (cid:2) | (cid:3) | (cid:2) (cid:3) |
| ------- | ------- | --------------- |
| w       | 0       | w 0             |
| W = p   | , W =   | u               |
| p 0 w   | u       | 0 w             |
|         | p       | u               |
and
−6(0.1s+1)
| 0.95(s2+2000s+4000) |     | 10         |
| ------------------- | --- | ---------- |
| w =                 | , w | =          |
| p s2+1900s+10       |     | u 0.001s+1 |
(c) Analyzetherobuststabilityoftheclosed-loopsystem.
(d) Analyzetherobustperformanceoftheclosed-loopsystem.
(e) Obtain the singular value plots of the sensitivity function and complementary
sensitivityfunctionoftheuncertainclosed-loopsystem.
(f) Obtainthetransientresponseoftheuncertainclosed-loopsystem.

Chapter 12
μ-Synthesis
Thischapterisdevotedtotheimplementationaspectsofoneofthemostimportant
techniquesinRobustControlDesign,namelytheμ-synthesis.Forproperlychosen
weighting functions this design method usually produces a controller that ensures
bothrobuststabilityandrobustperformanceoftheclosed-loopsystem.Afterashort
statementoftheμ-synthesisproblem,wedescribetheusageofthefunctiondksyn
fromRobustControlToolbox®3thatdeterminesiterativelyacontrollerwhichmin-
imizestheclosed-loopstructuredsingularvalue.Someversionsoftheμ-synthesis
areconsiderednext,includingthedesignof2-degree-of-freedomcontrollerthatusu-
ally produces the best results with respect to the closed-loop robust performance.
At the end of the chapter we discuss some practical aspects of the μ-analysis and
μ-synthesis.
12.1 The μ-SynthesisProblem
Consider a control problem in the Linear Fractional Transformation shown in
Fig.12.1.
ThesystemdenotedbyP istheopen-loopconnectionandrepresentsallknown
elementsincludingthenominalsystemmodelandtheperformanceweightingfunc-
tions,aswellastheuncertaintyweightingfunctions.Theblock Δ istheuncertain
elementfrom the set Δ,whichparameterizesall supposedmodeluncertainty.The
controller is denotedby K. Inputs to P are three sets of signals: inputs u due to
Δ
theuncertainty,referencesanddisturbanceswandcontrolsu.Threesetsofoutputs
aregenerated:outputsy duetotheuncertainty,errorsorcontrolledoutputszand
Δ
measurementsy.
ThesetofsystemstobecontrolledisdescribedbytheLFT
(cid:23) (cid:4) (cid:5) (cid:25)
F (P,Δ):Δ∈Δ,maxσ¯ Δ(jω) ≤1
U
ω
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 203
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_12,©Springer-VerlagLondon2013

204 12 μ-Synthesis
Fig.12.1 Block-diagramof
theclosed-loopsystem
Fig.12.2 μ-Synthesis
ThedesigngoalistodetermineacontrollerK,stabilizingthenominalsystem;also
forallΔ∈Δ,max σ¯[Δ(jω)]≤1,theclosed-loopsystemisstableandsatisfies
ω
| (cid:24) (cid:4) | (cid:5)(cid:24) |     |     |
| ---------------- | --------------- | --- | --- |
| (cid:24)         | (cid:24)        |     |     |
| F F              | (P,K),Δ         | <1  |     |
U L ∞
ForgivenarbitraryK thisperformancecriterionmaybetestedbyusingtherobust
performance test on the Linear Fractional Transformation F L (P,K). The robust
performancetestshouldbeperformedwithrespecttotheextendeduncertainstruc-
ture
| %(cid:2) | (cid:3) | &   |     |
| -------- | ------- | --- | --- |
Δ 0
| Δ d=ef | :Δ∈Δ,Δ | ∈Cnw ×nz |     |
| ------ | ------ | -------- | --- |
| P      |        | F        |     |
0 Δ F
whereΔ isafictitiouscomplex(unstructured)uncertainty.Thesystemwithcon-
F
trollerK achievesrobustperformanceifandonlyif
(cid:6) (cid:7)
| μ F | (P,K)(jω) | <1  |     |
| --- | --------- | --- | --- |
ΔP L
Theaimoftheμ-synthesisistominimizethepeakvalueofthestructuredsingular
value μ (.) oftheclosed-looptransferfunctionmatrix F (P,K) overthesetof
ΔP L
allstabilizingcontrollersK.Thisiswrittenas
|          | (cid:6)          | (cid:7) |        |
| -------- | ---------------- | ------- | ------ |
| min maxμ | ΔP F L (P,K)(jω) |         | (12.1) |
ω
K stabilizing
andisshowninFig.12.2.

12.2 μ-SynthesisbyD–KIterations 205
12.2 μ-Synthesisby D–K Iterations
Theμ-synthesismethodbyD–K iterations(Sect.6.2)isrealizedinRobustControl
Toolbox®3bythefunctiondksyn.Itisimplementedbythecommandline
[K,clp,bnd] = dksyn(P,nmeas,ncont,opt)
Inputarguments
– Pistheuncertaintyplantmodel(shouldbeofclassuss)obtained,forinstance,
bythecommandsysic(differentfromthecommandforH ∞designhinfsyn
thatmayworkwiththenominalsystemonly);
– nmeas: the number of plant measured outputs (corresponds to the last nmeas
measurementoutputs);
– ncont:thenumberofplantcontrolinputs(correspondstothelastncontcon-
trolinputs);
– opt:optionalparameter.Itisanobjectcreatedbythecommandopt = dkit-
optandhasthefollowingelements:
• opt.FrequencyVector: vector with frequency values used in the μ-
analysis;ifnotset,itischosenautomatically;
• opt.InitialController: controller used to initiate first iteration, de-
faultisanemptySSobject;
• opt.AutoIter:automatedmu-synthesismode,defaultis’on’;
• opt.DisplayWhileAutoIter: displays iteration progress in opt.
AutoItermode,defaultis’off’;
• opt.StartingIterationNumber: starting iteration number, default
is1;
• opt.NumberOfAutoIterations:numberofD–K iterationstoperform,
defaultis10;
• opt.AutoScalingOrder:maximumstateorderforfittingD-scalingdata,
defaultis5;
• opt.AutoIterSmartTerminate:automaticterminationofiterationpro-
cedurebasedonprogressofdesigniteration,defaultis’on’;
• opt.AutoIterSmartTerminateTol: tolerance used by opt.Auto-
IterSmartTerminate,defaultis0.005.
Outputarguments
– K:controllerdesigned(SSobject);
– clp:closed-loopsystemmodel(USSobject)—maybeobtainedalsoasclp =
lft(P,K);
– bnd:upperboundontherobustperformanceoftheclosed-loopsystemclp;
– dkinfo:N-by-1cellarraywhereN isthetotalnumberofiterationsperformed.
Theithcellcontainsastructurewithseveralfields,mostsignificantofwhichare:
• K:Controlleratithiteration,SSobject.
• Bnds:Robustperformanceboundfortheclosed-loopsystem.
• MussvBnds: Upper and lower μ bounds, an FRD object computed by the
auxiliaryfunctionmussv.

206 12 μ-Synthesis
Fig.12.3 Frequencyresponsesoftheuncertainplant
• MussvInfo:Structurereturnedfromthefunctionmussvateachiteration.
Theinformationcontainedinthesefieldsmaybeveryimportantinsomecases.
If,forinstance,onewantstotakethecontrollerfromthefourthiteration,thismay
bedonebytheline
K_4 = dkinfo{4}.K;
Thecommanddksynworkswithcontinuous-timeaswellasdiscrete-timesys-
tems. It is not necessary to be indicated by the user since this information is con-
tainedinthessandussobjects.
Example12.1 Consideratwo-input,two-outputsystemwithtransferfunctionma-
trix
⎡ ⎤
k1 − 0.05
G=⎣ T1s+1 0.1s+1⎦
0.1 k2
0.3s+1 T2s−1
where the coefficients k and k have nominal values 12 and 5, respectively, and
1 2
relativeuncertainty15%,andthetimeconstantsT andT havenominalvalues0.2
1 2
and0.7,respectively,andrelativeuncertainty20%.
ThefrequencyresponsesoftheplantsingularvaluesareshowninFig.12.3.
The design goal is to achieve robust stability and robust performance of the
closed-loop system shown in Fig. 12.4, in the presence of plant uncertainty and
outputdisturbances.

12.2 μ-SynthesisbyD–KIterations 207
Fig.12.4 Block-diagramoftheclosed-loopsystem
Theclosed-loopsystemisdescribedby
z=T w
zw
where
(cid:2) (cid:3) (cid:2) (cid:3)
z r
z= 1 , w=
z d
2
and
(cid:2) (cid:3)
W S −W S
T = p o p o
zw W KS −W KS
u o u o
where
S =(I −GK) −1
o
istheoutputsensitivitytransferfunctionmatrix.
Toachieveclosed-looprobustperformance,i.e.
(cid:6) (cid:7)
μ T (jω) <1
ΔP zw
meansthatthecondition
(cid:5)T
zw
(cid:5) ∞<1
willbefulfilledforeachpossibleplantuncertainty.This,inturn,guaranteesfulfill-
mentoftheconditions
(cid:5)W
p
S
o
(cid:5) ∞<1, (cid:5)W
u
KS
o
(cid:5) ∞<1
Inthegivencasetheperformanceweightingandcontrolweightingfunctionsare
takenintheform
(cid:2) (cid:3) (cid:2) (cid:3)
w 0 w 0
W = p , W = u
p 0 w u 0 w
p u
where
s+10
w (s)=0.5
p s+0.3

| 208 |     |     |     |     |     |     | 12 μ-Synthesis |
| --- | --- | --- | --- | --- | --- | --- | -------------- |
and
0.001s+1
(s)=0.1
w u
0.0001s+1
Theopen-looptransferfunctionmatrixP isobtainedbythecommandlines
| systemnames | = ’          | G Wp       | Wu ’;      |            |     |     |     |
| ----------- | ------------ | ---------- | ---------- | ---------- | --- | --- | --- |
| inputvar    | = ’[ ref{2}; |            | dist{2};   | control{2} |     | ]’; |     |
| outputvar   | = ’[ Wp;     | Wu;        | ref-G-dist |            | ]’; |     |     |
| input_to_G  | = ’[         | control    | ]’;        |            |     |     |     |
| input_to_Wp | = ’[         | ref-G-dist |            | ]’;        |     |     |     |
| input_to_Wu | = ’[         | control    | ]’;        |            |     |     |     |
| sys_ic      | = sysic;     |            |            |            |     |     |     |
andisstoredinthevariablesys_ic.Theopen-loopsystemisoforder8.
Theμ-synthesisisdonebythecommands
| nmeas = | 2;  |     |     |     |     |     |     |
| ------- | --- | --- | --- | --- | --- | --- | --- |
| ncont = | 2;  |     |     |     |     |     |     |
fv = logspace(-3,3,100);
| opt = dkitopt(’FrequencyVector’,fv, |                              |     |     |     | ... |     |     |
| ----------------------------------- | ---------------------------- | --- | --- | --- | --- | --- | --- |
|                                     | ’DisplayWhileAutoIter’,’on’, |     |     |     |     | ... |     |
’NumberOfAutoIterations’,3)
| [K,cl_mu,bnd_mu,dkinfo] |     |     | = dksyn(sys_ic,nmeas,ncont,opt); |     |     |     |     |
| ----------------------- | --- | --- | -------------------------------- | --- | --- | --- | --- |
settingthreestepsoftheDK-iterations.
Afterperformingthreeiterationsoneobtainsthereport
| Iteration | Summary |     |     |     |     |     |     |
| --------- | ------- | --- | --- | --- | --- | --- | --- |
-------------------------------------------------
| Iteration      | #     |     | 1     |     | 2     |       | 3   |
| -------------- | ----- | --- | ----- | --- | ----- | ----- | --- |
| Controller     | Order |     | 8     |     | 16    |       | 12  |
| Total D-Scale  | Order |     | 0     |     | 8     |       | 4   |
| Gamma Achieved |       |     | 1.990 |     | 1.046 | 1.218 |     |
| Peak mu-Value  |       |     | 1.433 |     | 1.001 | 1.173 |     |
This report shows that at the second iteration the closed-loop system practically
achievesrobustperformanceforavalueofμbeingcloseto1.Thecontrollerorder
H
at this iteration becomes equal to 16. (Different from ∞ design, the controller
order here may be obtained significantly higher than the order of the open-loop
systemduetotheuseofscalingmatrices.)Sinceatthethirditerationthevalueofμ
isgreaterthanthevalueattheseconditeration,theprogramchoosesautomatically
thecontrollerfromthesecondstep.
ThesingularvalueplotofthecontrollerisshowninFig.12.5.
Therobuststabilityandrobustperformanceanalysisaredonebythecommand
lines
| clp_ic = | lft(sys_ic,K);      |     |     |     |     |     |     |
| -------- | ------------------- | --- | --- | --- | --- | --- | --- |
| omega =  | logspace(-2,2,100); |     |     |     |     |     |     |

12.2 μ-SynthesisbyD–KIterations 209
Fig.12.5 Controllersingularvalues
clp_g = ufrd(clp_ic,omega);
%
% Robust stability
opt = robopt(’Display’,’on’);
[stabmarg,destabu,report,info] = robuststab(clp_g,opt);
report
%
% Robust performance
opt = robopt(’Display’,’on’);
[perfmarg,perfmargunc,report,info] = robustperf(clp_g,opt);
report
AsisseenfromFig.12.6,theclosed-loopsystemremainsstableevenforuncer-
taintiesthatare4timesgreaterthantheplant.
Thefrequencyresponseofthestructuredsingularvalueincaseofrobustperfor-
manceisshowninFig.12.7.
Thefrequencyresponsesoftheclosed-loopsystemforrandomperturbationsof
theuncertainparametersareshowninFig.12.8.
Sincetheclosed-loopsystemachievesrobustperformance,thecondition
(cid:5)W
p
S
o
(cid:5) ∞<1
issatisfiedforeachuncertaintyandthesingularvaluesoftheoutputsensitivityS
o
lie below the singular values of W
−1
(Fig. 12.9). Similarly, the singular values of
p

210 12 μ-Synthesis
Fig.12.6 Closed-looprobuststability
Fig.12.7 Closed-looprobustperformance

12.2 μ-SynthesisbyD–KIterations 211
Fig.12.8 Frequencyresponsesoftheclosed-loopsystem
Fig.12.9 Sensitivityfunctionsoftheclosed-loopsystem

212 12 μ-Synthesis
Fig.12.10 Inputsensitivityoftheclosed-loopsystem
thetransfermatrix S K =KS liebelowthesingularvaluesof W −1 (Fig.12.10),
i o u
i.e.,theconstraintsonthecontrolactionarerespected.
The transient responses of the closed-loop system due to the reference for 30
randomvaluesoftheuncertainparametersareshowninFig.12.11.
12.3 Versionsof μ-Synthesis
12.3.1 μ-SynthesiswithModel
Theμ-synthesiswithamodelcorrespondstotheblock-diagramoftheclosed-loop
system shown in Fig. 12.12. This diagram is the same as the diagram shown in
Fig.11.15,butinthiscaseinsteadofH ∞ normoftheclosed-loopsystemonemin-
imizesthestructuredsingularvalueμ.Theusageofμ-synthesisallowstosuppress
theeffectofthedisturbancesonthesystemoutputandtoachieveclosenessofthe
closed-loop system behavior to the model for all possible plant uncertainties. The
open-loopand closed-looptransfer functionmatricesare thesame as those shown
inSect.11.3,usinginsteadoftheplantnominalmodelG theuncertainplantG.
nom
Example12.2 Considertheμ-synthesisofthemass–damper–springsystemwhose
H ∞designwaspresentedinExample11.3.Forthisaimweusethesamemodeland
weightingfunctionsasgiveninExample11.3:

12.3 Versionsofμ-Synthesis 213
Fig.12.11 Transientresponsesoftheclosed-loopsystem
Fig.12.12 Closed-loopsystemwithmodel
1
M= , T =1,ξ =0.7
T2s2+2ξTs+1
2s+1
W (s)=0.5
p 2s+0.001
0.05s+1
W (s)=0.5
u 0.0001s+0.01
Inthegivencase,afterthreeiterationsoneobtainsacontrollerof20thorder,for
which the maximum value of μ decreases to 1.116, i.e., the performance margin
is 0.899. Despite the fact that the robust performance is not achieved the closed-
loop system is robustly stable with the maximum of the structured singular value

214 12 μ-Synthesis
Fig.12.13 Closed-loopsystemwith2-degree-of-freedomcontroller
beingequalto0.578.Inthiswaytheμ-synthesisproducesbetterresultscompared
to H ∞ design in which the controller does not ensure even robust stability of the
closed-loopsystem.Whentheμ-synthesisdoesnotleadtorobustperformance,as
in the case under consideration, it is necessary either to change the performance
requirements to the closed-loop system (i.e., the weighting functions) or to try
2-degree-of-freedomcontrollerdesign.
12.3.2 μ-Synthesisof 2-Degree-of-FreedomController
The block-diagram of the closed-loop system in the given case is shown in
Fig.12.13andisthesameastheblock-diagramforH ∞design,showninFig.11.24.
Theusageofμ-synthesisallowstoachievebetterrobustnessoftheclosed-loopsys-
tem improving usually the nominal performance as well. The implementation of
2-degree-of-freedom controller usually lead to better design results in comparison
withtheusageof1-degree-of-freedomcontroller.
Example 12.3 Consider again the mass–damper–spring system for which an 1-
degree-of-freedomcontrollerwasdesigninthepreviousexample.Forthesamesys-
tem,inExample11.4anH ∞designof2-degree-of-freedomcontrollerwasobtained
buttherobuststabilityandrobustperformanceoftheclosed-loopsystemwerenot
achieved. In the given case, by aid of the μ-synthesis, an 18th order controller is
obtained for which the maximum value of μ is decreased to 0.984 thus achieving
closed-looprobuststabilityandrobustperformance.
ThecontrollerfrequencyresponsesareshowninFig.12.14.
Thefrequencyresponseofμinthecaseofrobuststabilityanalysisisshownin
Fig.12.15andinthecaseofrobustperformanceanalysisinFig.12.16.Obviously,
thesystemachievesbothrobuststabilityandrobustperformance.

12.3 Versionsofμ-Synthesis 215
Fig.12.14 Frequencyresponsesofthecontroller
Fig.12.15 Robuststabilityfor2-degree-of-freedomcontroller

216 12 μ-Synthesis
Fig.12.16 Robustperformancefor2-degree-of-freedomcontroller
Theworst-casegainanalysisoftheclosed-loopsystemisdonebythecommand
line
[maxgain,maxgainunc] = wcgain(To);
whereT istheclosed-looptransferfunction.
o
Themagnituderesponseoftheworst-casegainisshowninFig.12.17.
Transient responses to the reference of the uncertain closed-loop system are
showninFig.12.18andthecorrespondingcontrolactionsinFig.12.19.Thetran-
sientresponsesarecharacterizedbysatisfactoryperformanceforallpossibleplant
uncertainties.
The results of H ∞ design and μ-synthesis of the mass–damper–spring system
obtainedinExamples11.3,11.4,12.2,and12.3showthatthebestclosed-loopsys-
tem robustness is achieved for the controller in the form of 2-degrees-of-freedom
andisdesignedbytheaidofμ-synthesis.
12.4 PracticalAspectsof μ-Analysisand μ-Synthesis
In this section we give some recommendations about how to use in practice the
structuredsingularvalueμ.

12.4 PracticalAspectsofμ-Analysisandμ-Synthesis 217
Fig.12.17 Worst-casegainmagnitudefrequencyresponse
Fig.12.18 Transientresponsesoftheclosed-loopsystem

218 12 μ-Synthesis
Fig.12.19 Closed-loopcontrolactions
1. Duetotheefforts necessarytoderivetheuncertainplantmodelandthealmost
unavoidable complication of the controller designed it is appropriate to begin
withsimplifieduncertaintydescriptioninordertoseewhethertheperformance
requirementscanbemet.Onlyinthecasewhentheserequirementsaresatisfied,
itisappropriatetoconsidermorecomplicateduncertaintydescriptionsincluding,
forinstance,parametricuncertaintiesto“sharpen”thedesignwithmoreaccurate
uncertaintymodel.
2. Theusageof μ meansworst-caseanalysis,sooneshouldbecautiouswhenin-
troducingmanysourcesofuncertainties,disturbancesandnoises.Insuchacase
it becomes less and less possible for the worst case to appear and the analysis
anddesignperformedmaybecomeunnecessarilyconservative.
3. Thereisalwaysuncertaintywithrespecttoinputsandoutputssothatitisreason-
ableinthegeneralcasetoincludediagonalinputandoutputuncertainties.The
relative(multiplicative)uncertaintyisveryappropriateforthisaim.
4. In the practical design it is customary to obtain values of μ that exceed 1.
This may result from very high requirements to the closed-loop performance
which are impossible to satisfy for the given plant. In such a case it is neces-
sarytoloosentherequirementssettingotherperformanceand/orcontrolaction
weighting functions. Finding a controller that ensures value of μ less than one
meansthattherequirementssetarepossibletoachieve.Inothercasesitmaybe
necessarytodesigncontrollerwithdifferentstructure,forinstance2-degree-of-
freedomcontroller,inordertofulfilltherequirementsposed.

12.5 Exercises 219
5. Incaseofadiscrete-timesystemitisappropriatetoperformthecontrollerdesign
initiallyinthecontinuous-timecase.Thisisduetothefactthatthebestpossible
performance may be obtained in the continuous-time case which can then be
consideredasalimitfordiscrete-timedesigns.Also,inthecontinuous-timecase
it is easier to find appropriate performance weighting functions that again may
beimplementedinthediscrete-timedesign.
12.5 Exercises
Exercise12.1 ForthesystemfromExample12.1dothefollowing.
(a) Designaμ-controllerminimizingtheperformanceindex
(cid:24)(cid:2) (cid:3)(cid:24)
(cid:24) (cid:24)
(cid:24) W SG (cid:24)
p
(cid:24) (cid:24)
W u KSG ∞
where
| (cid:2) | (cid:3) | (cid:2) (cid:3) |
| ------- | ------- | --------------- |
| w       | 0       | w 0             |
| W = p   | , W =   | u               |
| p       | u       |                 |
| 0 w     | p       | 0 w u           |
and
| 0.95(s2+2000s+4000) |     | 10 −6(0.1s+1) |
| ------------------- | --- | ------------- |
| =                   |     | =             |
| w p                 | , w | u             |
| s2+1900s+10         |     | 0.001s+1      |
(b) Analyzetherobustperformanceoftheclosed-loopsystem.
(c) Obtain the singular value plots of the sensitivity function and complementary
sensitivityfunctionoftheuncertainclosed-loopsystem.
(d) Obtainthetransientresponseoftheuncertainclosed-loopsystem.
Exercise 12.2 For the same plant and weighting functions as in Exercise 12.1 do
thefollowing.
(a) Designa2-degree-of-freedomμ-controller.
(b) Analyzetherobustperformanceoftheclosed-loopsystem.
(c) Obtain the singular value plots of the sensitivity function and complementary
sensitivityfunctionoftheuncertainclosed-loopsystem.
(d) Obtainthetransientresponseoftheuncertainclosed-loopsystem.
ComparetheresultswiththeresultsfromExercise12.1.

Chapter 13
Analysis and Design of Parameter-Dependent
Systems
The structured uncertainty models presented in Chap. 9 are not the unique way to
representsystemswithuncertainparameters.Thesemodelsareusuallyappropriate
todescribesystemswhoseuncertaintiesarerelativelysmallinsizeandmaynotbe
convenient to implement in the case of large parameter variations. In such cases
it might be better to use models in the form of the so called parameter-dependent
systemswhichare appropriatefor use in themore generalcase of large uncertain-
ties.Thelinearparameter-dependentsystems,calledalsoLinearParameter-Varying
Systems (LPV systems), arise in many applications, for instance in robotics and
aerospace systems. In this chapter we show how to build models of parameter-
dependentsystemsandhowtousethesemodelsinrobuststabilityanalysisandcon-
trollerdesign.Especiallyimportantisthesocalledgainschedulingdesignwhichal-
lowstoobtainsatisfactoryclosed-loopperformanceincaseofwidelyvaryingplant
parameters.
The presentation in this chapter follows closely the corresponding chapters
of[50].
13.1 Representation ofParameter-Dependent Systems
13.1.1 SYSTEMMatrix
Inmanycasesthelinearsystemmodelsareobtainedinthegeneralformoftheso
calleddescriptorsystemswhicharedescribedbystate-spaceequationsoftheform
dx
E =Ax(t)+Bu(t) (13.1)
dt
y(t)=Cx(t)+Du(t) (13.2)
IntheseequationsthematrixE isasquarematrixthatmaybesingularinthegen-
eral case. If this matrix is invertible and well conditioned, (13.1), (13.2) are eas-
ilyconvertedtotheusualstate-spacedescriptionmultiplyingontheleftbothsides
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 221
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_13,©Springer-VerlagLondon2013

| 222 |     |     |     | 13 AnalysisandDesignofParameter-DependentSystems |     |     |     |     |     |
| --- | --- | --- | --- | ------------------------------------------------ | --- | --- | --- | --- | --- |
−1.
of (13.1) by the matrix E However, if the matrix E is singular or poorly con-
ditioned this conversion is not possible and one has to use the descriptor system
model (13.1), (13.2). The descriptor system models arise naturally in the descrip-
tion of many physical systems and are especially appropriate to represent systems
withlargeparametervariations.
Inthediscrete-timecasethedescriptorsystemsaredescribedbythestate-space
equations
|     |     |     |     | Ex  | =Ax | +Bu |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     |     | k+1 | k   | k   |     |     |     |
|     |     |     |     | y   | =Cx | +Du |     |     |     |
|     |     |     |     | k   | k   | k   |     |     |     |
Considerasanexamplethemass–damper–springsystemintroducedinSect.9.2
anddepictedinFig.9.11.Thedynamicsofthissystemisdescribedbythe2nd-order
differentialequation
|     |     |     |     | mx¨ +cx˙ | +kx | =u  |     |     |        |
| --- | --- | --- | --- | -------- | --- | --- | --- | --- | ------ |
|     |     |     |     | s        | s   | s   |     |     | (13.3) |
wherex isthedisplacementofthemassblockfromtheequilibriumpositionandu
s
is the force acting on the mass, with m the mass, c the damperconstant and k the
springconstant.Denotingx =x ,x =dx /dt,thesystem(13.3)maybedescribed
|     |     |     |     | 1 s 2 | s   |     |     |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- | --- |
bythetwofirstorderdifferentialequations
x˙ =x
(13.4)
|     |     |     |     | 1        | 2   |     |     |     |        |
| --- | --- | --- | --- | -------- | --- | --- | --- | --- | ------ |
|     |     |     |     | mx˙ =−kx | −cx | +u  |     |     | (13.5) |
|     |     |     |     | 2        | 1   | 2   |     |     |        |
Takingtheoutputasy=x
,(13.4),(13.5)arerepresentedasadescriptorsystemin
s
theform(13.1),(13.2)withmatrices
|     | (cid:2) | (cid:3) | (cid:2) | (cid:3) |     | (cid:2) (cid:3) |     |                 |     |
| --- | ------- | ------- | ------- | ------- | --- | --------------- | --- | --------------- | --- |
|     | 1       | 0       |         | 0 1     |     | 0               |     | (cid:4) (cid:5) |     |
| E=  |         |         | A=      |         | B=  |                 | C=  |                 | D=0 |
|     |         | ,       | −k      | −c ,    |     | ,               |     | 1 0 ,           |     |
|     | 0       | m       |         |         |     | 1               |     |                 |     |
MATLAB®,
In a continuous-time or discrete-time descriptor system model is
stored for convenience as a single matrix called SYSTEM matrix. This matrix has
theform
|     |     |     | ⎡   |          |     |     | ⎤   |     |     |
| --- | --- | --- | --- | -------- | --- | --- | --- | --- | --- |
|     |     |     |     | A+j(E−I) |     | B n |     |     |     |
|     |     |     | ⎢   |          |     |     | ⎥   |     |     |
|     |     |     | ⎢   |          |     | 0   | ⎥   |     |     |
|     |     |     | ⎢   |          |     |     | ⎥   |     |     |
.
|     |     |     | ⎢   |     |     | .   | ⎥   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|     |     |     | ⎢   | C   |     | D . | ⎥   |     |     |
|     |     |     | ⎣   |     |     |     | ⎦   |     |     |
0
|     |     |     |     | 0   |     | 0 −Inf |     |     |     |
| --- | --- | --- | --- | --- | --- | ------ | --- | --- | --- |
√
where j = −1, n is equal to the number of states of (13.1) and the entry Inf is
usedtodistinguishSYSTEMmatricesfromtheregularmatrices.
TheSYSTEMmatricesarecreatedbythefunctionltisys.Forgivenmatrices
A,B,C,D,Eofthedescriptorsystemformulation(13.1),(13.2),thecommandline
sys = ltisys(A,B,C,D,E)

| 13.1 RepresentationofParameter-DependentSystems |     |     |     | 223 |
| ----------------------------------------------- | --- | --- | --- | --- |
produces the SYSTEM matrix sys. When omitted, D and E are set to the default
valuesD=0andE=I.TheautonomoussystemEx˙=Ax isthusspecifiedbythe
line
sys = ltisys(A,E)
GivenaSYSTEMmatrixsyscreatedwithltisys,thefunctionltissallowsto
extractthecorrespondingstate-spacerealization.Thisisdonebythecommandline
| (A,B,C,D,E) | = ltiss(sys) |     |     |     |
| ----------- | ------------ | --- | --- | --- |
It isimportanttonotethatwhentheoutputargument E isnotreferenced,ltiss
|     |     | −1A,E −1B,C,D) |     |     |
| --- | --- | -------------- | --- | --- |
returns the state-space realization (E provided the matrix E is
nonsingular.
The numberof states, inputs, and outputs of a linear system are extractedfrom
theSYSTEMmatrixsyswiththefunctionsinfo,
sinfo(sys)
The time and frequency response plots of descriptor systems represented by
SYSTEMmatricesmaybeobtainedbythefunctionsplot.
Series and parallel interconnections of SYSTEM matrices are performed by the
functionssaddandsmultandfeedbackinterconnectioncanbedonebythefunc-
tionsloop.
| 13.1.2 Affine | Parameter-DependentModels |     |     |     |
| ------------- | ------------------------- | --- | --- | --- |
Manyphysicalsystemsmaybedescribedbylinearizedequationsindescriptorform
|     | E(p)x˙ | =A(p)x+B(p)u  |     | (13.6) |
| --- | ------ | ------------- | --- | ------ |
|     |        | y=C(p)x+D(p)u |     | (13.7) |
where A(.),...,E(.) areknownfunctionsofsomeparametervectorp=(p ,...,
1
p ). The parameters p ,...,p may vary slowly with the time within some pre-
| s   | 1   | s   |     |     |
| --- | --- | --- | --- | --- |
scribedboundaries.Inthecaseofaffineparameter-dependentsystemsthematrices
of the state-space description are affine functions of the parameters, which means
thatthesematricesmayberepresentedas
| A(p)=A    | +p A +···+p | A , B(p)=B | +p B +···+p | B   |
| --------- | ----------- | ---------- | ----------- | --- |
| 0         | 1 1         | s s        | 0 1 1       | s s |
| C(p)=C +p | C +···+p    | C , D(p)=D | +p D +···+p | D   |
| 0         | 1 1         | s s        | 0 1 1       | s s |
| E(p)=E    | +p +···+p   |            |             |     |
| 0         | 1 E 1       | s E s      |             |     |
whereA ,...,A ,B ,...,B andsoonareconstantmatricesthatdonotdependon
| 0   | s 0 s |     |     |     |
| --- | ----- | --- | --- | --- |
theparametersp ,...,p .Notethatforaparticularsystemsomeofthesematrices
1 s
maybezeromatrices.

| 224 |     |     |     | 13 AnalysisandDesignofParameter-DependentSystems |     |     |     |     |
| --- | --- | --- | --- | ------------------------------------------------ | --- | --- | --- | --- |
Fig.13.1 Parameterbox
At first glance, the affine parameter-dependent systems constitute a very small
setofsystemswithvaryingparameters.However,manyrealworldsystemsmaybe
approximatedwithsufficientaccuracyasaffineparameter-dependentsystems.The
advantageofsuchasystemmodelisthepossibilitytoderiveeasilyseveralresults
concerningclosed-loopstabilityandcontrollerdesign.
Usingthenotation
|       | (cid:2)    |      |      | (cid:3) |     | (cid:2) | (cid:3)     |     |
| ----- | ---------- | ---- | ---- | ------- | --- | ------- | ----------- | --- |
|       | A(p)+jE(p) |      | B(p) |         |     | A +jE   | B           |     |
| S(p)= |            |      |      |         | =   | i i     | i i=0,...,s |     |
|       |            |      |      | ,       | S i |         | ,           |     |
|       |            | C(p) | D(p) |         |     | C i     | D i         |     |
the affine parameter-dependent system (13.6), (13.7) is written compactly in
SYSTEMmatrixtermsas
|     |     |     | S(p)=S | +p  | S +···+p | S   |     | (13.8) |
| --- | --- | --- | ------ | --- | -------- | --- | --- | ------ |
|     |     |     |        | 0   | 1 1      | s s |     |        |
TheconstantmatricesS ,...,S maybeconsideredassystemcoefficientsandmay
|     |     | 0   |     | s   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
havenotphysicalmeaningbythemselves.
The parameter uncertainty range can be described as a box in the parameter
space.Thiscorrespondstocaseswhereeachuncertainorslowlyvaryingparameter
| p rangesbetweentwoknownboundspl |     |     |      |         | andpu     | ,   |     |        |
| ------------------------------- | --- | --- | ---- | ------- | --------- | --- | --- | ------ |
| i                               |     |     |      |         | i         | i   |     |        |
|                                 |     |     | ∈[pl | ],      | i=1,...,s |     |     |        |
|                                 |     |     | p i  | i ,pu i |           |     |     | (13.9) |
If p=(p ,...,p ) is the vector of all uncertain parameters, (13.9) constitutes a
|     | 1   | s   |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
hyperrectangleintheparameterspacecalledtheparameterbox.Theparameterbox
=3),
is set by the function pvec. For instance, in case of three parameters (s the
parameterboxisspecifiedbythecommandlines
| range | = [pl_1 | pu_1,pl_2 |     | pu_2,pl_3 |     | pu_3] |     |     |
| ----- | ------- | --------- | --- | --------- | --- | ----- | --- | --- |
p = pvec(’box’,range)
TheparameterboxforthecaseofthreeparametersisshowninFig.13.1.

| 13.1 RepresentationofParameter-DependentSystems |     |     |     |     |     |     |     | 225 |
| ----------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
p˙
The function pvec allows also to specify bounds on the rates of variation i
of the parameter vector components p (t). For instance, if the rates of the three
i
parameters p (t),p (t),p (t) vary in the ranges [vl vu ], [vl vu ], [vl vu ],
|     | 1   | 2 3 |     |     |     | 1 1 | 2 2 | 3 3 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
respectively,these rates may be specifiedby addinga third argument rate to the
callinglistofpvecasshownbelow
| rate = | [vl_1 | vu_1, | vl_2 | vu_2, vl_3 | vu_3] |     |     |     |
| ------ | ----- | ----- | ---- | ---------- | ----- | --- | --- | --- |
p = pvec(’box’,range,rate)
When the argument rate is omitted, all parameters are assumed to be time-
invariant.
Provided the coefficient matrices S ,...,S are known and the domains where
|     |     |     |     | 0 s |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
the parameters and their rates vary are specified, the affine parameter-dependent
model(13.8)maybeobtainedbythefunctionpsys.Forinstance,thesystem
|     |     | S(p)=S | +p  | S +p | S +p | S   |     |     |
| --- | --- | ------ | --- | ---- | ---- | --- | --- | --- |
|     |     |        | 0   | 1 1  | 2 2  | 3 3 |     |     |
dependingonthreeparameters,isdefinedby
S0 = ltisys(A0,B0,C0,D0,E0)
S1 = ltisys(A1,B1,C1,D1,E1)
S2 = ltisys(A2,B2,C2,D2,E2)
S3 = ltisys(A3,B3,C3,D3,E3)
| pds = | psys(pv, | [S0 | S1 S2 | S3]) |     |     |     |     |
| ----- | -------- | --- | ----- | ---- | --- | --- | --- | --- |
wherepvistheparameterdescriptionreturnedbythefunctionpvec.
It is necessary to stress that, by default, the function ltisys sets the E(p)
matrix to the identity matrix I. That is why if the arguments E0, E1, E2, E3
in the above lines are omitted then the matrix E(p) will be set to E(p) =
I +(p +p +p )I. To specify an affine parameter-dependent system with a
| 1   | 2   | 3   |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
E(p)=I),
parameter-independent E matrix (e.g., it is necessary to explicitly set
| E =E | =E =0byentering |     |     |     |     |     |     |     |
| ---- | --------------- | --- | --- | --- | --- | --- | --- | --- |
| 1 2  | 3               |     |     |     |     |     |     |     |
S0 = ltisys(A0,B0,C0,D0)
S1 = ltisys(A1,B1,C1,D1,0)
S2 = ltisys(A2,B2,C2,D2,0)
S3 = ltisys(A3,B3,C3,D3,0)
Example 13.1 Consider the mass–damper–spring system whose state-space equa-
tions (13.4), (13.5) were obtained earlier in this section in descriptor form. The
threeuncertainparametersm,k,cofthesystemvaryintheintervals
|     | m∈[1.8,4.2], |     |     | k∈[1.4,2.6], |     | c∈[0.8,1.2] |     |     |
| --- | ------------ | --- | --- | ------------ | --- | ----------- | --- | --- |
Theparameter-dependentmatricesofthemass–damper–springsystemmayberep-
resentedasaffinefunctionsoftheuncertainparametersm,k,cas
(cid:2) (cid:3) (cid:2) (cid:3) (cid:2) (cid:3) (cid:2) (cid:3) (cid:2) (cid:3)
|           |     | 0 1   | 0   | 1 0 | 0   | 0   | 0   | 0 0 |
| --------- | --- | ----- | --- | --- | --- | --- | --- | --- |
| A(m,k,c)= |     |       | =   | +m  | +k  |     | +c  |     |
|           |     | −k −c |     |     |     | −1  |     | −1  |
|           |     |       | 0   | 0 0 | 0   |     | 0   | 0   |

| 226       |         |         | 13              | AnalysisandDesignofParameter-DependentSystems |         |                 |         |         |
| --------- | ------- | ------- | --------------- | --------------------------------------------- | ------- | --------------- | ------- | ------- |
|           | (cid:2) | (cid:3) | (cid:2) (cid:3) | (cid:2)                                       | (cid:3) | (cid:2) (cid:3) | (cid:2) | (cid:3) |
|           | 1       | 0       | 1 0             |                                               | 0 0     | 0 0             | 0       | 0       |
| E(m,k,c)= |         | =       |                 | +m                                            |         | +k              | +c      |         |
|           | 0       | m       | 0 0             |                                               | 0 1     | 0 0             | 0       | 0       |
The affine model of the mass–damper–spring system is specified by the following
commandlines:
| A_0 = | [0 1;0 | 0]; B_0 | = [0 | 1]’; | C_0 | = [1 0]; | D_0 | = 0; |
| ----- | ------ | ------- | ---- | ---- | --- | -------- | --- | ---- |
| E_0 = | [1 0;0 | 0];     |      |      |     |          |     |      |
S_0 = ltisys(A_0,B_0,C_0,D_0,E_0);
%
| A_m = | [0 0;0 | 0]; B_m | = [0 | 0]’; | C_m | = [0 0]; | D_m | = 0; |
| ----- | ------ | ------- | ---- | ---- | --- | -------- | --- | ---- |
| E_m = | [0 0;0 | 1];     |      |      |     |          |     |      |
S_m = ltisys(A_m,B_m,C_m,D_m,E_m);
%
| A_k = | [0 0;-1 | 0]; | B_k = | [0 0]’; | C_k | = [0 | 0]; D_k | = 0; |
| ----- | ------- | --- | ----- | ------- | --- | ---- | ------- | ---- |
| E_k = | [0 0;0  | 0]; |       |         |     |      |         |      |
S_k = ltisys(A_k,B_k,C_k,D_k,0);
%
| A_c = | [0 0;0 | -1]; | B_c = | [0 0]’; | C_c | = [0 | 0]; D_c | = 0; |
| ----- | ------ | ---- | ----- | ------- | --- | ---- | ------- | ---- |
| E_c = | [0 0;0 | 0];  |       |         |     |      |         |      |
S_c = ltisys(A_c,B_c,C_c,D_c,0);
%
| pv = pvec(’box’,[1.8 |                |     | 4.2;1.4 |     | 2.6;0.8 | 1.2]); |     |     |
| -------------------- | -------------- | --- | ------- | --- | ------- | ------ | --- | --- |
| pds_mds              | = psys(pv,[S_0 |     | S_m     | S_k | S_c]);  |        |     |     |
ThefirstSYSTEMmatrixS_0containsthestate-spacedataform=k=c=0while
S_m, S_k, S_cdefinethecoefficientmatricesof m,k,c.Therangeof param-
eter values in the parameter box is specified by the pvec command. The results
obtainedcanbecheckedwiththecommandspsinfoandpvinfo:
psinfo(pds_mds)
| Affine | parameter-dependent |     |             | model |     | with 3 parameters |     |     |
| ------ | ------------------- | --- | ----------- | ----- | --- | ----------------- | --- | --- |
| (4     | systems)            |     |             |       |     |                   |     |     |
| Each   | system              | has | 2 state(s), |       | 1   | input(s),         | and |     |
1 output(s)
pvinfo(pv_mds)
| Vector | of 3 parameters |     | ranging |     | in  | a box |     |     |
| ------ | --------------- | --- | ------- | --- | --- | ----- | --- | --- |
Thecommandline
| nom_sys | = psinfo(pds_mds,’eval’,[3.0 |     |     |     |     | 2.0 | 1.0]) |     |
| ------- | ---------------------------- | --- | --- | --- | --- | --- | ----- | --- |
=
allows to evaluate the parameter-dependent model for the nominal values m
3.0,k=2.0,c=1.0.

13.1 RepresentationofParameter-DependentSystems 227
Fig.13.2 Polytopic
parameterrange
Apartfromthepossibilitytodescribetheparameteruncertaintyrangeasabox,
uncertainparametervectorscanbespecifiedasranginginapolytopeoftheparam-
eter space. This possibility is illustrated in Fig. 13.2 for the simple case of s =2.
Thepolytopeischaracterizedbythefourvertices
|     | Π   | =(1,3), | Π   | =(7,7), | Π   | =(8,2), | Π =(2,1) |
| --- | --- | ------- | --- | ------- | --- | ------- | -------- |
|     | 1   |         |     | 2       |     | 3       | 4        |
Anuncertainparametervectorpwiththisrangeofvaluesisdefinedby
| pi1=[1,3], |     | pi2=[7,7], |     | pi3=[8,2], |     | pi4=[2,1] |     |
| ---------- | --- | ---------- | --- | ---------- | --- | --------- | --- |
p = pvec(’pol’,[pi1,pi2,pi3,pi4])
Thestring’pol’indicatesthattheparameterrangeisdefinedasapolytope.
13.1.3 PolytopicModels
Polytopicsystemisalineartime-varyingsystem
|     |     |     |     | E(t)x˙ =A(t)x+B(t)u |     |     |     |
| --- | --- | --- | --- | ------------------- | --- | --- | --- |
y=C(t)x+D(t)u
whoseSYSTEMmatrix
|     |     |     |     | (cid:2)    |     | (cid:3) |     |
| --- | --- | --- | --- | ---------- | --- | ------- | --- |
|     |     |     |     | A(t)+jE(t) |     | B(t)    |     |
S(t)=
|     |     |     |     | C(t) |     | D(t) |     |
| --- | --- | --- | --- | ---- | --- | ---- | --- |
varieswithinafixedpolytopeofmatrices
|                       |     |     |         | (cid:21)                     |         |           | (cid:22) |
| --------------------- | --- | --- | ------- | ---------------------------- | ------- | --------- | -------- |
|                       |     |     |         | (cid:14)q                    |         | (cid:14)q |          |
|                       |     |     | =       | :α                           | ≥0,     | =1        |          |
|                       |     |     | P       | α S                          |         | α         |          |
|                       |     |     |         | i i                          | i       | i         |          |
|                       |     |     |         | i=1                          |         | i=1       |          |
| IntheaboveexpressionS |     |     | ,S      | ,...,S aregivenvertexsystems |         |           |          |
|                       |     |     | 1       | 2 q                          |         |           |          |
|                       |     |     | (cid:2) |                              | (cid:3) |           |          |
|                       |     |     |         | A +jE                        | B       |           |          |
|                       |     |     | S =     | i i                          | i ,     | i=1,...,q |          |
i
|     |     |     |     | C i | D i |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |

| 228 |     |     |     | 13 AnalysisandDesignofParameter-DependentSystems |     |     |     |     |
| --- | --- | --- | --- | ------------------------------------------------ | --- | --- | --- | --- |
correspondingtotheverticesofS(t).
In this way the polytopic system S(t) is a convex combination (linear com-
bination with nonnegative coefficients) of the SYSTEM matrices S 1 ,...,S q , i.e.
S(t)=α S +···+α S .Thenonnegativenumbersα ,...,α arecalledthepoly-
|     | 1   | 1   | q q |     |     | 1   | q   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
topiccoordinatesofS(t).
Polytopic models are fully specified by the list of their vertex systems, i.e., by
the SYSTEM matrices S 1 ,...,S q and may be created by the function psys. For
instance, a polytopic model taking values in the convex combination of the three
| lineartime-invariantsystemsS1, |     |            |     | S2,     | S3iscreatedbytheline |     |     |     |
| ------------------------------ | --- | ---------- | --- | ------- | -------------------- | --- | --- | --- |
| polsys                         |     | = psys([S1 |     | S2 S3]) |                      |     |     |     |
Affineparameter-dependentsystems
|     |     |     |     | (cid:2)    |     |      | (cid:3) |     |
| --- | --- | --- | --- | ---------- | --- | ---- | ------- | --- |
|     |     |     |     | A(p)+jE(p) |     | B(p) |         |     |
S(p)=
|     |     |     |     | C(p) |     | D(p) |     |     |
| --- | --- | --- | --- | ---- | --- | ---- | --- | --- |
maybeconvertedeasilytopolytopicsystems.Ifeachparameterp i variesinsome
interval [pl ,pu ], i =1,...,s, then the parameter vector p=(p ,...,p ) takes
|     |     | i i |     |     |     |     | 1   | s   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
=2s
values in a parameter box with q corners Π 1 ,Π 2 ,...,Π q . According to the
results of functional analysis, if the function S(p) is affine in p, then it maps this
parameter box to some polytope of SYSTEM matrices. Specifically, this polytope
istheconvexlinearcombinationoftheimagesS =S(Π ),S =S(Π ),...,S =
|     |     |     |     |     | 1   |     | 1 2 2 | q   |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- |
S(Π q ) oftheparameterboxcorners Π 1 ,Π 2 ,...,Π q .Theseimagesarethevertex
systemsofthepolytopicmodel.
An affine parameter-dependent system is converted to an equivalent polytopic
modelusingthefunctionaff2pol.Thesyntaxisofthisfunctionis
| polsys |     | = aff2pol(affsys) |     |     |     |     |     |     |
| ------ | --- | ----------------- | --- | --- | --- | --- | --- | --- |
where affsys is the affine model and polsys is the resulting polytopicmodel.
The polytopic model consists of the instances of affsys at the vertices of the
parameterbox.
Forillustration,ifthefunctionaff2polisappliedtothemass–damper–spring
system,consideredinExample13.1,oneobtains
| pols_mds |     | = aff2pol(pds_mds); |     |     |     |     |     |     |
| -------- | --- | ------------------- | --- | --- | --- | --- | --- | --- |
psinfo(pols_mds)
| Polytopic |      | model  | with | 8 vertex    | systems |           |     |     |
| --------- | ---- | ------ | ---- | ----------- | ------- | --------- | --- | --- |
|           | Each | system | has  | 2 state(s), | 1       | input(s), | and |     |
1 output(s)
In the given case the affine model depends on three parameters, which results in
q=23=8vertexsystemsofthepolytopicmodel.

13.2 AnalysisofParameter-DependentSystems 229
13.2 Analysisof Parameter-Dependent Systems
InthissectionweconsidertheimplementationofMATLAB®functionsforstability
analysisofparameter-dependentsystemsandevaluationofthetransientresponseof
suchsystems.
Stabilityanalysisofparameter-dependentsystemsisdonebythesecondmethod
ofLyapunov.Accordingtothismethodalineartime-varyingsystem
E(t)x˙=A(t)x (13.10)
isasymptoticallystableifthereexistsapositivedefinitequadraticLyapunovfunc-
tion
V(x)=xTPx
suchthatitsderivativewithrespecttotimeisnegativedefinite,i.e.
dV(x(t))
<0
dt
along all state trajectories. If it is possible to find such a Lyapunov function we
saythatthesystem(13.10)isquadraticallystable.TheexistenceofquadraticLya-
punovfunctionguaranteesstabilityforarbitrarilyfasttimevariationsofthesystem
parameterswhichisaverystringentconditioninpractice.
The quadratic stability of affine or polytopic parameter-dependent system may
betestedbytheMATLAB®functionquadstabwhichinvolvessolutionofseveral
LinearMatrixInequalities(LMI)inanattempttofindasuitableLyapunovfunction
V(x).However,quadstabmayproducepessimisticresultsduetotheallowance
ofarbitrarilyfastparametervariations.Lessconservativeresultsincaseofconstant
orslowlyvaryingparametersmaybeobtainedbythefunctionpdlstabwhichis
considerednext.
For a parameter-dependent system the function pdlstab seeks a parameter-
dependentLyapunovfunctiontoestablishthestabilityofuncertainstate-spacemod-
els over some parameter range or polytope of systems. Specifically, for an affine
parameter-dependentsystem
E(p)x˙ =A(p)x+B(p)u
y=C(p)x+D(p)u
withp=(p ,p ,...,p )pdlstabseeksaLyapunovfunctionoftheform
1 2 s
V(x,p)=xTQ −1x, Q(p)=Q +p Q +···+p Q
0 1 1 s s
with symmetric matrices Q ,Q ,...,Q such that dV(x,p)/dt <0 along all ad-
0 1 s
missibletrajectories.
Foratime-invariantpolytopicsystem
Ex˙ =Ax+Bu

| 230 |     | 13 AnalysisandDesignofParameter-DependentSystems |     |     |     |
| --- | --- | ------------------------------------------------ | --- | --- | --- |
y=Cx+Du
with
| (cid:2) | (cid:3)   | (cid:2) | (cid:3) |            |         |
| ------- | --------- | ------- | ------- | ---------- | ------- |
|         | (cid:14)q |         |         | (cid:14)q  |         |
| A+jE    | B         | A +jE   | B       |            |         |
|         | = α       | i i     | i ,     | α ≥0, α =1 | (13.11) |
|         |           | i       |         | i i        |         |
| C       | D         | C i     | D i     |            |         |
|         | i=1       |         |         | i=1        |         |
pdlstabseeksasingleLyapunovfunctionoftheform
| V(x,α)=xTQ(α) |     | −1x, Q(α)=α |     | +···+α      |     |
| ------------- | --- | ----------- | --- | ----------- | --- |
|               |     |             |     | 1 Q 1 q Q q |     |
suchthat dV(x,α)/dt <0 for all polytopicdecompositions(13.11). Notethat for
thistypeofmodelsoneofthematrices A,E shouldbeconstantandtheotherun-
certain.
Similarly to quadstab, the function pdlstab determines whether the suffi-
cientLMIstabilityconditionsarefeasible.
Thesyntaxofthefunctionpdlstabis
| [tau,Q0,Q1,...,Qs] |     | = pdlstab(affsys,options) |     |     |     |
| ------------------ | --- | ------------------------- | --- | --- | --- |
forthecaseofaffineparameter-dependentsystemsand
| [tau,Q1,Q2,...,Qq] |     | = pdlstab(polsys,options) |     |     |     |
| ------------------ | --- | ------------------------- | --- | --- | --- |
forthecaseofpolytopicparameter-dependentsystems.
Inputarguments
– affsysistheaffinesystemdescriptionspecifiedwiththefunctionpsys,which
contains information about the range of values and rate of variation of each pa-
rameterp ;
i
– polsysisthepolytopicsystemdescriptionspecifiedwiththefunctionpsysor
obtainedbythefunctionaff2polfromanaffinemodel;
– options:optionalparameter.
•
| Settingoptions(1) |     | = 0testsrobuststability(default). |     |     |     |
| ----------------- | --- | --------------------------------- | --- | --- | --- |
• When options(2) = 0, pdlstab uses simplified sufficient conditions
forfasterexecution.Setoptions(2) = 1tousetheleastconservativecon-
ditions.
Outputarguments
– tau: a scalar parameter which shows whether the LMI stability conditions are
feasible.Iftauisnegativethenthesystemisstable;
– Q0,Q1,...,Qs:containthecoefficientmatricesQ 0 ,Q 1 ,...,Q s ofthematrix
Q(p)associatedwiththeLyapunovfunctionV(x,p)incaseofaffinemodel;
– Q1,Q2,...,Qq:containthecoefficientmatricesQ ,Q ,...,Q ofthematrix
|     |     |     |     | 1 2 q |     |
| --- | --- | --- | --- | ----- | --- |
Q(α)associatedwiththeLyapunovfunctionV(x,α)incaseofpolytopicmodel.

13.2 AnalysisofParameter-DependentSystems 231
Example 13.2 Consider the mass–damper–spring system whose affine parameter-
dependentmodelpds_mdswascreatedinExample13.1.Forthismodelthecom-
mandline
[tmin,Q0,Q1,Q2,Q3] = pdlstab(pds_mds)
produces
Solver for LMI feasibility problems L(x) < R(x)
This solver minimizes t subject to L(x) < R(x) + t*I
The best value of t should be negative
for feasibility
Iteration : Best value of t so far
1 -0.024610
Result: best value of t: -0.024610
f-radius saturation: 0.000% of R = 1.00e+007
This system is stable for the specified parameter
trajectories
tmin =
-0.0246
Q0 =
1.6750 -0.3994
-0.3994 1.1642
Q1 =
0.8456 -0.0451
-0.0451 -0.0271
Q2 =
0.0543 -0.0989
-0.0989 0.9498
Q3 =
0.6545 -0.7452
-0.7452 -0.0235

232 13 AnalysisandDesignofParameter-DependentSystems
Theresultsshowsthatthemass–damper–springsystemremainsstableforallparam-
etervaluesthatbelongtothespecifiedparameterbox.Notethatalthoughthematri-
cesQ andQ arenotpositivedefinite,thematrixQ(p)=Q +mQ +kQ +cQ
1 3 0 1 2 3
remainspositivedefiniteforthewholeparameterrange.
Thetimeresponseofanaffineparameter-dependentsystem
E(p)x˙ =A(p)x+B(p)u
y=C(p)x+D(p)u
along a given parameter trajectory p(t) and for an input signal u(t) is simulated
by the function pdsimul. The parameter vector p(t) is required to range in a
box (type ’box’ of the function pvec). The function pdsimul also accepts
the polytopic representation of affine parameter-dependent systems as returned by
aff2pol(pds).
Thesyntaxofthefunctionpdsimulis
pdsimul(pds,’traj’,tf,’ut’,xi,options)
or
[t,x,y] = pdsimul(pds,pv,’traj’,tf,’ut’,xi,options)
Wheninvokedwithoutoutputarguments,pdsimulplotstheoutputresponsey(t)
of the affine parameter-dependent system pds. Otherwise, it returns the vector of
integrationtimepointst aswellasthestateandoutputresponsesx,y.Theparame-
tertrajectoryandinputsignalsarespecifiedbytwotimefunctionsp = traj(t)
andu = ut(t).If’ut’isomitted,theresponsetoastepinputiscomputedby
default.Thefinaltimeandinitialstatevectorcanberesetthroughtfandxi(their
respectivedefaultvaluesare5secondsandzerovector).Finally,theinputargument
options givesaccess totheparameterscontrollingthe integrationof thesystem
differentialequations.
Example13.3 Considerthesimulationofthestepresponseofmass–damper–spring
systemforaperiodof30seconds.Theparametertrajectoryischosenas
m(t)=3+1.2e −0.3tcos(10t)
k(t)=2+0.6e −0.3tsin(10t)
c(t)=0.8+0.01t
andisspecifiedinthefiletraj_mds.m.
function p = traj_mds(t)
%
p = [3.0 + 1.2*exp(-0.3*t)*cos(10*t); ...
2.0 + 0.6*exp(-0.3*t)*sin(10*t); ...
0.8 + 0.01*t];

13.2 AnalysisofParameter-DependentSystems 233
Fig.13.3 Parametertrajectoryforsystemsimulation
TheparametertrajectoryisshowninFig.13.3.
The time response of the mass–damper–spring system for the given parameter
trajectoryalongthetimeresponseofthenominalsystemareobtainedbythelines
| [t,x,y]   | = pdsimul(pds_mds,’traj_mds’,30); |        |                |     |
| --------- | --------------------------------- | ------ | -------------- | --- |
| mds_nom   | = psinfo(pds_mds,’eval’,[3        |        | 2 1]);         |     |
| [a,b,c,d] | = ltiss(mds_nom);                 | mds_ss | = ss(a,b,c,d); |     |
tt = 0:0.01:30;
| y_nom = | step(mds_ss,tt); |     |     |     |
| ------- | ---------------- | --- | --- | --- |
figure(1)
| plot(t,y(:,1),’b-’,tt,y_nom,’r--’), |          |     | grid |     |
| ----------------------------------- | -------- | --- | ---- | --- |
| xlabel(’Time                        | (secs)’) |     |      |     |
ylabel(’y’)
| title(’System               | transient | response’)       |     |          |
| --------------------------- | --------- | ---------------- | --- | -------- |
| legend(’Parameter-dependent |           | system’,’Nominal |     | system’) |
BothtimeresponsesareshowninFig.13.4.Comparingwiththestepresponses
ofthemass–damper–springsystemfor20randomvaluesoftheuncertainelements,
showninFig.9.14,weseethattheresponseoftheparameter-dependentsystemis
slightlydifferentfromtheresponseofthenominalsystem.Thisisexplainedbythe
factthatinthelattercasetheparametersm,k,ccorrespondtoagiventrajectoryin
theparameterspaceanddonotvaryindependently.

| 234 | 13 AnalysisandDesignofParameter-DependentSystems |     |     |     |
| --- | ------------------------------------------------ | --- | --- | --- |
Fig.13.4 Timeresponseoftheparameter-dependentsystem
| 13.3 GainScheduling | Designfor | Parameter-Dependent |     | Systems |
| ------------------- | --------- | ------------------- | --- | ------- |
When the system parameters undergo large variations it is often impossible to
achieve high performance and even closed-loop stability over the entire operating
rangewithasingletime-invariantcontroller.Inthiscaseitisappropriatetoapplya
techniquecalledgainscheduling,whichissuccessfullyusedinthecontrolofuncer-
tainortime-varyingsystems.Thistechniqueinvolvesimplementationofafamilyof
controllersdesignedfordifferentregionsoftheparameterspacesoastoguarantee
stabilityandperformanceinthatregion.Duringthesystemoperationthecontrollers
arechangedaccordingtoaphysicalparametermeasuredinrealtimewhichdetects
in what region the system is working in the corresponding moment of the time.
Thechangeofcontrollersisdoneeitherbyinterpolationofcertainparametersorby
switching.Suchcontrollersaresaidtobescheduledbytheparametermeasurements.
Inthissectionweconsiderimplementationofgain-scheduledH
∞controllerswhich
ensures higher performance in the face of large variations in operating conditions
andprovidessmoothchangesbetweencontrollers.
Thesynthesistechniquepresentedinthissectionisapplicabletoaffineparameter-
dependentplantswithstate-spacedescription
⎧
|        | ⎪⎨x˙=A(p)x+B | (p)w+B |      |         |
| ------ | ------------ | ------ | ---- | ------- |
|        |              | 1      | 2 u, |         |
| P(.,p) | z=C (p)x+D   | (p)w+D |      |         |
|        | ⎪⎩ 1         | 11     | 12 u | (13.12) |
|        | y=C x+D      | w+D22u |      |         |
|        | 2            | 21     |      |         |

| 13.3 GainSchedulingDesignforParameter-DependentSystems |     |     |     |     |     |     | 235 |
| ------------------------------------------------------ | --- | --- | --- | --- | --- | --- | --- |
where
|       | (cid:6)     |     | (cid:7) |        |     |              |     |
| ----- | ----------- | --- | ------- | ------ | --- | ------------ | --- |
| p(t)= | p (t),...,p |     | (t) ,   | p ∈[pl | ,pu | ], i=1,...,s |     |
|       | 1           | s   |         | i      | i i |              |     |
is a time-varying vector of physical parameters and A(.),B 1 (.),C 1 (.),D 11 (.) are
affinefunctionsofp(t).Notethatp(t)mayincludepartofthestatevectorx itself
providedthatthecorrespondingstatesareaccessibletomeasurement.Althoughthis
descriptionisnotvalidinthegeneralcasewhenallmatricesarefunctionsofp(t),
itmaybeusedformanysystemsarisinginpractice.
,i=1,...,q
Iftheparametervectorp(t)takesvaluesinaboxwithcornersΠ i
(q=2s)thentheplantSYSTEMmatrix
|     |        | ⎡    |       |          |     | ⎤   |     |
| --- | ------ | ---- | ----- | -------- | --- | --- | --- |
|     |        | A(p) |       | B (p)    | B   |     |     |
|     |        |      |       | 1        |     | 2   |     |
|     | S(p)=⎣ |      |       |          |     | ⎦   |     |
|     |        | C    | 1 (p) | D 11 (p) | D   | 12  |     |
|     |        |      | C     | D        | D   |     |     |
|     |        |      | 2     | 21       |     | 22  |     |
rangesinamatrixpolytopewithverticesS(Π ).Decomposingtheparametervector
i
(cid:14)q
|     | p(t)=α | Π +···+α | Π   | , α | ≥0, | α =1 | (13.13) |
| --- | ------ | -------- | --- | --- | --- | ---- | ------- |
|     |        | 1 1      | q   | q   | i   | i    |         |
i=1
overthecornersΠ i oftheparameterbox,thesystemmatrixS(p)isrepresentedas
|     | S(p)=α | S(Π | )+···+α |     | S(Π | )   |     |
| --- | ------ | --- | ------- | --- | --- | --- | --- |
|     |        | 1   | 1       |     | q   | q   |     |
Thisrepresentationsuggeststoseekaparameter-dependentcontroller
(cid:21)
˙
|     |        | ζ =A | (p)ζ | +B  | (p)y, |     |     |
| --- | ------ | ---- | ---- | --- | ----- | --- | --- |
|     | K(.,p) |      | K    |     | K     |     |     |
|     |        | u=C  | (p)ζ | +D  | (p)y  |     |     |
|     |        |      | K    |     | K     |     |     |
whoseSYSTEMmatrixhasthepolytopicrepresentation
|     | (cid:2) | (cid:3) |     | (cid:2) |     | (cid:3) |     |
| --- | ------- | ------- | --- | ------- | --- | ------- | --- |
(cid:14)q
|     | A (p)   | B (p)   |     | A   | (Π )     | B (Π )     |         |
| --- | ------- | ------- | --- | --- | -------- | ---------- | ------- |
|     | K       | K       | =   |     | K i      | K i        |         |
|     |         |         |     | α i |          |            | (13.14) |
|     | C K (p) | D K (p) |     | C   | K (Π i ) | D K (Π i ) |         |
i=1
Inthisway,foragivenconvexdecomposition(13.13)ofthecurrentparametervec-
torp(t),thecontrollerstate-spacematricesattheoperatingpointp(t)areobtained
byconvexinterpolationofthelineartime-invariantvertexcontrollers
|     |     | (cid:2) |      |     | (cid:3) |     |     |
| --- | --- | ------- | ---- | --- | ------- | --- | --- |
|     |     |         | A (Π | ) B | (Π )    |     |     |
|     |     | K =     | K i  | K   | i       |     |     |
|     |     | i       | C (Π | ) D | (Π )    |     |     |
|     |     |         | K i  | K   | i       |     |     |
ThevaluesofcontrollermatricesA (p),B (p),C (p),D (p)arederivedfrom
|     |     |     | K   | K   | K   | K   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
the values A (Π),B (Π),C (Π),D (Π) at the corners of the parameter box
| K   | K   | K   | K   |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
accordingto
|     | (p)=α |     | )+···+α |     |     |          |     |
| --- | ----- | --- | ------- | --- | --- | -------- | --- |
|     | A K   | 1 A | K (Π 1  |     | q A | K (Π q ) |     |

236 13 AnalysisandDesignofParameter-DependentSystems
Fig.13.5 Gain-scheduled
H∞problem
| B (p)=α | B   | (Π )+···+α | B (Π )       |
| ------- | --- | ---------- | ------------ |
| K       | 1   | K 1        | q K q        |
| (p)=α   |     | )+···+α    |              |
| C K     | 1 C | K (Π 1     | q C K (Π q ) |
| D (p)=α | D   | (Π )+···+α | D (Π )       |
| K       | 1   | K 1        | q K q        |
Thisinterpolationyieldsasmoothschedulingofthecontrollermatricesbythepa-
rametermeasurementsp(t).
Theclosed-loopinterconnectioninvolvingtheparameter-dependentplantP(.,p)
and parameter-dependent controller K(.,p) is shown in Fig. 13.5 where w is the
vector of external input signals and z is the vector characterizing the closed-loop
system behavior.The design goal is to determine a gain-scheduled controller with
the vertex representation (13.14) that stabilizes the closed-loop system for all ad-
missibleparametertrajectoriesp(t)andsuchtheworst-caseclosed-loopgainfrom
w to z does not exceed some prescribed level γ >0. Controllers that satisfy this
aimarecalledH ∞ gainscheduledcontrollers.
Thedesignof H gain-scheduledcontrollersis donebythefunctionhinfgs
∞
which finds the desired controller by solving 2s LMIs (see for details [9, 50,
Chap.7]).Thesyntaxofthisfunctionis
[gopt,pdK] = hinfgs(pdP,r)
TheinputofthefunctionconsistsoftheaffineorpolytopicmodelpdPoftheplant
13.12 and the vector r=[p2 m2] specifying the dimensions of the output y and
control u,respectively.Onoutput,goptisthebestachievablewithrespecttopa-
rametervariationsclosed-loopH normandpdKisapolytopicsystemconsisting
∞
ofthevertexcontrollers
|     | (cid:2) |            | (cid:3)  |
| --- | ------- | ---------- | -------- |
|     | = A     | K (Π i ) B | K (Π i ) |
K
|     | i C | (Π ) D | (Π ) |
| --- | --- | ------ | ---- |
|     |     | K i    | K i  |
Foragivenvaluepoftheparametervectorp(t),thecorrespondinggain-scheduled
controller
|     |     | (cid:2) | (cid:3) |
| --- | --- | ------- | ------- |
|     |     | A K (p) | B K (p) |
K(p)=
|     |     | C (p) | D (p) |
| --- | --- | ----- | ----- |
|     |     | K     | K     |
isdeterminedbyenteringthecommandlines

| 13.3 GainSchedulingDesignforParameter-DependentSystems |     |     |     |     |     |     |     | 237 |
| ------------------------------------------------------ | --- | --- | --- | --- | --- | --- | --- | --- |
alpha = polydec(pv,p)
Kp = psinfo(pdK,’eval’,alpha)
(cid:26)
Here,thefunctionpolydeccomputestheconvexdecompositionp(t)= q α Π
i=1 i i
producing as an output(cid:26)the vector alpha = (alpha_1, ..., alpha_q).
q
The controller K(p)= α K corresponding to the vector p is obtained as a
|     |     | i=1 | i i |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
SYSTEMmatrixbythefunctionpsinfo.
Apolytopicmodeloftheclosed-loopsystemmaybefoundbythefunctionslft
usingthecommandline
pcl = slft(pdP,pdK)
For a given parameter value p of p(t) the closed-loop system is evaluated by the
line
pcl_t = psinfo(pcl,’eval’,polydec(pv,p))
Theclosed-looptimeresponseisobtainedby
pdsimul(pcl,’trajfun’,tf,’inputfun’)
wherepclisthepolytopicrepresentationoftheclosed-loopsystemandtfisthe
desireddurationofthesimulation.Thefunctionstrajfuninputfundefinethe
desiredparametertrajectoryandinputsignals,respectively,asfunctionofthetime.
Iftheparameter’inputfun’isomitted,thepdsimulplotsthestepresponseby
default.
H
Example 13.4 This example presents the design of an ∞ gain-scheduled con-
trollerforahydroturbinepowerunitinthecaseofwiderangepowervariation.
Assumingarigidconduitandincompressibleflow,theturbineandpenstockchar-
acteristics are determined by three basic equations relating to the velocity of the
waterinthepenstock,theturbinemechanicalpower,andtheaccelerationofwater
column[88].Wehave
√
|     |     |     | U =k | G   | H   |     |     |     |
| --- | --- | --- | ---- | --- | --- | --- | --- | --- |
u
=k
|     |     |     | P m | p HU |     |     | (13.15) |     |
| --- | --- | --- | --- | ---- | --- | --- | ------- | --- |
dU
|     | (ρLA | )   | =−A | (ρa | )(H | −H ) |     |     |
| --- | ---- | --- | --- | --- | --- | ---- | --- | --- |
|     |      | p   |     | p   | g   | 0    |     |     |
dt
where U is the water velocity; G gate opening, H hydraulic head at gate, k a
u
proportionalitycoefficient,P turbinemechanicalpower,k turbineefficiency,H
|     |     | m   |     |     |     | p   |     | 0   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
initial steady-state value of H, A pipe area, L length of the penstock, ρ mass
p
density, a acceleration due to gravity, ρa (H −H ) static pressure deviation at
| g   |     |     |     | g   |     | 0   |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
turbinegate.
Todescribethedynamicsofthehydroturbineinwiderangeofoperationalcondi-
tions,itisconvenienttorepresent(13.15)innormalizedform,basedonsteady-state
operatingvaluesofthecorrespondingvariables.Setting
|     | U   |     | G   |     | H   |     | P   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ¯   | =   | ¯   | =   |     | ¯ = | ¯   | = m |     |
| U   | ,   | G   | ,   | H   | ,   | P   | m   |     |
|     | U   |     | G   |     | H   |     | P   |     |
|     | 0   |     | 0   |     | 0   |     | m0  |     |

| 238 | 13  | AnalysisandDesignofParameter-DependentSystems |     |     |
| --- | --- | --------------------------------------------- | --- | --- |
wherethesubscript0referstoinitialsteady-statevalues,(13.15)arewrittenas
|     |     | (cid:6)      | (cid:7) |         |
| --- | --- | ------------ | ------- | ------- |
|     |     | H ¯ = U ¯ /G | ¯ 2     |         |
|     |     | ¯ ¯ ¯        |         |         |
|     |     | P =U H       |         | (13.16) |
m
|     |     | ¯ (cid:6) | (cid:7) |     |
| --- | --- | --------- | ------- | --- |
|     |     | dU        | ¯       |     |
|     | T   | =− H      | −1      |     |
w
dt
where
LU
|     |     | T = | 0   | (13.17) |
| --- | --- | --- | --- | ------- |
w
|     |     | a g H | 0   |     |
| --- | --- | ----- | --- | --- |
isthewaterstartingtimeatanyload.ItrepresentsthetimerequiredforaheadH
0
toacceleratethewaterinthepenstockfromstandstilltothevelocityU 0 .Thevalue
ofT atratedloadiscalledwaterstartingtimeatratedloadandisdenotedbyT .
w W
This time constant has a fixed value for a given turbine-penstock unit and can be
obtainedfrom
LQ r
|     | T   | =     |     |     |
| --- | --- | ----- | --- | --- |
|     |     | W a A | H   |     |
|     |     | g     | p r |     |
=A
where Q r p U r is the water-flow rate at rated load and U r ,H r are the water
velocityandhydraulicheadatratedload,respectively.
Incaseofsmallsignaldeviationsabouttheoperationpoint,thelinearizedrepre-
sentationof(13.16)is
|     | ΔU  | ¯ =ΔG ¯ | +0.5ΔH ¯ |         |
| --- | --- | ------- | -------- | ------- |
|     |     | ¯ ¯     | ¯        |         |
|     | ΔP  | =ΔH     | +ΔU      | (13.18) |
m
|     | dΔU | ¯    |     |     |
| --- | --- | ---- | --- | --- |
|     |     | =−ΔH | ¯   |     |
T
w dt
Aftersomealgebraicmanipulationsof(13.18)thetransferfunctionbetweenthe
gateopeningpositionandtheturbinemechanicalpowerisobtainedas
|     |      | −T s+1   |     |         |
| --- | ---- | -------- | --- | ------- |
|     | ¯    | = w      | ¯   |         |
|     | ΔP m |          | ΔG  | (13.19) |
|     |      | 0.5T s+1 |     |         |
w
Itcanbeseenthatthelinearizedmodeltransferfunctiondependsonthetimecon-
stant T , which varies with load, i.e., it has to be considered as a varying system
w
parameter.
Denoting the power reference value as P =k H U , it is possible to obtain
|     |     |     | 0 p 0 0 |     |
| --- | --- | --- | ------- | --- |
from(13.17)arelationshipbetweenthetimeconstantT w andthenormalizedpower
¯
referenceP =P /P ,whereP =k H U istheturbinepoweratratedload.Asa
| 0 0 r | r   | p r r |     |     |
| ----- | --- | ----- | --- | --- |
resultwehave
¯
|     | ¯      | P 0 | LP r    |         |
| --- | ------ | --- | ------- | ------- |
| T   | (P )=k | ,   | k=      | (13.20) |
| w   | 0      | ¯ 2 | a k H 2 |         |
|     |        | H   | g p r   |         |
0

13.3 GainSchedulingDesignforParameter-DependentSystems 239
whereH ¯ =H /H .Equation(13.20)showsthatthetimeconstantT isafunction
0 0 r w
¯
ofthepowerreferencevalueP whichchangesduringthehydroturbineoperation.
0
Thevariationofthistimeconstantleadstovariationsofturbinemodelwhichshould
beconsideredasaparameter-dependentmodel.Takingintoaccount(13.20)thefol-
lowingplantmodelisobtained:
ΔP ¯ = −T w (P ¯ 0 )s+1 ΔG ¯ (13.21)
m 0.5T (P ¯ )+1
w 0
Furtheronweshallmakeuseofthefollowingdatarelatedtotheturbine,penstock
andgeneratorofthehydrogeneratingunit:penstocklength900m;ratedhydraulic
head150m;initialhydraulichead1m;pipingarea8.5m2;watervelocityatrated
load7.65m/s;waterflowrateatratedload65m3/s;gateopeningatratedload0.96;
gateopeningatnoload0.02.
Theservosystemopeningtheturbinegateisassumedtohavethedescription
ΔG ¯ (s)= 1 Δu¯(s)
T s+1
s
whereu¯ isthenormalizedservosystemreferencesignalandT =3s.Incorporating
s
thisdynamicsintheplantequationsweobtain
(cid:6) (cid:7)
P ¯ (s)=W s,P ¯ u¯(s)
m o
¯
wherethetransferfunction W(s,P ) relatingthecontrolsignalandthehydrotur-
o
binepowerisobtainedas
W (cid:6) s,P ¯ (cid:7) = 1 (−T w (P ¯ 0 )s+1) (13.22)
o (T s s+1)(0.5T w (P ¯ 0 )s+1)
Introducingthestateandoutputvectors
(cid:4) (cid:5)
x(t)= ΔG ¯ (t) ΔP ¯ (t) T , y(t)=P ¯ (t)
m m
oneobtainsthestatespacedescription
(cid:6) (cid:7)
x˙(t)=A P ¯ x(t)+Bu(t) (13.23)
0
y(t)=Cx(t) (13.24)
where
(cid:30) (cid:31) (cid:30) (cid:31)
(cid:6) (cid:7) −1 0 1 (cid:4) (cid:5)
A P ¯ = Ts , B= Ts , C= 0 1
0 2 + 2 − 2 −2
Ts Tw Tw Ts
Thesystem(13.23),(13.24)mayberepresentedastheparameter-dependentsystem
x˙ =A(p)x+B(p)u (13.25)

| 240 |     |     | 13  | AnalysisandDesignofParameter-DependentSystems |     |     |
| --- | --- | --- | --- | --------------------------------------------- | --- | --- |
y=C(p)x+D(p)u
(13.26)
whichisaffineintheuncertainparameter
2
p=
(13.27)
T
w
Infact,usingthesetting(13.27),thesystemmatricesmaybewrittenas
|     |     | A(p)=A | +pA |     | B(p)=B | +pB |
| --- | --- | ------ | --- | --- | ------ | --- |
|     |     |        | 0   | 1 , |        | 0 1 |
|     |     | C(p)=C | +pC | ,   | D(p)=D | +pD |
|     |     |        | 0   | 1   |        | 0 1 |
where
|     |     |     | (cid:30) | (cid:31) |         |         |
| --- | --- | --- | -------- | -------- | ------- | ------- |
|     |     |     |          |          | (cid:2) | (cid:3) |
|     |     |     | 1        | 0        |         |         |
|     |     |     | T        |          |         | 0 0     |
|     |     | A   | = s      | ,        | A =     |         |
|     |     | 0   | 1        |          | 1       | 1 −1    |
0
Ts
|     |     |     | (cid:30) | (cid:31) | (cid:2) (cid:3) |     |
| --- | --- | --- | -------- | -------- | --------------- | --- |
1
0
|     |     | B   | = Ts | , B | =   |     |
| --- | --- | --- | ---- | --- | --- | --- |
|     |     | 0   |      |     | 1   |     |
|     |     |     | 2    |     | 0   |     |
Ts
|     |     |     | (cid:4) | (cid:5) | (cid:4) | (cid:5) |
| --- | --- | --- | ------- | ------- | ------- | ------- |
|     |     | C   | = 0     | 1 ,     | C = 0   | 0       |
|     |     | 0   |         |         | 1       |         |
|     |     |     | =0,     | =0      |         |         |
|     |     | D   | 0       | D 1     |         |         |
Assumingthatthenormalizedpowerreferencevariesintheinterval [0.1,1.0],the
variesintherange[0.46771,4.6771].Hencetheuncertainparam-
| timeconstantT | w   |     |     |     |     |     |
| ------------- | --- | --- | --- | --- | --- | --- |
eterpvariesbetweenthevalues2/4.6771and2/0.46771.
Theaffineparameter-dependentsystemmodelisobtainedinthevariablepdsby
thelines
| A_0 = [-1/Ts |     | 0;2/Ts | 0];  | B_0 | = [1/Ts | -2/Ts]’; |
| ------------ | --- | ------ | ---- | --- | ------- | -------- |
| C_0 = [0     | 1]; | D_0    | = 0; |     |         |          |
S_0 = ltisys(A_0,B_0,C_0,D_0,1);
%
| A_p = [0 | 0;1 | -1]; | B_p  | = [0 | 0]’; |     |
| -------- | --- | ---- | ---- | ---- | ---- | --- |
| C_p = [0 | 0]; | D_p  | = 0; |      |      |     |
S_p = ltisys(A_p,B_p,C_p,D_p,0);
%
| % determine |     | the range | of  | time | constant | Tw  |
| ----------- | --- | --------- | --- | ---- | -------- | --- |
P0 = 1.0;
Tw1 = L*P0*Pr/(ag*kp*Hr^2);
P0 = 0.1;
Tw2 = L*P0*Pr/(ag*kp*Hr^2);
%
| pv = pvec(’box’,[2.0/Tw1 |     |     |        | 2.0/Tw2]); |     |     |
| ------------------------ | --- | --- | ------ | ---------- | --- | --- |
| pds = psys(pv,[S_0       |     |     | S_p]); |            |     |     |

13.3 GainSchedulingDesignforParameter-DependentSystems 241
Fig.13.6 Closed-loop
system
Thedesignofgain-scheduledcontrollerofthehydroturbinesystemisdoneac-
cordingtotheblockdiagramshowninFig.13.6andresemblesthemixed-sensitivity
H ∞design.A2-degree-of-freedomcontrollerisusedtoachievebetterperformance.
Theopen-loopplantinterconnectionisobtainedbythecommandline
[pdP,nmc] = sconnect(’r’,’e=r-G(1);K’,’K:[r;G]’,
’G:K’,pds);
Theargumentsofthefunctionsconnecthavethefollowingmeaning.
– Thefirstinputargument’r’isthescalarreferencesignalr.
– Thesecondargument’e=r-G(1);K’specifiestwooutputsignalsseparatedby
asemicolon.Thesesignalsarethedifferencer−y betweenreferenceandplant
output,andthecontrolactionu.
– Thethirdargument’K:[r;G]’namesthecontrollerandspecifiesitsinputs.In
thegivencasea2-degrees-of-freedomcontrollerisusedwithinputsr andy.
– Theremainingargumentscomeinpairsandspecify,foreachsystemintheloop,
its input list and its SYSTEM matrix. Here ’G:K’ means that the input of G is
theoutputofK,andttpdsistheSYSTEMmatrixofG(s).
Thedesignaimistofulfillthemixed-sensitivityrequirement
(cid:24)(cid:2) (cid:3)(cid:24)
(cid:24) (cid:24)
(cid:24) (cid:24) W p S (cid:24) (cid:24) <1
W KS
u ∞
Theperformanceandcontrolweightingfunctionsarechosenas
4s+1 1.2s+1
W (s)=1.6 , W (s)=0.4
p 60s+0.01 u 0.0024s+1
respectively, in order to achieve good transient response respecting the constraint
onthecontrolaction.Theseweightingfunctionsareappendedtotheplantintercon-
nectionbytheline
Paug = smult(pdP,sdiag(Wp,Wu,eye(2)));
wherethefunctionsdiagformsablock-diagonalmatrixwithW ,W andtheunit
p u
2×2matrixonthediagonalandsmultmultipliestheparameter-dependentplant
pdPwiththismatrix.Nowthepolytopicgain-scheduledcontrollerwithtwofourth

242 13 AnalysisandDesignofParameter-DependentSystems
Fig.13.7 Variationofthesystemparameter
ordervertexsystemsK andK isobtainedinthevariablepdKbytheline
1 2
[gopt,pdK] = hinfgs(Paug,nmc)
andthecorrespondingclosed-loopsystemis
pCL = slft(pdP,pdK)
Thesimulationoftheclosed-loopsystemisdonebythefunctionpdsimul.Inor-
dertosetdifficultconditionsforcontrollerwork,theparametertrajectoryischosen
tovaryasshowninFig.13.7.Thetrajectoryissetinthefiletraj_ht.Thetran-
sient response of the closed-loop system for this parameter trajectory is computed
foratimeperiodof100sbythelines
tf = 100;
[t,x,y] = pdsimul(pCL,’traj_ht’,tf);
Thestepresponseoftheclosed-loopsystemisshowninFig.13.8.Althoughthepa-
rameterT variesrapidlywhichleadstoquickvariationsofthecontroller,thetran-
w
sientresponseissatisfactory.ThecorrespondingcontrolactionisshowninFig.13.9.
The Simulink® model Hinf_GS_Control of the closed-loop system involving
thenonlinearplantmodelandthegain-scheduledcontrollerisshowninFig.13.10.
Themodelofthegain-scheduledcontroller
K(p)=α K +α K
1 1 2 2
including the two vertex time-invariant controllers K and K , is shown in
1 2
Fig. 13.11. For given value of the scheduling parameter T , computed from the
w

13.3 GainSchedulingDesignforParameter-DependentSystems 243
Fig.13.8 Stepresponseoftheclosed-loopsystem
Fig.13.9 Closed-loopcontrolaction

244 13 AnalysisandDesignofParameter-DependentSystems
Fig.13.10 Simulinkmodeloftheclosed-loopsystem
Fig.13.11 Simulinkmodelofthegain-scheduledcontroller

13.3 GainSchedulingDesignforParameter-DependentSystems 245
Fig.13.12 Transientresponseoftheclosed-loopsystem
Fig.13.13 Closed-loopcontrolaction

246 13 AnalysisandDesignofParameter-DependentSystems
desired power reference P , the polytopic coordinates α and α are evaluated in
0 1 2
thefunctionalpha_evalbytheline
alpha = polydec(pv,2.0/Tw);
Theclosed-loopsystem simulationisdonefor different valuesofthepowerrefer-
ence in the range 0.3–0.9 and for a period of time equal to 450 s. The simulation
resultsareplottedbythefunctionplot_simul_results.Thevariationofthe
referencesignalandthecorrespondingclosed-looptransientresponseareshownin
Fig.13.12.Itisseenthatthebehaviorofthenonlinearclosed-loopsystemisclose
to the behavior of the linear system whose step response was shown in Fig. 13.8.
Theclosed-loopcontrolaction,showninFig.13.13,variesintheinterval[0, 0.9].
13.4 Exercises
Exercise 13.1 Analyze the quadratic stability of the mass–damper–spring system
usingthefunctionquadstab.
Exercise 13.2 For the plant described in Example 13.4 try to find a μ-controller
that ensures robust stability and robust performance of the closed-loop system for
thesamerangeofvariationofthetimeconstantT .
w

Part III
Design Examples

Chapter 14
Robust Control of a Hard Disk Drive
This chapter considers the design of a robust servo system of a hard disk drive
(HDD).Threerobustdesignmethodsareapplied,namely,theμ-synthesis,H ∞op-
timaldesignandthe H ∞ loop-shapingdesignprocedure(LSDP).Afteradescrip-
tion of the HDD servo-system dynamics in Sect. 14.1, it is shown (in Sect. 14.2)
howtoderivetheplantmodelthatinvolvesseveraluncertainparameters.Thenwe
consider the synthesis of continuous-time controllers using the available methods
for robust control design. These controllers are compared in aspects of robustness
ofclosed-loopsystemstabilityandofperformanceinthefrequencydomainandin
the time-domain. The design of discrete-time controller is also included, for two
sampling frequencies. Finally, we present the simulation results of the nonlinear
continuous-timeanddiscrete-timeclosed-loopsystems,followedbyconclusionsat
theendofthechapter.
Theprevalenttrendinhard-diskdesignistowardssmallerdiskswithincreasingly
largercapacities.Thisimpliesthatthetrackwidthhastobesmallerleadingtolower
error tolerance in the positioning of the read/write heads. The controller for track
followinghastoachievetighterregulationinthepresenceofparametervariations,
nonlinearitiesandnoises.Hence,itisappropriatetouseadvanceddesignmethods
likeμ-synthesisandH ∞optimizationinordertoachieverobuststabilityandrobust
performanceoftheclosed-loopservosystem.
14.1 HardDiskDriveServo System
The schematic diagram of a typical hard disk drive is shown in Fig. 14.1. The
disk assembly consists of several flat disks called platters coated on both sides
with very thin layers of magnetic material (thin-film media). The magnetic mate-
rial is used to store the data in the form of magnetic patterns. The platters rotate
at high speed, driven by a spindle motor. Recently, the spindle speed has become
5400 r.p.m., 7200 r.p.m. or even 10,000 and 15,000 r.p.m. The data are retrieved
from,orrecordedonto,theplattersbyelectromagneticread/write(R/W)headsthat
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 249
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_14,©Springer-VerlagLondon2013

250 14 RobustControlofaHardDiskDrive
Fig.14.1 Schematicdiagramofaharddiskdrive
are mounted at the bottom of sliders. Today’s hard disks read data using giant-
magneto-resistive(GMR)headsandwritedatawiththin-filminductiveheads.The
sliderswithread/writeheadsaremountedontoheadarms.Thearmsarelightweight
rigidconstructionsallowingthemtobemovedrapidlyontheplattersurface.There
is one arm per read/write head and all arms are mounted in a stack assembly that
moves over multiple disk surfaces simultaneously. The heads are suspended less
than1microinchabovethedisksurface.Theappropriateflyingheightoftheheads
isachievedthankstotheairflowgeneratedbythespinningdisk.
Thedatarecordedontheplattersareinconcentriccirclescalledtracks.Modern
harddiskshavetensofthousandsoftracksresultingintrackdensity35,000tracks
per inch (TPI) or more. Thus, the distance between adjacent tracks is less than a
microinch.Eachtrackisdividedintosmallerpiecescalledsectorsthatcontain512
bytesof information.There maybe several hundredsor even thousandsof sectors
in a track. The drive density may reach several hundreds GB per platter (1 GB=
109bytes).
Theheadarmsaremovedonthesurfaceoftheplatterbyarotaryvoicecoilac-
tuatorfrequentlycalledtheVoiceCoilMotor(VCM).TheVCMconsistsofavoice
coil,mountedattheendoftheheadarmassembly,andpermanentelectromagnets.
By controlling the current in the coil, the heads can move in one direction or the
otherinordertofollowpreciselythedatatrack.

14.1 HardDiskDriveServoSystem 251
Thegoaloftheharddiskdriveservocontrolsystemistoachieveaprecisepo-
sitioningoftheread/writeheadsonthedesiredtrack(track-followingmode)while
data are being written or read, and a quick transition from one track to another
target track (seeking mode). As the drive initiates a seek command, it switches to
a seek control algorithm that is a type of time-optimal (bang-bang) control algo-
rithm. When the head is positioned over the desired track, the drive switches into
track-following mode. In the present work we consider the servo controller of the
track-followingmode.
Allmodernharddiskdrivesreadtherelativepositionoftheheadtotrackdirectly
fromthediskmediabyusingamethodcalledembeddedservoorsectorservo.For
this method the servo information is interleaved with user data across the entire
surface of all platters. Position information is placed on the disk surfaces in servo
frames during the manufacturing of the disk and cannot be rewritten. This is why
thediskheadsarelockedoutbythedrivecontrollerfromwritingtotheareaswhere
servoinformationiswritten.Becauseoftheinterleavingofservoinformationwith
data,theembeddedservosystemisasampled-datasystem.Increasingthenumber
ofservoframeswithinatrackimprovestheperformanceoftheservosystemdueto
thehighersampleratebutlimitsthemaximumdatastorage.Theservoinformation
isreadbythesameheadthatreadsthedata.Thepositioninformationusuallycon-
sistsoftwoparts:coarsepositiongivingtracknumberandfinepositioninformation
relative to each track. The position error, representing the difference between the
referencetrackpositionandtheheadposition,ismeasuredbymakinguseofposi-
tionburststhatarepartoftheservoinformation.Thepositionburstsarepatternsof
alternatingmagneticpolaritywrittenonthedisksurfacewithaparticularfrequency.
Theperiodicsignal,obtainedfromthereadheadpassingoveraburstpattern,hasan
amplitudethatisproportionaltohowmuchthereadheadisdirectlyovertheburst
pattern.Thesignalscorrespondingtotwoorfourburstsofpositioninformationare
demodulatedbyaservodemodulatorinordertocomposethepositionerrorsignal
(PES). This signal is used by the servo controller to change the voice coil current
appropriatelyandhencetheread/writeheadsposition.Itshouldbepointedoutthat
the absolute head position is not generally known from the servo information that
isreadoffofthedisk.Onlyasignalproportionaltothepositionerrorisavailable,
whichmeansthatfortrackfollowingthereferencesignalisideallyequaltozero.
The failure of the head to follow the track on a platter surface faithfully as the
disk spins is referred to as runout. The runout could have serious consequences,
especiallyduringwritingwheredatainadjacenttracksmightbeoverwritten.There
are two types of runout, namely the repeatable runout (RRO) and nonrepeatable
runout(NRRO).Repeatablerunoutiscausedbybothimbalanceinthespindleand
imperfections in the servowriting process that result in noncircular position infor-
mation.Thisinformationisencodedatthespindlefrequency,yieldingarepeatable
noncirculartrackforthediskservotofollow.Thenonrepeatablerunoutiscausedby
a windageinducedactuatorarm,slidermotionandmechanicalvibrationsthat can
arisefromvarioussourcessuchasballbearingdefects,spindlemotorvibrationsand
slider vibrations. The RRO may be reduced through feedforward compensation at
thecorrespondingfrequencybyusingharmoniccorrectors.

252 14 RobustControlofaHardDiskDrive
Fig.14.2 Block-diagramoftheharddiskdriveservosystem
The block-diagram of the HDD servo system is shown in Fig. 14.2. The R/W
headsaremovedbyaVCMthatisdrivenbytheoutputcurrent i ofapoweram-
c
plifier (PA). The actual position signal y is compared with the signal y , which
ref
represents the desired head position. For the track following, the reference input
y is theoretically equal to zero and y(t) appears as an error signal. In practice,
ref
y mustbesetequaltothesignalrepresentingbothRROandNRRO.Thedigital
ref
signal y is a reference for the desired track and is used during the seeking mode.
r
Theerrorsignalissampledbyananalogue-to-digital(A/D)converterandservesas
partofaninputtothedigitalservocontrollerK thatistypicallyimplementedona
d
digitalsignalprocessor(DSP)chip.Theoutputofthecontrollerisconvertedtoana-
logue form by a digital-to-analog(D/A) converter and amplifiedby the PA. Since
themotortorqueisproportionaltothevoicecoilcurrent,theamplifierisconfigured
asacurrentsource.Theexogenoussignalt isthetorquedisturbanceduetoexter-
d
nalshockandvibrations,poweramplifiernoise,digital-to-analogueconverternoise,
pivotbearingfrictionandflexcablebias.Theincreaseofthespindlespeedincreases
the air flow inside the disk (windage) that in turn increases the disturbance torque
ontheactuator.Thedisturbanceisalow-frequencysignalwithspectralcontentusu-
allybelow500Hz.Thepositionnoisesignalη includesquantizationerrorsdueto
servodemodulatornoise,finiteresolutionoftheanalogue-to-digitalconverter,me-
dianoiseandpreamplifiernoise.Thepositionnoiseisahigh-frequencysignalwith
spectralcontentusuallyabove1kHz.SincethemeasuredPESiscontaminatedwith
noise,thetruePES,y −y,isnotavailable.
ref
One of the limitations inherent in the design of servo controllers for high track
densityHDDis the influenceof actuatormechanicalresonantmodes on the head-
positioning servo. If the actuator input contains a periodic component with fre-
quency equal to a resonance frequency, this component may be amplified greatly
thatresultsinlargeoff-trackdeviationoftheread/writeheads.Usually,theactuator
ismechanicallydesignedinsuchawaythattheresonantmodesoccuratfrequencies
thatwillbeattenuatedbytheservosystem.However,asservobandwidthincreases

| 14.1 HardDiskDriveServoSystem |     |     | 253 |
| ----------------------------- | --- | --- | --- |
Table14.1 Rigidbodymodelparametersandtolerances
| Parameter Description | Value       | Units | Tolerance |
| --------------------- | ----------- | ----- | --------- |
| J armmomentofinertia  | 6.3857×10−6 | kg m2 | ±10.0%    |
5.08×10−2
| R armlength |     | m   | ±0.1% |
| ----------- | --- | --- | ----- |
±0.0%
| kPA amplifiergain          | 10.0       | V/V     |        |
| -------------------------- | ---------- | ------- | ------ |
| kt VCMtorqueconstant       | 9.183×10−2 | Nm/A    | ±10.0% |
|                            | 9.183×10−2 |         | ±10.0% |
| kb backe.m.f.constant      |            | Nm/A    |        |
| tpm trackspermeter         | 106        | tracks  | –      |
| ky positionmeasurementgain | 1.2        | V/track | ±5.0%  |
±20.0%
| Rcoil coilresistance         | 8.00 | (cid:2) |       |
| ---------------------------- | ---- | ------- | ----- |
| Rs senseresistanceinthepower | 0.2  | (cid:2) | ±1.0% |
amplifierfeedback
+0, −15%
| Lcoil coilinductance                | 0.001 | H       |         |
| ----------------------------------- | ----- | ------- | ------- |
| emax saturatedpoweramplifiervoltage | 12.0  | V       | −0, +5% |
| RPM diskrotationrate                | 7200  | rev/min | ±1.0%   |
±1.0%
| tw trackwidth | 1   | µm  |     |
| ------------- | --- | --- | --- |
tomeethigherperformancerequirements,thisattenuationmaynotbeachieveddue
tomechanicaldesignconstraints.Itisalsoimportanttonotethatthepresenceofres-
onantmodesmaylimittheservobandwidthviastabilitymarginconstraints.Witha
reducedbandwidth,theservosystemmaynotbeabletoachievethedesiredperfor-
mance.
Therotaryactuatorsofharddisksmayhavetensofresonancesthatmayleadto
ahighordermodel.However,inpracticeonly3tofourmainresonancesaretaken
into account. Usually, these are the first and second torsion modes (in the range
1500–2500Hz)aswellasthefirstswaymode(intherange8000–12000Hz).
A common approach to reduce the effect of resonance modes is to put notch
filtersintheservoloopthatattenuatesorfiltersoutvibrationsatselectedmajorres-
onant frequencies. However, each notch filter introduces phase margin loss at low
frequenciesthusreducingthesystemrobustness.Also,thepresenceofuncertainty
intheresonantmodesmaydecreasesignificantlytheefficiencyofthosefilters.
Ourgoalinthischapteristodesignarobusttrack-followingservocontrolsys-
temfora3.5-inchHDDwithtrackdensity25,400TPI.Thedesiredsettlingtimeis
about1msinthepresenceoffourresonances,severaluncertainparameters,position
sensing noise and disturbances. The parameters of the rigid-body model and their
tolerancesaregiveninTable14.1.Fordimensionalcompatibility,thetrackdensity
isgivenintrackspermeter,insteadofinTPI.
WenowfirstconsiderthederivationofaHDDservosystemmodel.
Thedynamicsoftherotaryarmisdescribedbytheequation
d2Θ
=t +t
J
dt2 m d

254 14 RobustControlofaHardDiskDrive
Fig.14.3 Blockdiagramofthepoweramplifierwithvoicecoil
whereJ isthearmmomentofinertia,Θ istheangleofarmrotation,t istheVCM
m
torque,andt isthedisturbancetorque.
d
TheVCMtorqueisgivenby
t =k i
m t c
wherek isthemotortorqueconstantandi isthecurrentthroughtheVCMcoil.
t c
ThevoicecoilhasaresistanceR andaninductanceL .Anadditionalcur-
coil coil
rent sense resistance R is connected in serial with the voice coil to implement a
s
feedback from the power amplifier output. Hence the voice coil admittance is de-
scribedbythetransferfunction
i (s) 1/R
G (s)= c = c
vca e (s) τs+1
c
wheree istheinputvoltagetothevoicecoil,τ =L /R andR =R +R .
c coil c c coil s
TheblockdiagramofthepoweramplifierwithvoicecoilisshowninFig.14.3.
The input of the voice coil is the difference e =e −e , where e is the output
c p b p
voltageoftheamplifierande =k ωisthebackelectromotiveforce(e.m.f.)thatis
b b
generatedduringthemovingofthecoilinthemagneticfield.Sincethesaturation
voltage of the amplifier is e , in the absence of back e.m.f., the amplifier will
max
saturate for an input voltage greater than e /k . In the study limited to linear
max PA
systems,theamplifiersaturationisneglected.
Thelengthofthearc,correspondingtothearmrotationangleΘ,isequaltoRΘ.
ForsmallvaluesofΘ thenumberoftrackscontainedinthearcisR·Θ·tpm.This
givesanoutputsignaly=R·tpm·k ·Θ.
y
Ifweneglectthedynamicsofthevoicecoil,thetransferfunctionoftheservoac-
tuatorconsideredasarigidbodyisobtainedintheformofadoubleintegrator.Such
a modeloversimplifiesthe systemdynamicsand cannotproducereliableresults if
usedinthedesign.

14.2 DerivationofUncertaintyModel 255
Fig.14.4 Transferfunctions
ofresonantmodes
The next step is to take into account the high-frequency resonant modes of the
head disk assembly represented by the transfer function H (s). In the given case
d
H (s)consistsoffourresonantmodesandisobtainedas
d
H (s)= (cid:14)4 b 2j ω j s+b 2j−1 ω j 2
d s2+2ξ ω s+ω2
j=1 j j j
(seeFig.14.4).
Hereω j , ξ j andb 2j , b 2j−1 are,respectively,theresonancefrequency,thedamp-
ingcoefficientandthecouplingcoefficientsofthejthmode,forj =1,...,4.The
resonanceparametersareusuallydeterminedexperimentallyandfortheservosys-
temunderconsiderationtheirvaluesareshowninTable14.2.
Itisimportanttonotethatallmodelparametersareknownwithsometolerances
andmayvarywiththechangingofworkingconditionsaswellaswithtime.Also,
theclosed-loopsystemcanbeverysensitivetotheexternaldisturbancet andthe
d
position-sensingnoiseη.Bothfactorswouldleadtoanactualsystemdynamicsfar
awayfromthedynamicsofthenominalclosed-loopsystem.Thus,itisnecessaryto
usecontrol-systemdesignmethodsthatensurethedesiredclosed-loopstabilityand
performanceinthepresenceofuncertainparameters,noises,anddisturbances.
14.2 Derivationof UncertaintyModel
In order to implement robust control design methods we must have a plant model
that incorporates uncertain parameters. As is seen from Tables 14.1 and 14.2, the
totalnumberofuncertainparametersisgreaterthan25,whichcomplicatestheanal-
ysisanddesignofaHDDservosystem.Inthisstudy,weshallconcentrateonthose
uncertaintyparametersthatinfluencetheclosed-loopsystembehaviormost.Byus-
ingthefunctionurealwedefinetherealuncertainparameters
J,K ,K ,ω ,ω ,ω ,ω ,ξ ,ξ ,ξ ,ξ
t y 1 2 3 4 1 2 3 4
Theblock-diagramoftheplantisshowninFig.14.5.

| 256                                        |                         | 14 RobustControlofaHardDiskDrive |                 |
| ------------------------------------------ | ----------------------- | -------------------------------- | --------------- |
| Table14.2 Resonanceparametersandtolerances |                         |                                  |                 |
| Parameter                                  | Description             | Value                            | Units Tolerance |
| ω1                                         | pivotbearingresonance   | 2π50                             | rad/s ±5.0%     |
| ω2                                         | firsttorsionalresonance | 2π2200                           | rad/s ±12.0%    |
±8.0%
| ω3  | secondtorsionalresonance | 2π6400 | rad/s        |
| --- | ------------------------ | ------ | ------------ |
| ω4  | firstswayresonance       | 2π8800 | rad/s ±15.0% |
±7.0%
| b1  | firstresonancecoupling  | 0.006 | –         |
| --- | ----------------------- | ----- | --------- |
| b2  | firstresonancecoupling  | 0     | 1/s ±7.0% |
| b3  | secondresonancecoupling | 0.013 | – ±10.0%  |
−0.0018 ±7.0%
| b4  | secondresonancecoupling |       | 1/s     |
| --- | ----------------------- | ----- | ------- |
| b5  | thirdresonancecoupling  | 0.723 | – ±5.0% |
−0.0015 ±10.0%
| b6  | thirdresonancecoupling  |         | 1/s        |
| --- | ----------------------- | ------- | ---------- |
| b7  | fourthresonancecoupling | 0.235   | – ±5.0%    |
| b8  | fourthresonancecoupling | −0.0263 | 1/s ±10.0% |
±5.0%
| ξ1  | firstresonancedamping  | 0.05  | –       |
| --- | ---------------------- | ----- | ------- |
| ξ2  | secondresonancedamping | 0.024 | – ±8.0% |
±10.0%
| ξ3  | thirdresonancedamping  | 0.129 | –        |
| --- | ---------------------- | ----- | -------- |
| ξ4  | fourthresonancedamping | 0.173 | – ±10.0% |
Fig.14.5 Block-diagramoftheplant
Consider first the derivation of the uncertainty model for the resonant modes.
Allfourmodeshavesimilartransferfunctions.Theuncertaintymodelmaybeob-
tainedinadifferentway.Forinstance,onthebasisoftherepresentation,shownin
Fig.14.5,onemayimplementthefunctiontfinordertoobtainuncertaintransfer
functionforeachoftheresonantmodes.Inthiscase,however,theuncertainparam-
eterω isrepeatedfivetimes,whichleadstoalargenumberofthemodeluncertain
parameters. This complicates very much the analysis and especially the synthesis
ofthesystem.Thatiswhyinthegivencaseweuseastatespacerepresentationin
whichωisrepeatedonlytwice.
Themodelofaresonantmodeinthestatespaceis
x˙ =ωx
1 2

14.2 DerivationofUncertaintyModel 257
Fig.14.6 Block-diagramofaresonantmode
Fig.14.7 Parallelconnection
ofthefourresonantmodes
Fig.14.8 Block-diagramof
theharddiskconsideredasa
controlplant
x˙ =ω(−x −2ξx +t )
2 1 2 a
y =b x +b x
a 1 1 2 2
The block-diagram corresponding to the state equations of a resonant mode is
showninFig.14.6.Theuncertainmodeloftheresonantmodeinthegivencaseis
obtained by using the function iconnect. In this model the uncertain parameter
ωisrepeatedtwice.
Theparallelconnectionofthefourresonantmodes,whichhastransferfunction
H (s),isshowninFig.14.7.
d
Afterobtainingthetransferfunctionoftheresonantmodes,thederivationofthe
uncertainplantmodelisdonebythefunctioniconnect,usingtheblockdiagram,
shown in Fig. 14.5. The model obtained is of 11th order and has 11 independent
uncertainparameters,fourofthem(ω , ω , ω andω )beingrepeatedtwice,such
1 2 3 4
thatthetotalnumberoftheuncertainparametersbecomesequalto15.Theuncertain
modeloftheharddiskservosystemisobtainedbytheM-filemod_hdd.mandis
savedinthevariableG.
Theharddiskmodelhastwoinputsandoneoutput(Fig.14.8).

258 14 RobustControlofaHardDiskDrive
Fig.14.9 Bodeplotoftheharddiskwithuncertainparameters
Letusintroducetherepresentation
G=[G G ]
d u
suchthat
y=G t +G u
d d u
whereG andG aretheplantscalartransferfunctionswithrespecttothedistur-
d u
banceandcontrolaction,respectively.
InFig.14.9weshowtheBodeplotoftheharddisk,obtainedfromthetransfer
functionG forrandomvaluesoftheuncertainparameters.
u
14.3 Closed-Loop System DesignSpecifications
The design of the HDD servo controller will be first conducted in the continuous-
time case. In general, it may obtain best possible performance in the continuous-
time case that can then be considered as a limit for discrete-time designs. Also,
in the continuous-time case it is easier to find appropriate performance weighting
functionsthatagainmaybeimplementedinthediscrete-timedesign.
Theblock-diagramoftheclosed-loopsystem,whichincludesthefeedbackstruc-
ture and the controller as well as the elements representing the model uncertainty
andtheperformanceobjectives,isshowninFig.14.10.

14.3 Closed-LoopSystemDesignSpecifications 259
Fig.14.10 Block-diagramoftheclosed-loopsystemwithperformancespecifications
The system has a reference input (r), an input disturbance (d), a noise (n) and
two output costs (e and e ). The system M is an ideal model of performance,
y u
to which the designed closed-loop system tries to match. The transfer function of
theuncertainplantisdenotedbyG.Theperformanceobjectiverequiresthetransfer
matrixfromr,d,andntoe ande tobesmallinthesenseof(cid:5)·(cid:5) ∞,forallpossible
|     |     |     | y   | u   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
valuesoftheuncertainparameters.Thepositionnoisesignalisobtainedbypassing
the unit-bounded signal n through the weighting transfer matrix W . The transfer
n
matrices W p and W u are used to reflect the relative significance of the different
frequency ranges for which the performance is required. Hence, the performance
(cid:5)·(cid:5)
objectivecanberecast,withpossibleslightconservativeness,asthatthe ∞ of
| thetransferfunctionmatrixfromr,d,andntoe |     |     |     |     |     | ande islessthan1. |     |
| ---------------------------------------- | --- | --- | --- | --- | --- | ----------------- | --- |
|                                          |     |     |     |     |     | y u               |     |
Itisstraightforwardtoshowthat
⎡ ⎤
|     | (cid:2) (cid:3) (cid:2) |     |     |     |     |     | (cid:3) |
| --- | ----------------------- | --- | --- | --- | --- | --- | ------- |
r
|     | e W | (S G | K−M)  | W   | S G      | −W S G KW  |          |
| --- | --- | ---- | ----- | --- | -------- | ---------- | -------- |
|     | y = | p o  | u     |     | p o d    | p o u      | n ⎣ ⎦    |
|     |     |      |       | −W  |          | −W         | d (14.1) |
|     | e u | W u  | S i K |     | u KS o G | d u KS o W | n        |
n
|       | =(I | +KG) | −1, | =(I +GK) | −1  |                                    |     |
| ----- | --- | ---- | --- | -------- | --- | ---------------------------------- | --- |
| where | S   |      | S   |          |     | aretheinputandoutputsensitivities, |     |
|       | i   |      | o   |          |     |                                    |     |
respectively.In(14.1)wemakeuseofthefactthatS K =KS .NotethatS G is
|                             |     |     |     |       |     | i o | o d |
| --------------------------- | --- | --- | --- | ----- | --- | --- | --- |
| thetransferfunctionbetweend |     |     |     | andy. |     |     |     |
ThisobjectiveissimilartotheusualmixedS/KS sensitivityoptimizationandit
wouldmeetbothrobuststabilityandperformancecriteriabyincorporatingperfor-
mancespecificationsinthematchingmodelM.Thesixfunctionstobeminimized
aredescribedinTable14.3.
ThecontrollersynthesisproblemoftheHardDiskDriveServoSystemistofind
alinear,outputfeedbackcontrollerK(s)thathastoensurethefollowingproperties
oftheclosed-loopsystem.

| 260 |     |     |     | 14  | RobustControlofaHardDiskDrive |     |     |     |
| --- | --- | --- | --- | --- | ----------------------------- | --- | --- | --- |
Table14.3 H∞functionsto
|     |     |     | Function | Description |     |     |     |     |
| --- | --- | --- | -------- | ----------- | --- | --- | --- | --- |
beminimized
Wp(SoGuK−M)
Weighteddifferencebetweentheidealand
actualclosed-loopsystems
|     |     |     | WpSoGd    | Weighteddisturbancesensitivity        |     |     |     |     |
| --- | --- | --- | --------- | ------------------------------------- | --- | --- | --- | --- |
|     |     |     | WpSoGuKWn | Weightednoisesensitivity              |     |     |     |     |
|     |     |     | WuSiK     | Weightedcontroleffortduetoreference   |     |     |     |     |
|     |     |     | WuKSoGd   | Weightedcontroleffortduetodisturbance |     |     |     |     |
|     |     |     | WuKSoWn   | Weightedcontroleffortduetonoise       |     |     |     |     |
14.3.1 NominalPerformance
Theclosed-loopsystemachievesnominalperformanceiftheperformanceobjective
issatisfiedforthenominalplantmodel.
Thenominalperformanceobjectiveistosatisfytheinequality
| (cid:24)(cid:2) |      |         |         |        |      |           | (cid:3)(cid:24) |     |
| --------------- | ---- | ------- | ------- | ------ | ---- | --------- | --------------- | --- |
| (cid:24)        |      |         |         |        |      |           | (cid:24)        |     |
| W               | (S G | K−M)    | W S G   |        | −W S | G         | KW              |     |
| (cid:24) p      | o    | un om   | p o     | dnom   | p    | o u nom   | n (cid:24)      | <1  |
| (cid:24)        |      |         | −W      |        | −    |           | (cid:24)        |     |
|                 | W    | u S i K | u K S o | G dnom | W    | u K S o W | n               |     |
∞
(14.2)
wherethetransferfunctionsG ,G areobtainedforthenominalplantpa-
dnom unom
rameters.
| 14.3.2 | Robust | Stability |     |     |     |     |     |     |
| ------ | ------ | --------- | --- | --- | --- | --- | --- | --- |
Theclosed-loopsystemachievesrobuststabilityiftheclosed-loopsystemisinter-
nallystableforeachpossibleplantdynamicsG.
| 14.3.3 | Robust | Performance |     |     |     |     |     |     |
| ------ | ------ | ----------- | --- | --- | --- | --- | --- | --- |
Theclosed-loopsystemmustremaininternallystableforeachGandinadditionthe
performancecriterion
| (cid:24)(cid:2) |          |       |             |     |           | (cid:3)(cid:24) |     |        |
| --------------- | -------- | ----- | ----------- | --- | --------- | --------------- | --- | ------ |
| (cid:24)        |          | −M)   |             | −   |           | (cid:24)        |     |        |
| (cid:24)        | W p (S o | G u K | W p S o G d | W   | p S o G u | K W n (cid:24)  |     |        |
| (cid:24)        |          |       |             |     |           | (cid:24)        | <1  | (14.3) |
|                 | W        | S K   | −W K S G    | −   | W K S     | W               |     |        |
|                 |          | u i   | u o         | d   | u         | o n             | ∞   |        |
G.
has to be satisfied for each This means that t(cid:2)he(cid:3)structured singular value cor-
(cid:4) (cid:5)
|     |     |     |     |     | r   | ey  |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
responding to the transfer function matrix from d to (Fig. 14.10) should
eu
n
belessthan1,withregardtotheparametricuncertaintyandthecomplexfictitious
uncertainty,connectingtheinputsandoutputsintherobustperformanceanalysis.

14.4 SystemInterconnections 261
Fig.14.11 Block-diagramoftheopen-loopsystemwithperformancespecifications
Fig.14.12 Schematic
diagramoftheopen-loop
connection
Inadditiontotheserequirementsitisdesirablethatthecontrollerdesignedwould
haveacceptablecomplexity,i.e.itisofreasonablyloworder.
According to the above considerations, the aim of the design is to determine a
controllerK,suchthatforallstableperturbations,theperturbedclosed-loopsystem
remainsstableandtheperformanceobjectiveissatisfiedforallsuchperturbations.
14.4 System Interconnections
Theinternalstructureofthefour-input,three-outputsystem,whichissavedinthe
variable sys_ic, is shown in Fig. 14.11. The reference, the disturbance and the
noisearesavedinthevariablesref,dist,andnoise,respectively,andthecon-
trolsignal—inthevariablecontrol.
Thevariablesref,dist,noise,y,y_c,e_y,ande_uarescalarvariables.
The open-loop connection is obtained by the M-file olp_hdd. The schematic
diagram, showing the specific input/output ordering for the variable sys_ic, is
giveninFig.14.12.
Theblock-diagramusedinthesimulationoftheclosed-loopsystemisshownin
Fig. 14.13. The corresponding closed-loop interconnection, which is saved in the
variablesim_ic,isobtainedbytheM-filesim_hdd.
The schematic diagram showing the specific input/output ordering for the vari-
ablesim_icisshowninFig.14.14.

262 14 RobustControlofaHardDiskDrive
Fig.14.13 Block-diagramof
theclosed-loopsystem
Fig.14.14 Schematic
diagramoftheclosed-loop
connection
14.5 ControllerDesigninContinuous-Time
Thereareafewfurther“hard”constraintsforthecontrollerdesign,aslistedbelow.
Peakclosed-loopgain <4dB
Open-loopgain >20dBat100Hz
Steady-stateerror <0.1µm
Settlingtime <1.5ms
Closed-loopbandwidth >1000Hz
Gainmargin >5dB
Phasemargin >40deg
Thedesignedcontrolsystemmustachievegooddisturbancerejectionandnoise
attenuation.Inaddition,itisnecessarytohavecontrolactionsmallerthan1.2Vin
ordertoavoidpower-amplifiersaturation.
Todesignthecontrollerweshalluseμ-synthesis,H
∞
optimizationandtheH
∞
loopshapingdesignprocedure(LSDP)inthisexercise.
Inthecaseof μ-synthesisand H ∞ optimizationdesign,wehavetospecifythe
modeltransferfunctionM andtheweightingtransferfunctionsW ,W ,andW .
n p u
Themodeltransferfunctionischosensothatthetimeresponsetothereference
signal would have an overshoot less than 20 % and a settling time less than 1 ms.
Apossiblemodelsatisfyingtherequirementsis
1
M=
3.75×10−9s2+1.2×10−4s+1

14.5 ControllerDesigninContinuous-Time 263
Fig.14.15 Block-diagramof
theclosed-loopsystemwith
μ-controller
ThenoiseshapingfunctionW isdeterminedonthebasisofthespectraldensity
n
ofthepositionnoisesignal.Inthegivencaseitistakenasthehigh-passfilter
0.1s+1
W =6×10 −4
n 0.001s+1
whoseoutputhasasignificantspectralcontentabove500Hz.Forthisshapingfilter,
thepositionnoisesignalisonly0.6mVinthelow-frequencyrangebutitis60mV
inthehigh-frequencyrangethatcorrespondstoapositionerrorof5%ofthetrack
width.
The weighting functions W and W have to be chosen so as to ensure an ac-
p u
ceptabletrade-offbetweenthenominalperformanceandtherobustperformanceof
the closed-loop system. They are selected in the course of the μ-synthesis, since
this particular design method allows us to achieve maximum performance of the
perturbed,closed-loopsystem.
14.5.1 μ-Design
Intheμ-synthesisweshalltakeintoaccountonlytheuncertaintyintherigid-body
model (i.e. only the uncertainty in the parameters k , J, and k ) will be consid-
t y
ered. The inclusion of the uncertainties of resonant modes would make the D–K
iterations difficult to converge which is the reason to ignore these uncertainties.
This confirms that the resonant modes may create difficulties in the controller de-
sign.However,theseresonantmodes(withnominalvalues)areincludedintheplant
dynamics and will be considered, with parametric variations, in the assessment of
designedcontrollersinSect.14.6.
The block-diagram of the closed-loop system used in the μ-synthesis is shown
inFig.14.15.DenotebyP(s)thetransferfunctionmatrixofthefour-input,three-
output, open-loop system. This matrix is obtained from the open-loop connection
sys_icbythecommandline
mu_ic = usubs(sys_ic,’w1’,’nom’,’w2’,’nom’,’w3’,’nom’, ...
’w4’,’nom’,’z1’,’nom’,’z2’,’nom’, ...
’z3’,’nom’,’z4’,’nom’)

| 264 |     |     |     |     | 14  | RobustControlofaHardDiskDrive |     |     |
| --- | --- | --- | --- | --- | --- | ----------------------------- | --- | --- |
and is saved in the variable mu_ic. During the execution of this command the
parametersω ,ω ,ω ,ω ,ξ ,ξ ,ξ ,andξ aresubstitutedbytheirnominalvalues.
|     | 1   | 2 3 | 4 1 2 | 3   | 4   |     |     |     |
| --- | --- | --- | ----- | --- | --- | --- | --- | --- |
ThetransferfunctionmatrixP(s)mayberepresentedastheupperLinearFractional
Transformation
|     |     |     | P   | =F (P | ,Δ  | )   |     |     |
| --- | --- | --- | --- | ----- | --- | --- | --- | --- |
|     |     |     |     | u     | nom | r   |     |     |
where the matrix P is the nominal transfer matrix and Δ r contains the three
nom
uncertainties in the rigid body model. The robust performance of the closed-loop
systemisconsideredwithregardtotheblockuncertainty
|     |     |      | %(cid:2) | (cid:3) |        |       | &   |     |
| --- | --- | ---- | -------- | ------- | ------ | ----- | --- | --- |
|     |     |      | Δ r      | 0       | ∈R3×3, | ∈C3×2 |     |     |
|     |     | Δ := |          | :Δ      |        | Δ     |     |     |
|     |     | P    | 0 Δ      |         | r      | F     |     |     |
F
wherethesecondblockΔ isafictitiousuncertaintyblockthatconnectstheinputs
F
and outputs of the closed-loop system. In order to satisfy the robust performance
requirementsitisnecessarytofindastabilizingcontrollerK(s),suchthatforeach
frequencyω∈[0,∞]thestructuredsingularvaluesatisfiesthecondition
|     |     |     | (cid:4) |          |         | (cid:5) |     |     |
| --- | --- | --- | ------- | -------- | ------- | ------- | --- | --- |
|     |     |     | μ ΔP F  | L (P nom | ,K)(jω) | <1      |     |     |
Thefulfillmentofthisconditionguaranteesrobustperformanceoftheclosed-loop
system,i.e.
| (cid:24)(cid:2) |      |         |     |           |     |             | (cid:3)(cid:24) |        |
| --------------- | ---- | ------- | --- | --------- | --- | ----------- | --------------- | ------ |
| (cid:24)        | W (S | G K −M) | W   | S G       | − W | S G K       | W (cid:24)      |        |
| (cid:24)        | p    | o u     |     | p o d     |     | p o u       | n (cid:24)      |        |
| (cid:24)        |      |         | −W  |           | −   |             | (cid:24) <1     | (14.4) |
|                 | W    | u S i K |     | u K S o G | d   | W u K S o W | n               |        |
∞
The μ-synthesis is conducted by using the M-file ms_hdd. It should be noted
thattherobustperformanceachievedduringtheD–K iterationisonlywithrespect
totheuncertaintiesintherigid-bodymodel,sinceonlytheseuncertaintiesaretaken
intoaccountinthedesign.Henceitisnecessarytomakeanadditionalrobuststabil-
ityandrobustperformanceanalysisthattakesintoaccounttheotheruncertainties.
Theclosed-loopsystemperformancespecificationsarereflectedbytheweight-
ingperformancefunction W (s).Threeperformanceweightingfunctionsarecon-
p
sideredinthedesign.Theyare
s2+8×104s+108
|     |     | W   | (s)=10 −4 |                   |     |     |     |     |
| --- | --- | --- | --------- | ----------------- | --- | --- | --- | --- |
|     |     | p1  |           | s2+7×104s+2.5×104 |     |     |     |     |
s2+4×105s+2.5×109
|     |     | W   | (s)=10 −4 |                      |     |     |     |     |
| --- | --- | --- | --------- | -------------------- | --- | --- | --- | --- |
|     |     | p2  |           | s2+3.9×105s+6.25×105 |     |     |     |     |
and
s2+1.15×106s+3.6×1010
−4
W (s)=10
|     |     | p3  |     | s2+1.05×106s+9×106 |     |     |     |     |
| --- | --- | --- | --- | ------------------ | --- | --- | --- | --- |
In Fig. 14.16 we show the magnitude responses of the inverses of these three
weightingfunctions,i.e.W −1,W −1,andW −1.Itisseenthatinallthreeselections,
|     |     |     | p1 p2 |     | p3  |     |     |     |
| --- | --- | --- | ----- | --- | --- | --- | --- | --- |

14.5 ControllerDesigninContinuous-Time 265
Fig.14.16 MagnituderesponsesoftheinverseofWp
theaimistoachieveasmalldifferencebetweenthesystemandmodeloutputs,anda
smalleffectofthedisturbanceonthesystemoutputs.Thiswillensuregoodtracking
ofthereferenceinputandsmallerrorduetolow-frequencydisturbances.Changing
theperformanceweightingfunctionfromW toW movestheinverseweighting
p1 p3
frequencyresponse to the right (to higher frequencies) which forces the system to
matchthemodelinoveralargerfrequencyrange.
Thecontrolweightingfunctionisusuallychosenashigh-passfiltersinorderto
ensure that the control action will not exceed 1.2 V. Again, three such weighting
functionsareconsideredinthedesignandarelistedbelow:
0.385s2+s+1
W (s)=10 −6
u1 10−4s2+2×10−3s+1
0.55s2+s+1
W (s)=10 −6
u2 10−4s2+2.1×10−3s+1
and
4.05s2+s+1
W (s)=3×10 −6
u3 10−4s2+2×10−3s+1
These three control weighting functions are paired with the three performance
weightingfunctions,inthegivenorder,intheμ-synthesis.

266 14 RobustControlofaHardDiskDrive
Table14.4 Robuststability
Controller Order Robuststability Robustperformance
androbustperformancefor
stabmarg perfmarg
threecontrollers
1 26 2.82 2.33
2 34 2.19 1.94
3 26 1.94 1.19
Table14.5 Gainandphase
Controller GainmargindB Phasemargindeg
marginsforthreecontrollers
1 15.1 50.9
2 11.1 44.1
3 10.9 36.6
Thefinalchoiceoftheappropriateperformanceandcontrolweightingfunctions
is obtained by comparing the results from the corresponding μ-designs. (Three
D–K iterations are used in the first version and four in the second and third ver-
sion.)Therobuststabilityandrobustperformanceanalysisareconductedbythefile
mu_hdd, using the functions robuststab and robustperf. The results are
showninTable14.4.
Itisseenfromthetablethattheclosed-loopsystemachievesrobuststabilityand
robust performance for all three controllers; however, the best results, in terms of
stabilityandperformancemargins,comefromthefirstcontroller.
Thegainandphasemarginsforallthreedesigncasesarefoundfromthetrans-
fer function G K of the nominal open-loop system by the function margin.
unom
TheresultsarelistedinTable14.5andconfirmtherulethathighergainandphase
marginsmeanbetterrobustness.
The closed-loop transient responses are shown in Fig. 14.17, for a simulated
runoutofonetrackwidth(1µm)andatorquedisturbancet =0.0005Nm.
d
ItisseenfromFig.14.17thatthefirstcontrolleryieldsatransientresponsewith
thesmallestundershoot(lessthan30%),butthisresponseistheslowestone.The
third controller yields the fastest response but the undershoot in this case is the
largestone(greaterthan50%).
Figure 14.18 shows that as a result of the appropriate tuning of the control
weightingfunctionsallthreecontrollersproduceacontrolactionwhoseamplitude
isslightlylessthan1.2V.
The comparison of the transient responses to disturbance, shown in Fig. 14.19,
revealsthattheworstdisturbancerejectionisfoundinthefirstcontrollercaseand
thebestinthethirdcontrollercase.Thisisaresultofthetightestclosed-loopband-
width of 9×103 rad/s (measured at −3 dB) in the first controller case compared
withthebandwidthof15.5×103 rad/sinthethirdcontrollercase(seeFig.14.20).
Note that the largest peak of the magnitude is found in the third controller case,
whichresultsinthelargestundershootofthetransientresponse.

14.5 ControllerDesigninContinuous-Time 267
Fig.14.17 Transientresponsesforthreeμ-controllers
Fig.14.18 Controlactionsofthreeμ-controllers

268 14 RobustControlofaHardDiskDrive
Fig.14.19 Transientresponsestodisturbanceofthreeμ-controllers
Fig.14.20 Closed-loopmagnitudeplotsofthreeμ-controllers

14.5 ControllerDesigninContinuous-Time 269
Fig.14.21 Closed-loop
systemwithH∞controller
The results obtained from different weighting functions show that moving the
frequency response of the inverse performance weighting function to the right
wouldleadtolargerclosed-loopsystembandwidth,andconsequently,fastertime-
responsesoftheclosed-loopsystem,thoughmayintroducelargerover(under)shoot.
However,atthesametime,thismayreducetherobustnessoftheclosed-loopsys-
tem.Hence,onehastocompromisebetweenthedifferentobjectivesinthedesign.
Inthepresentdesigncase,itseemsthatthesecondcontrollerleadstoagoodtrade-
offbetweentherequirementsintermsoftransientresponse,disturbancerejection,
and robustness. Hence, we will use the weighting functions W and W in both
p2 u2
theμ-synthesisandH ∞ design.
14.5.2 H ∞ Design
TheaimofthedesigninthiscaseistofindanH ∞ (sub)optimal,outputcontroller
fortheinterconnectionshowninFig.14.21inwhichweignoretheplantuncertainty.
Thevariablehin_icthatcorrespondstothetransferfunctionP ofthenom-
nom
inalopen-loopsystemisobtainedbythecommandline
hin_ic = sys_ic.Nom
TheH ∞optimalcontrolminimizesthe∞-normofF
L
(P
nom
,K)withrespecttothe
transferfunctionK ofthecontroller.InthegivencaseF (P ,K)(asthetransfer
L nom
functionmatrixin(14.2))isthenominalclosed-looptransferfunctionmatrixfrom
thereference,disturbanceandnoisesignals(thevariablesref,distandnoise)
to the weighted outputs e_y and e_u. The design is conducted using the M-file
hinf_hdd.m,whichcomputesa(sub)optimalH ∞ controllawforagivenopen-
loop system. The value of γ is chosen 10 % higher than the minimum possible
value.Thecontrollersuchobtainedisof18thorder.
14.5.3 H ∞ Loop-Shaping Design
ThedesignofarobustcontrolfortheDiskDriveSystemcanbesuccessfullyaccom-
plishedusingtheH ∞ loop-shapingdesignprocedure(LSDP)aswell,asdescribed

270 14 RobustControlofaHardDiskDrive
inthissubsection.NotethatinthecaseofH ∞LSDP,wedonotusetheperformance
weightingfunctionimplementedinthecasesofμandH ∞designs.Instead,weuse
aprefilterW andapostfilterW inordertoshapeappropriatelythefrequencyre-
1 2
sponseoftheaugmented,open-looptransferfunctionW GW (seeChap.5).
2 1
Inthepresentcasewechooseaprefilterwithtransferfunction
0.05s+1
W =4
1
s
Thegainof4ischosentoensureasteady-stateerror,duetothedisturbance,ofless
than 10 % of the track width. Larger gain leads to smaller steady-state errors but
possiblyworsetransientresponse.ThepostfilteristakensimplyasW =1.
2
ThemagnitudeplotsoftheoriginalandshapedsystemsareshowninFig.14.22.
ThedesignoftheH ∞ LSDPcontrollerusestheM-filelsh_hddthatimplements
thefunctionncfsyn.Thecontrollerobtainedisoforder12.
14.6 Comparison ofDesignedControllers
Thecomparisonoftheclosed-loopsystemwithμ,H ∞,andH ∞ LSDPcontrollers
beginswiththerobuststabilityandperformanceanalysis.
Therobuststabilityistestedontheclosed-looptransferfunctionmatrix,thecom-
putationofthestructuredsingularvalueμ (.)beingdonebythecommandmussv.
Δ
TheuncertaintymatrixΔ,whichisnecessaryinthecomputationofμ (.),ispulled
Δ
outfromtheclosed-looptransfermatrixbythecommandlftdataandhasdimen-
sion15×15(theuncertaintiesintheresonantmodesparticipatetwice).Toachieve
robust stability it is necessary that the μ-values are less than 1 over the frequency
range.Therobuststabilitytestisdonebythefilerbs_hdd.
InFig.14.23wecomparetheupperboundsofthestructuredsingularvalues,for
the robust stability analysis, of the closed-loop systems with the three controllers
(μ,H ∞,andH ∞ LSDP).
It is seen from the figure that all three closed-loop systems achieve the robust
stability.Thebestrobustnessisobtainedbytheμ-controller.
The comparison of the nominal performance for the three controllers, in
Fig. 14.24, shows that the performance in the H ∞ LSDP controller case over the
low-frequencyrangeismuchworsethanthatintheothertwocases.Thisisacon-
sequence of the fact that the performance specifications used in the μ-design and
H ∞ design are not explicitly adopted in the design of the H ∞ LSDP controller.
The larger magnitude over the low frequencies leads to an expectation of larger
steady-stateerrors.
The robust performance of the closed-loop system is studied also with the aid
oftheμ-analysisusingthefunctionmussv.InthiscasetheuncertaintyblockΔ ,
P
which is used in the computation of the structured singular value, has dimension
18×17 and consists of the matrix Δ plus 3×2 complex block that corresponds
to a fictitious uncertainty and connects the inputs and outputs of the closed-loop

14.6 ComparisonofDesignedControllers 271
Fig.14.22 Magnitudesplotsoftheoriginalandshapedsystems
Fig.14.23 Robuststabilityoftheclosed-loopsystems

272 14 RobustControlofaHardDiskDrive
Fig.14.24 Nominalperformanceoftheclosed-loopsystems
Fig.14.25 Robustperformanceoftheclosed-loopsystems

14.6 ComparisonofDesignedControllers 273
system (see Fig. 14.15). The robust performance (with respect to the uncertainty
andperformanceweightingfunctions)isachievedifandonlyifforeachfrequency
μ (.),computedfortheclosed-loopfrequencyresponse,islessthan1.Therobust
ΔP
performancetestisdonebythefilerbp_hdd.
TherobustperformancetestforallcontrollersisshowninFig.14.25.Again,the
H ∞ LSDPcontrollershowslargeμ-valuesoverthelow-frequencyrange.
The robust stability and robust performance analysis also shows that the worse
resultsmaypossiblyoccuroverfrequenciesaroundtheresonantfrequencies.
The Bode plots of the closed-loop systems with three controllers are shown in
Fig.14.26.Itisseenthatthesystemwiththe H ∞ LSDPcontrollerhasthelargest
bandwidth,whichmayleadtothefasttransientresponse.Alargerbandwidth,how-
ever,mayalsoleadtoalargereffectofnoisesandresonances.
The plot of the output sensitivity to disturbances (Fig. 14.27) shows that in the
low-frequency range the influence of the disturbance on the system output in the
case of the H ∞ LSDP controller is the largest. Better disturbance attenuation for
this controller may be achieved by choosing higher gain in the prefilter. This will
lead,however,togreaterovershootinthetransientresponse.Thesensitivitytodis-
turbance in the cases of μ and H ∞ controllers reaches a maximum value in the
frequency range from 103 rad/s to 104 rad/s, which is inside of the closed-loop
bandwidth. This means that the closed-loop system will be susceptible to distur-
bancesoverthatfrequencyrange.Itisinterestingtonoticethatthesensitivityofthe
H ∞ LSDPcontrolleroverthesamerangeis8dBlower.
TheoutputsensitivitytonoiseisshowninFig.14.28.(Notethatthesensitivity
iswithrespecttotheunit-boundednoise,theinputofthenoiseshapingfilter.)The
lowest sensitivity to noise has been achieved by the system with the μ-controller
andthelargestsensitivitybythesystemwiththeH ∞ LSDPcontroller.
The Bode plots of the three controllers are compared in Fig. 14.29. It is seen
that the H ∞ LSDP controller has a very low gain in the range from 40 rad/s to
2000 rad/s, which is the reason for the weak attenuation of the disturbances over
thatrange.
The transient responses of the closed-loop systems for the nominal parameter
valuesareobtainedbyusingthefileclp_hdd.InFig.14.30weshowthetransient
responsesoftheclosed-loopsystemstoareferencesignal,equivalenttoonetrack.
While for the H ∞ and H ∞ LSDP controllers the undershoot is about 60 %, it is
about 38 % for the μ-controller. The settling time for the H ∞ LSDP, μ and H ∞
controllersis0.8ms,1msand1.5ms,respectively.
ThecontrolactionsofthethreecontrollersareshowninFig.14.31.Forallcon-
trollersthecontrolsignalamplitudedoesnotexceed1.2V,asrequired.
In Fig. 14.32 we show the system response to a step torque disturbance t =
d
0.0005Nm(equivalenttoaforceof9.8×10 −3 Nappliedtothediskheadassem-
bly). The transient error for the H ∞ LSDP controller has the smallest undershoot
(10.5%)buthasanonzerosteady-stateerror.Thisrevealsthatinthegivencasethe
LSDP controller does not have integrating action with respect to the disturbance.
The transient error for μ and H ∞ controllers is less than 18 % of the track width
andthesteady-stateerrorispracticallyequaltozero.

274 14 RobustControlofaHardDiskDrive
Fig.14.26 Bodeplotsoftheclosed-loopsystems
Fig.14.27 Outputsensitivitytodisturbance

14.6 ComparisonofDesignedControllers 275
Fig.14.28 Outputsensitivitytonoise
Fig.14.29 Bodeplotsofthreecontrollers

276 14 RobustControlofaHardDiskDrive
Fig.14.30 Transientresponseswiththreecontrollers
Fig.14.31 Controlactionsofthreecontrollers

14.7 Controller-OrderReduction 277
Fig.14.32 Transientdisturbanceresponsesofthreecontrollers
Theoutputresponsetotheposition-sensingnoiseissimulatedforanoisesignal
withanamplitudethatdoesnotexceed60mV(5%ofthetrackwidth).Thissignalis
obtainedattheoutputofthenoiseshapingfilterwhoseinputischosenasasequence
ofuniformlydistributedrandomnumbersintheinterval[−1,1].Inthecaseofthe
μ-controllertheoutputduetonoiseislessthan0.6%ofthetrackwidth.Thelargest
outputtothenoise(1%ofthetrackwidth)isseenintheH ∞LSDPcontrollercase
duetothelargestclosed-loopbandwidthofthiscontroller.
Thecomparisonoftherobuststabilityandrobustperformanceforthethreecon-
trollers, as well as the comparison of the corresponding frequency and transient
responsesshowsthatitisreasonabletoconcludethattheμcontrollerispreferable.
Considernowthepropertiesoftheclosed-loopsystemwithμ-controllerforvari-
ationsoftheplantparameters.
InFig.14.33weshowthemagnitudeclosed-loopplotsforrandomplantparam-
eters.Themagnitudeplotgivenwithcontinuouslinecorrespondstotheworsegain
whentheparameterchange(thisgainisdeterminedbythefunctionwcgain).
InFig.14.34weshowtheoutputsensitivityandinFig.14.35thesensitivityto
noisefor20randomcombinationsoftheuncertainplantparameters.
14.7 Controller-OrderReduction
The controller obtained by the μ-synthesis is initially of 34th order. It is useful to
reduceasmuchaspossiblethecontrollerorder,whichwillsimplifytheimplemen-
tation and increase the reliability. To do this we use the function reduce. The

278 14 RobustControlofaHardDiskDrive
Fig.14.33 Magnitudeclosed-loopplotsforrandomplantparameters
Fig.14.34 Outputdisturbancesensitivityforrandomplantparameters

14.8 DesignofDiscrete-TimeController 279
Fig.14.35 Outputsensitivitytonoiseforrandomplantparameters
experience with different controllers shows that the order may be reduced to 12.
Further reduction of the controller order leads to deterioration of the closed-loop
performance.
InFig.14.36wecomparetheBodeplotsofthefullorderandreduced-ordercon-
trollers.Thecorrespondingplotspracticallycoincidewitheachother,whichimplies
similarperformancesoftheclosed-loopsystems.
InFig.14.37weshowthetransientresponsesoftheclosed-loopsystemwiththe
reducedorderμ-controllerfor30randomcombinationsoftheuncertainparameters
and in Figs. 14.38 and 14.39 we show the control action and the transient distur-
banceresponses,respectively,forthesamevaluesoftheuncertainparameters.The
transientresponsesareobtainedbytheM-filemcs_hdd.
14.8 DesignofDiscrete-TimeController
Ingeneral,therearetwoapproachestodesigningadiscrete-timeservocontroller.
Thefirstapproachistosamplethealreadydesignedcontinuous-timecontroller
atagivensamplingfrequencyf =1/T .ThismaybeaccomplishedbytheM-file
s s
dcl_hdd.m that utilizes the function c2d. The resultant sampled-data, closed-
loopsystemissimulatedbyusingthefunctionsdlsim.Thisapproachgivessatis-
factoryresultsforasufficientlyhighsamplingfrequency(say,100kHzinthegiven
case).

280 14 RobustControlofaHardDiskDrive
Fig.14.36 Bodeplotsoffull-andreduced-orderμ-controllers
Fig.14.37 Transientresponseswithμ-controllerforrandomplantparameters

14.8 DesignofDiscrete-TimeController 281
Fig.14.38 Controlactionoftheμ-controllerforrandomplantparameters
Fig.14.39 Transientdisturbanceresponseswithμ-controllerforrandomplantparameters

282 14 RobustControlofaHardDiskDrive
Thesecondmethodistosamplethecontinuous-time,open-loopsystem(includ-
ingtheweightingfilters)andtodesigndirectlyadiscrete-timecontrollerbyusing
H ∞ optimization (implementing the function hinfsyn) or μ-synthesis (imple-
mentingthefunctiondksyn).
Thechoiceofthesamplingfrequencyinthediscrete-timecasehasastronginflu-
enceontheclosed-loopsystemperformance.Alowsamplingfrequencylimitsthe
systembandwidthandwoulddeterioratethetransientperformancesuchasthedis-
turbancerejection.Ontheotherhand,theincreaseofthesamplingfrequencywould
complicatethecontrollerimplementationandraisethecostoftheHDD.
Later we consider the μ-synthesis of the discrete-time controller for two sam-
plingrates:24kHzand36kHz.Inbothcasesweusethesameperformanceweight-
ingfunction
s2+4×105s+2.5×109
W (s)=10 −4
p2 s2+3.9×105s+6.25×105
utilizedalreadyinthecontinuous-timedesign.Dependingonthesamplerateweuse
twodifferentcontrolweightingfunctions
4s2+2s+1
W (s)=10 −7
u1 2×10−3s2+2×10−3s+1
(forf =24kHz)and
s
1.04s2+2s+1
W (s)=10 −7
u2 7.5−5s2+2×10−3s+1
(for f =36kHz).Thisallows,inbothcases,toobtaincontrolsignalsthatdonot
s
exceed1.2V.
Thenoiseshapingfilteristhesameasinthecontinuous-timecase.
The sampling of the extended open-loop system for the given sampling rate is
conductedbytheM-filedlp_hdd.m.
InFig.14.40weshowtheBodeplotsofthecontinuoustimeplantandthesam-
pledwithf =36kHzplant.
s
The discrete-time μ-synthesis is accomplished by the file dms_hdd.m. As in
thecontinuous-timeμ-synthesis,onlytherigid-bodyuncertainparametersaretaken
intoaccount.
The results from the μ-synthesis for f = 24 kHz show that for the chosen
s
weightingfunctionstheclosed-loopsystemalmostachievesrobustperformanceat
the sixth D–K iteration (μ =1.125) but the closed-loop response is relatively
max
slow and the undershoot is large (60 %). To obtain better results it is necessary to
increasethesamplingfrequency.
Wenowpresentinmoredetailtheresultsfromtheμ-synthesisatf =36kHz.
s
In this case an appropriate controller is obtained after six D–K iterations and the
maximum robust performance μ achieved is almost equal to 1. In Figs. 14.41
max
and 14.42, we show the μ-plots, obtained by the M-file dmu_hdd.m, for robust

14.8 DesignofDiscrete-TimeController 283
Fig.14.40 Bodeplotsofthecontinuoustimeplantandthesampledwithfs =36kHzplant
Fig.14.41 Robuststabilityoffs =36kHzdesign

284 14 RobustControlofaHardDiskDrive
Fig.14.42 Robustperformanceoffs =36kHzdesign
stability analysis and robust performance analysis, respectively. In both plots the
worstresultsareseenaroundthesecondresonantfrequencyof2.2kHz.
The transient responses of the closed-loop system for 30 random combinations
of the uncertain parameters are obtained by the file dsl_hdd.m, which imple-
mentsthefunctionsdlsim.Thefunctionsdlsimalsocomputesthecontrolac-
tionsignalobtainedattheoutputofthedigital-to-analogconverter.Theclosed-loop
transient response is shown in Fig. 14.43 and the corresponding control action in
Fig.14.44.Theundershootforallparametervaluesislessthan50%andthemaxi-
mummagnitudeofthecontrolsignalis1V.
ThetransientresponsetodisturbanceisshowninFig.14.45.Overall,theresults
obtained are almost as good as the results obtained with the continuous-time, μ-
controller.
14.9 NonlinearSystem Simulation
In order to obtain a realistic idea about the behavior of the designed system, the
nonlinear,closed-loopservosystemissimulatedbyusingSimulink®.Forthisaim,
twomodelsaredeveloped,namelyc_hdd.mdlforthecontinuous-timesystemand
d_hdd.mdl for the sampled-data system. In the simulation we take into account
theamplifiersaturation,whichwasneglectedinthedesignsofar.Bothmodelsallow
ustosimulatetheclosed-loopsystemfordifferentreference,disturbanceandnoise
signalsandfordifferentvaluesoftheuncertainparameters.

14.9 NonlinearSystemSimulation 285
Fig.14.43 Transientresponseoffs =36kHzdesign
Fig.14.44 Controlactionoffs =36kHzdesign

286 14 RobustControlofaHardDiskDrive
Fig.14.45 Transientresponsetodisturbanceoffs =36kHzdesign
Beforesimulatingthecontinuous-timesystemitisnecessarytoassignthemodel
parametersbyusingtheM-fileinit_c_hdd.m.
The sampled-data model involves the discrete-time controller, 16-bit analogue-
to-digital converter with maximum input voltage 2.5 V and 16-bit digital-to-
analogue converter with maximum output voltage 10 V. It is assumed that the
discrete-timecontrollerisimplementedonaDSPwithwordlengthof64bits.These
parametersaresetpriortothesimulationbyusingtheM-fileinit_d_hdd.m.It
isassumedthatthecontrolactioncalculationrequiresonesamplingperiodT .
s
In Fig. 14.46 we show the Simulink® model d_hdd.mdl of the nonlinear,
sampled-data,closed-loopsystem.
Asinthelinearcase,thetransientresponsesofthenonlinearclosed-loopsystem
areobtainedforasimulatedrunoutofonetrackwidth(1µm)andtorquedisturbance
t =0.0005Nm.
d
In Fig. 14.47 and in Fig. 14.48 we compare the results from the simulation of
thecontinuous-timeanddiscrete-timenonlinearsystems.Thecontinuous-timecon-
trolleristhereduced-orderμ-controllerinSect.14.7andthediscrete-timecontroller
isthecontrollerdesignedatthesamplingfrequencyof36kHz.
The transient responses of the nonlinear system are close to the corresponding
responses of the linear system due to the small input signals (amplitude less than
1.2V).
Itshouldbementionedthatthecontrollersdesignedareappropriateforsmallref-
erencesignals(equivalenttoonetrack).Forlargerreferencestheamplifiersaturates
anditisnecessarytoimplementanappropriateseekingalgorithm.

14.9 NonlinearSystemSimulation 287
metsysatad-delpmasraenilnonehtfoledomnoitalumiS
64.41.giF

288 14 RobustControlofaHardDiskDrive
Fig.14.47 Transientresponsesofthenonlinearsystems
Fig.14.48 Disturbanceresponsesofthenonlinearsystems

14.10 Conclusions 289
14.10 Conclusions
TheexperiencegainedinthedesignoftheHDDservocontrollersmakesitpossible
toderivethefollowingconclusions:
• Theimplementationofdesignedμ,H ∞,andH ∞ LSDPcontrollersintheHDD
servo system gives satisfactory results with respect to robustness and perfor-
mance. All three controllers ensure robust stability of the closed-loop system.
ThebestrobustperformanceisachievedbyusingtheμandH ∞controllers.The
implementation of the H ∞ LSDP controller gives the fastest transient response
andthecorrespondingdesignislesscomplicated.Thiscontroller,however,leads
to the worst performance in the low-frequency range, which results in a large
steady-stateerror.Inthegivencasethebesttrade-offbetweentherobustnessand
transient response requirements is achieved by using the μ-controller that is, to
someextent,duetothespeciallychosenweightingfunctions.
• The number of original uncertain parameters is very large (more than 25 in the
given case). This complicates the design and produces heavy computation de-
mands.This is whyitis necessarytoinvestigatetheparameterimportancewith
respecttotherobustnessandperformanceinordertoreducetheirnumbertoan
acceptablevalue.However,intheevaluationofthedesign,itisbettertotakeinto
accountallthepossibleuncertaintiestoensureasatisfactorydesigninarealcase.
• Intheμ-synthesis,theorderoftheresultantcontrollerdependsontheorderofthe
plant,oftheweightingfunctions,andofthescalingdiagonalelementsapproxi-
mations.Thedesignedcontrollersareusuallyofhighorders,whichcomplicates
the implementation of the controller. Hence, an order reduction should usually
beconsideredrightafterthecontrollerdesign.MostcontrollersusedintheHDD
designsareoforderbetween8and15.
• Good disturbance attenuation requires sufficiently large closed-loop bandwidth.
This may, however, lead to difficulties in achieving robust stability and robust
performanceinthepresenceofresonantmodes.Someresonanceswhosefrequen-
ciesaremuchhigherthantheclosed-loopbandwidthandthusseeminnocentmay
evenactuallydestroytherobuststabilityofthesystem.Insuchcases,itisneces-
sarytoincreasethedampingofthesemodesbyusingtechniquesofpassive/active
damping.
• Thepresenceofresonantmodesmayrequiresufficientlyhighsamplingratesin
thecaseofusingadiscrete-timecontroller.
• It is importantto stress thatbetter results, withrespect to the transientresponse
(overshootandsettlingtime),aredifficulttoobtainfor thecurrentplantparam-
eters.Ifhigherperformancedemandsarerequired,itisnecessarytochangethe
HDDparameters,forinstancetoincreasetheVCMtorqueconstant.
14.11 Notesand References
ThehistoryoftheHardDiskDrivecontrolispresentedinthefascinatingpapersof
AbramovitchandFranklin[2,3].Anexcellentsurveyonsimilaritiesandcontrasts

290 14 RobustControlofaHardDiskDrive
in the magnetic and optical disk controls is given in [1]. In [87] one may find an
attractivedescriptionoftheHDDconstructionandfunctioning.
ThebookofChenetal.[20]isentirelydevotedtoHDDservosystemsandcon-
tains rich information related to the design of such systems. A tutorial on HDD
controlcanbefoundin[117].
AdetailedmodeloftheHDDservosystem,whichhasverymuchinfluencedthe
modelusedinthischapter,ispresentedinthebookofFranklinetal.[46,Chap.14].
Below100Hztherotaryactuatordynamicsisaffectedbypivotbearingnonlinearity,
whichisknownunderthename“stick–slip”.Ithasastrongeffectparticularlyinthe
caseofsmalldiskdriveswithloweractuatorinertia.Analysisandsimulationofthis
phenomenonarepresentedin[4,174].
An important step in the design of HDD servo systems is the reliable estima-
tionofthevariousdisturbancesandnoisesactingonthesystem.Methodsforsuch
estimationsaredescribedin[5,35,69].
TheharmoniccompensationusedtoreduceRROisconsideredin[21,83,163].
The track-seeking and track-following modes require different control algo-
rithms.Track-seekingalgorithmsaredescribedin[46,135].Theswitchingofcon-
trolmodefromtrackseekingtotrackfollowingshouldbesmoothsothattheresidual
vibrationoftheread/writeheadsuspensionisminimal.Thereareseveralcontrolal-
gorithmsthatworkforbothtrack-seekingandfollowing,seeforinstance[71,79].
Suchalgorithmsutilize2-degree-of-freedom(2DOF)controllersinwhichcasethe
trackseekingisaccomplishedbyusingafeedforwardcontrolleralongwitharefer-
encetrajectory.
ApartfromthetrackseekingandtrackfollowingtheHDDalsocontainsaspindle
velocitycontrolloop.Thepurposeofthisloopistocontroltheairflowoverthedisk
inordertoguaranteetheappropriateflyingheightoftheread/writehead.Thisisa
low-frequencycontrolloopanditsdesigndoesnotrepresentaseriousdifficulty.
Furtherexpansionoftheclosed-loopbandwithoftheHDDcontrolsystemmay
beachievedbyusingtheso-calleddual-stageservosthatconsistofalow-bandwidth
coarseactuator(theusualVCM)andahighbandwidthfineactuator.Thefineactua-
torhasasmallstrokeandmaybeimplementedasapiezoelectrictransducer(PZT)
[40].Thedesignofdual-stageservosisconsideredin[29,74,86].
Other important aspects of the analysis and design of HDD servo systems are
presentedin[59,77,94,95,110,183],tonameafew.

Chapter 15
A Triple Inverted Pendulum Control System
Design
Robustdesignofatripleinvertedpendulumcontrolsystemisdiscussedinthischap-
ter.
The triple inverted pendulum is an interesting control system that resembles
many features found in, for instance, walking robots and flexible space structures,
andotherindustrialapplications.Thiskindofpendulumsystemisdifficulttocon-
trol due to the inherent instability and nonlinear behavior. Some of the pendulum
parametersmaynotbeknownexactlyinpractice,whichinfluencessignificantlythe
systemdynamics.
Inthedesignofarobustcontrolsystemfortripleinvertedpendulumsitiscon-
ventionally assumed that the system is affected by unstructured uncertainties and
thustherobustpropertiesoftheclosed-loopsystemcouldbeachievedbyusingan
H ∞ controller. In real cases, however, the uncertainties of such a pendulum sys-
tem would be more reasonably considered to have some structures. For instance,
becausethemomentsofinertiaandthefrictioncoefficientsaredifficulttoestimate
precisely,itmakessensetoassumeunknowndeviationsinthoseparameters.Also,
wewouldliketodesigntheclosed-loopcontrolsystemtobemore“robust”against
thoseparametersthathavea“larger”ormoreseriousinfluenceuponthesystembe-
havior.Forinstance,theviscousfrictioninthejointsmaydestroythecontrollability
ofthelinearizedmodel.Hence,itwouldbeimportanttotreatuncertaintiesinsuch
parameters individually rather than aggregate them in an overall, unstructured un-
certainty of the system dynamics. Consequently, it may be more suitable to apply
theμ-synthesistechniquethatmayleadtoaless-conservativedesigntomeettighter
designspecifications.
In the pendulum control-system design we first model the uncertainties as
a mixed type that consists of complex uncertainties in the actuators, real un-
certainties in the moments of inertia and in the viscous friction coefficients.
A2-degree-of-freedom (2DOF) design framework is adopted. Both H ∞ subopti-
maland μ-controllersaredesigned.The H ∞ controllershowsbettertransientand
disturbanceresponsesbutdoesnotensurerobuststabilitynorrobustperformance.
Theμ-controllerachievesbothrobuststabilityandrobustperformance,however,at
the price of poorer time responses. The μ-controller designed is initially of quite
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 291
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_15,©Springer-VerlagLondon2013

292 15 ATripleInvertedPendulumControlSystemDesign
Fig.15.1 Tripleinvertedpendulum
highorder,whichmakesitunsuitableforimplementationinpractice.Amodelre-
duction is then conducted that leads to a reduced-order controller maintaining the
requiredrobuststabilityandrobustperformanceoftheclosed-loopsystem.
15.1 System Description
Thetripleinvertedpendulumconsideredis theexperimentalsetuprealizedbyFu-
ruta et al. [48] (Fig. 15.1). The pendulum consists of three arms that are hinged
by ball bearings and can rotate in the vertical plane. The torques of the two upper
hinges are controlled by motors, with the lowest hinge made free for rotation. By
controllingtheanglesofthetwoupperarmsaroundspecifiedvalues,thependulum
canbestabilizedinverselywiththedesiredangleattitudes.Ahorizontalbarisfixed
to each of the arms to ease the control by increasing the moment of inertia. Two
dcmotors,M andM ,aremountedonthefirstandthirdarm,respectively,acting
1 2
asactuatorsthatprovidetorquestothetwoupperhingesthroughtimingbelts.The
potentiometersP ,P ,andP arefixedtothehingestomeasurethecorresponding
1 2 3
angles.

| 15.1 | SystemDescription |     |     |     |     |     | 293 |
| ---- | ----------------- | --- | --- | --- | --- | --- | --- |
Fig.15.2 Geometric
relationshipofpotentiometers
Let Θ i denote the angle of the ith arm. The first potentiometer measures the
angleΘ ,andthesecondandthirdpotentiometersmeasuretheanglesΘ −Θ and
|     | 1   |     |     |     |     |     | 2 1 |
| --- | --- | --- | --- | --- | --- | --- | --- |
Θ −Θ ,respectively(Fig.15.2).
3 2
The mathematical description of the triple inverted pendulum is derived under
thefollowingassumptions:
(a) eacharmisarigidbody;
(b) thelengthsofthebeltsremainconstantduringtheoperationofthesystem;
(c) thefrictionforceinthebottomhingeisproportionaltothevelocityofthebottom
armandthefrictionforcesintheupperhingesareproportionaltothedifferences
oftherespectivevelocitiesoftwoneighboringarms.
We shall first consider the mathematical model of the pendulum itself, without
the actuators. The pendulum model is constructed using the Lagrange differential
equations[48],whichyieldthefollowingnonlinearvector–matrixdifferentialequa-
tion:
|      | ⎡ ⎤     | ⎡ ⎤     | ⎡ ⎤ |         |         | ⎡ ⎤          | ⎡ ⎤ |
| ---- | ------- | ------- | --- | ------- | ------- | ------------ | --- |
|      | ¨       | ˙       |     | (cid:2) | (cid:3) |              |     |
|      | Θ 1     | Θ 1     | q 1 |         |         | τ 1          | Θ 1 |
|      | ⎣ ¨ ⎦+N | ⎣ ˙ ⎦+⎣ | ⎦+G | t       | m1      | ⎣ ⎦ whereΘ=⎣ | ⎦   |
| M(Θ) | Θ       | Θ       | q   |         | =T      | τ            | Θ   |
|      | 2       | 2       | 2   | t       |         | 2            | 2   |
|      | Θ ¨     | Θ ˙     | q   |         | m2      | τ            | Θ   |
|      | 3       | 3       | 3   |         |         | 3            | 3   |
(15.1)
andwehave

294 15 ATripleInvertedPendulumControlSystemDesign
Table15.1 Systemnomenclature
Symbol Description
uj inputvoltagetothejthmotor
tmj controltorqueofthejthmotor
τi disturbancetorquetotheitharm
li lengthoftheitharm
hi thedistancefromthebottomtothecenterofgravityoftheitharm
mi massoftheitharm
Ii momentofinertiaoftheitharmaroundthecenterofgravity
Ci coefficientofviscousfrictionoftheithhinge
Θi angleoftheitharmfromverticalline
Cmi viscousfrictioncoefficientoftheithmotor
Imi momentofinertiaoftheithmotor
Ki ratioofteethofbelt–pulleysystemoftheithhinge
C p(cid:23) viscousfrictioncoefficientofthebelt–pulleysystemoftheithhinge
i
I p(cid:23) momentofinertiaofthebelt–pulleysystemoftheithhinge
i
αi gainoftheithpotentiometer
g accelerationofgravity
M(Θ)
⎡ ⎤
=⎣ l 1 M 2cos J (Θ 1 + 1 − Ip Θ 1 2 )−Ip1 l 1 M 2 J co 2 s + (Θ I 1 p1 − + Θ I 2 p ) 2 −Ip1 l 2 M l 1 3 M co 3 s c (Θ os 2 (Θ − 1 Θ − 3 ) Θ − 3 ) Ip2 ⎦
l
1
M 3cos(Θ
1
−Θ
3
) l
2
M 3cos(Θ
2
−Θ
3
)−Ip2 J
3
+Ip2
⎡ ⎤
C +C +C −C −C 0
N =⎣
1
−C −
2
C
p1
C +C
2
+C
p1
+C −C −C ⎦
2 p1 p1 p2 2 3 3 p2
0 −C −C C +C
3 p2 3 p2
q =l M sin(Θ −Θ )Θ ˙2+l M sin(Θ −Θ )Θ ˙2−M gsin(Θ )
1 1 2 1 2 2 1 3 1 3 3 1 1
q =l M sin(Θ −Θ )Θ ˙2+l M sin(Θ −Θ )Θ ˙2−M gsin(Θ )
2 1 2 1 2 (cid:6) 1 2 3 (cid:7) 2 3 3 2 (cid:6) 2 (cid:7)
q =l M sin(Θ −Θ ) Θ ˙2−2Θ ˙ Θ ˙ +l M sin(Θ −Θ ) Θ ˙2−2Θ ˙ Θ ˙
3 1 3 1 3 1 1 3 2 3 2 3 2 2 3
−M gsin(Θ )
⎡ 3 3⎤ ⎡ ⎤
K 0 1 −1 0
1
G=⎣−K K ⎦ , T =⎣ 0 1 −1 ⎦
1 2
0 −K 0 0 1
2
C pi =C p
i
(cid:23) +K i 2C mi , I pi =I p
i
(cid:23) +K i 2I mi
M =m h +m l +m l , M =m h +m l , M =m h
1 1 1 2 1 3 1 2 2 2 3 2 3 3 3
J =I +m h2+m l2+m l2, J =I +m h2+m l2
1 1 1 1 2 1 3 1 2 2 2 2 3 2
J =I +m h2
3 3 3 3
andallotherparametersandvariablesaredefinedinTable15.1.

15.2 ModelingofUncertainties 295
Afterlinearizationof(15.1)undertheassumptionsofsmalldeviationsofthepen-
dulumfromtheverticalpositionandofsmallvelocities,oneobtainsthefollowing
equation:
⎡ ⎤ ⎡ ⎤ ⎡ ⎤ ⎡ ⎤
¨ ˙ (cid:2) (cid:3)
Θ Θ Θ τ
M ⎣ Θ ¨ 1 ⎦+N ⎣ Θ ˙ 1 ⎦+P ⎣ Θ 1 ⎦+G t m1 =T ⎣ τ 1 ⎦ (15.2)
Θ ¨ 2 Θ ˙ 2 Θ 2 t m2 τ 2
3 3 3 3
where
⎡ ⎤
J +I l M −I l M
M=⎣ l M 1 − p I 1 J 1 +I 2 + p I 1 l M 1 − 3 I ⎦
1 2 p1 2 p1 p2 2 3 p2
l M l M −I J +I
⎡ 1 3 2 3 ⎤p2 3 p2
M g 0 0
1
P =⎣ 0 −M g 0 ⎦
2
0 0 −M g
3
Byintroducingthecontroltorquesvectort =[t t ]T andthevectorofdis-
m m1 m2
turbancetorquesd=[τ ,τ ,τ ]T,(15.2)canberewrittenintheform
1 2 3
MΘ ¨ +NΘ ˙ +PΘ+Gt =Td
m
i.e.,
Θ ¨ =M −1(−NΘ ˙ −PΘ−Gt +Td)
m
Asfortheoutputvector,wedefine
y=[Θ Θ Θ ]T
1 2 3
Theoutputsaremeasuredbylinearpotentiometers,whosevoltagesaregivenby
y =α Θ , y =α (Θ −Θ ), y =α (Θ −Θ )
p1 1 1 p2 2 2 1 p3 3 3 2
Byintroducingthevectorofthemeasuredoutputs
y =[y y y ]T
p p1 p2 p3
weobtain
⎡ ⎤
α 0 0
1
y =C Θ, C =⎣−α α 0 ⎦
p p p 2 2
0 −α α
3 3
Theblock-diagramofthependulumsystemisshowninFig.15.3andthenominal
valuesoftheparametersaregiveninTable15.2.
15.2 ModelingofUncertainties
Based on practical considerations, we in particular consider the variations of the
momentsofinertiaI ,I ,andI ofthethreearmsandthevariationsoftheviscous
1 2 3

| 296 15 | ATripleInvertedPendulumControlSystemDesign |     |     |
| ------ | ------------------------------------------ | --- | --- |
Fig.15.3 Block-diagramofthetripleinvertedpendulumsystem
Table15.2 Nominalvalues
| Symbol(unit) | Value | Symbol(unit) | Value |
| ------------ | ----- | ------------ | ----- |
oftheparameters
| l1(m) | 0.5  | α1(V/rad) | 1.146  |
| ----- | ---- | --------- | ------ |
| l2(m) | 0.4  | α2(V/rad) | 1.146  |
| h1(m) | 0.35 | α3(V/rad) | 0.9964 |
2.19×10−3
| h2(m)  | 0.181 | Cm1 (Nms)         |           |
| ------ | ----- | ----------------- | --------- |
| h3(m)  | 0.245 | Cm2 (Nms)         | 7.17×10−4 |
|        |       | (kgm2)            | 2.40×10−5 |
| m1(kg) | 3.25  | Im1               |           |
| m2(kg) | 1.90  | Im2 (kgm2)        | 4.90×10−6 |
| m3(kg) | 2.23  | C p(cid:23) (Nms) | 0         |
1
I1(kgm2)
|     | 0.654 | C p(cid:23) (Nms) | 0   |
| --- | ----- | ----------------- | --- |
2
| I2(kgm2) | 0.117 | I p(cid:23) (kgm2) | 7.95×10−3 |
| -------- | ----- | ------------------ | --------- |
| I3(kgm2) |       | 1                  | 3.97×10−3 |
|          | 0.535 | I p(cid:23) (kgm2) |           |
2
| C1(Nms) | 6.54×10−2 |     |       |
| ------- | --------- | --- | ----- |
|         |           | K1  | 30.72 |
2.32×10−2
| C2(Nms) |           | K2  | 27.00 |
| ------- | --------- | --- | ----- |
| C3(Nms) | 8.80×10−3 |     |       |
friction coefficients C 1 , C 2 , C 3 , and C m1 , C m2 . It is assumed that the moments of
inertia are constants but with possible relative error of 10 % around the nominal
values;similarly,thefrictioncoefficientsmayhavewith15%relativeerrors.
TheeightrealuncertainparametersI , I , I , C , C , C , C , C aresetby
|     | 1 2 3 | 1 2 3 m1 | m2  |
| --- | ----- | -------- | --- |
usingthefollowingcommandlines:
i1 = ureal(’i1’,0.654,’Percentage’,10);
i2 = ureal(’i2’,0.117,’Percentage’,10);
i3 = ureal(’i3’,0.535,’Percentage’,10);

| 15.2 ModelingofUncertainties |     |     |     |     |     |     | 297 |
| ---------------------------- | --- | --- | --- | --- | --- | --- | --- |
Fig.15.4 Uncertainmodelof
thetripleinvertedpendulum
c1 = ureal(’c1’,0.0654,’Percentage’,15);
c2 = ureal(’c2’,0.0232,’Percentage’,15);
c3 = ureal(’c3’,0.0088,’Percentage’,15);
cd1 = ureal(’cd1’,0.00219,’Percentage’,15);
cd2 = ureal(’cd2’,0.000717,’Percentage’,15);
ThenitispossibletocomputetheuncertainmatricesM,N,Qwhichappearinthe
linearizedpendulummodel.
The uncertain pendulum model is obtained on the basis of the block-diagram
shown in Fig. 15.3 by using the function sysic. This pendulum model is imple-
mentedbytheM-filemod_pend.m.
Theinput/outputrelationoftheuncertainpendulummodelisdescribedby
|     |     | (cid:2) | (cid:3) | (cid:2) | (cid:3) |     |     |
| --- | --- | ------- | ------- | ------- | ------- | --- | --- |
|     |     |         | y       |         | d       |     |     |
=G
pend
|     |     |     | y p |     | t m |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
andisdepictedinFig.15.4.
Thesingularvalueplotoftheuncertainparameterstriple,invertedpendulumis
showninFig.15.5.
It should be pointed out that the uncertain pendulum model can be obtained in
severalways.Forinstance,itispossibletousethestatespacerepresentation,derived
onthebasisof(15.2),
|     |     |     |     | (cid:2) | (cid:3) |     |     |
| --- | --- | --- | --- | ------- | ------- | --- | --- |
A B
G =
|     |     |     | pend | C D |     |     |     |
| --- | --- | --- | ---- | --- | --- | --- | --- |
where
|     | (cid:2) |         | (cid:3) |     | (cid:2) |      | (cid:3) |
| --- | ------- | ------- | ------- | --- | ------- | ---- | ------- |
| A=  | 0 3× 3  | I 3×    | 3       | B=  | 0 3 × 3 | 0 3× | 2       |
|     | −       |         | − ,     |     | −       |      | −       |
|     | −M 1P   | −M      | 1N      |     | M 1 T   | −M   | 1G      |
|     | (cid:2) | (cid:3) |         |     |         |      |         |
|     | I 0     |         |         |     |         |      |         |
| C=  | 3× 3 3  | × 3     | D=0     |     |         |      |         |
|     |         | ,       |         | 6×5 |         |      |         |
|     | C p 0   | ×       |         |     |         |      |         |
|     | 3       | 3       |         |     |         |      |         |
In such a case, however, the uncertain parameters I , I , and I are repeated at
|     |     |     |     |     | 1 2 | 3   |     |
| --- | --- | --- | --- | --- | --- | --- | --- |
least twice in the model G such that the total number of uncertain parameters
pend
increase to 11. In the derivation, based on the block-diagram shown in Fig. 15.3,
the parameters I 1 , I 2 , and I 3 appear only once thus keeping the total number of
uncertainparametersequaltoeight.
Wenowconsiderthemodelsoftheactuators.Thenominaltransferfunctionsof
theactuatorsaretakenasfirst-order,phase-lagmodelsof
|     |     | K    | m1  |     | K m2 |     |     |
| --- | --- | ---- | --- | --- | ---- | --- | --- |
|     | G   | =    | ,   | G   | =    |     |     |
|     | m1  |      | s+1 | m2  | s+1  |     |     |
|     |     | T m1 |     |     | T m2 |     |     |

| 298 |     |     | 15 ATripleInvertedPendulumControlSystemDesign |     |     |     |     |
| --- | --- | --- | --------------------------------------------- | --- | --- | --- | --- |
Fig.15.5 Singularvaluesofthependulumsystem
withparameters
|     | =1.08, | =0.005, |     | =0.335, |     | =0.002 |     |
| --- | ------ | ------- | --- | ------- | --- | ------ | --- |
| K   | m1     | T m1    |     | K m2    |     | T m2   |     |
It is assumed that the actual gain coefficients (K m1 ,K m2 ) are constants with rela-
tiveerror10%aroundtheirnominalvaluesandthetimeconstants(T ,T )with
m1 m2
relativeerror20%.
TheuncertainfrequencyresponsesoftheactuatorsareshowninFig.15.6.
Inordertoaccountforunmodeleddynamicsandnonlineareffects,theuncertain-
ties in the actuator models are approximated by input multiplicative uncertainties
thatgiverisetotheperturbedtransferfunctions
|     | G =(1+W | δ )G  | ,   | G =(1+W | δ     | )G  |     |
| --- | ------- | ----- | --- | ------- | ----- | --- | --- |
|     | m1      | m1 m1 | m1  | m2      | m2 m2 | m2  |     |
where
|                           |     | |δ  | |≤1,            | |δ |≤1 |     |     |     |
| ------------------------- | --- | --- | --------------- | ------ | --- | --- | --- |
|                           |     | m1  |                 | m2     |     |     |     |
| andtheuncertaintyweightsW |     | ,W  | aresochosenthat |        |     |     |     |
|                           |     | m1  | m2              |        |     |     |     |
|G (jω)−G (jω)| (cid:18) (cid:18) |G (jω)−G (jω)| (cid:18) (cid:18)
| m1  | m1    | (cid:18) | (cid:18) | m2  | m2    | (cid:18) | (cid:18) |
| --- | ----- | -------- | -------- | --- | ----- | -------- | -------- |
|     |       | < W (jω) | ,        |     |       | < W (jω) | .        |
| |G  | (jω)| | m1       |          | |G  | (jω)| | m2       |          |
|     | m1    |          |          | m2  |       |          |          |
Notethatδ m1 ,δ m2 arecomplexuncertainparameterscorrespondingtouncertainLTI
dynamics.
The frequency responses of W , W are found graphically as shown in
m1 m2
Fig. 15.7 and then approximated by first-order transfer functions using the file
wfit.m.Asaresult,weobtain

15.2 ModelingofUncertainties 299
Fig.15.6 Uncertainfrequencyresponsesoftheactuators

300 15 ATripleInvertedPendulumControlSystemDesign
Fig.15.7 Actuatorsuncertaintyapproximations

| 15.2 | ModelingofUncertainties |     |     |     |     |     |     | 301 |
| ---- | ----------------------- | --- | --- | --- | --- | --- | --- | --- |
Fig.15.8 Block-diagramof
theuncertainactuatorsmodel
Fig.15.9 Tripleinverted
pendulumsystemwith
uncertainties
|     |     | 0.3877s+25.6011  |     |     |     | 0.3803s+60.8973  |     |     |
| --- | --- | ---------------- | --- | --- | --- | ---------------- | --- | --- |
|     | W   | =                |     | , W | =   |                  |     |     |
|     | m1  | 1.0000s+246.3606 |     |     | m2  | 1.0000s+599.5829 |     |     |
Byintroducingthevectoru=[u ]T,theequationsoftheactuatorsarerewritten
|     |     |     |     | 1 ,u 2 |     |     |     |     |
| --- | --- | --- | --- | ------ | --- | --- | --- | --- |
as
t =G u
m act
where
|     | =G  | +W  |     |     |     |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
G act (cid:2)m (I 2 m(cid:3)m Δ ), (cid:2) (cid:3) (cid:2) (cid:3)
|     | G   |     | 0   | W    | 0   |     | δ    | 0   |
| --- | --- | --- | --- | ---- | --- | --- | ---- | --- |
|     | =   | m1  |     | = m1 |     |     | = m1 |     |
|     | G m |     | ,   | W m  |     | ,   | Δ m  |     |
|     |     | 0 G |     | 0    | W   |     | 0    | δ   |
|     |     |     | m2  |      | m2  |     |      | m2  |
The block-diagram of the actuators with the input multiplicative uncertainty is
showninFig.15.8.
The uncertain actuators model is obtained by using the file act_pend.m that
containsthefollowingcommandlines:
| %          | First           | actuator |                         |      |     |             |     |     |
| ---------- | --------------- | -------- | ----------------------- | ---- | --- | ----------- | --- | --- |
| gd1        | = 1.080;        |          | Td1 = 0.005;            |      |     |             |     |     |
| G1         | = tf([gd1],[Td1 |          |                         | 1]); |     |             |     |     |
| Wm1        | = tf([0.3877    |          | 25.6011],[1.0000        |      |     | 246.3606]); |     |     |
| Delta_act1 |                 | =        | ultidyn(’Delta_act1’,[1 |      |     | 1]);        |     |     |
| Act1       | = G1*(1         |          | + Wm1*Delta_act1);      |      |     |             |     |     |
%
| %          | Second          | actuator |                         |      |     |             |     |     |
| ---------- | --------------- | -------- | ----------------------- | ---- | --- | ----------- | --- | --- |
| gd2        | = 0.335;        |          | Td2 = 0.002;            |      |     |             |     |     |
| G2         | = tf([gd2],[Td2 |          |                         | 1]); |     |             |     |     |
| Wm2        | = tf([0.3803    |          | 60.8973],[1.0000        |      |     | 599.5829]); |     |     |
| Delta_act2 |                 | =        | ultidyn(’Delta_act2’,[1 |      |     | 1]);        |     |     |
| Act2       | = G2*(1         |          | + Wm2*Delta_act2);      |      |     |             |     |     |
Note that the uncertain LTI dynamics δ , δ are set implementing the function
1 2
ultidyn.
Havingmodeledboththependulumandtheactuatorswithconsiderationofpos-
sibleperturbations,theblock-diagramof thewholesystemisseenasinFig.15.9.
Notethatwehaveacaseofamixed,real,andcomplex,uncertaintyconfiguration.

302 15 ATripleInvertedPendulumControlSystemDesign
Fig.15.10 Uncertainmodel
ofthetripleinverted
pendulumsystem
Fig.15.11 Interconnection
structureoftheclosed-loop
system
Thewhole,perturbed,tripleinvertedpendulumsystemcanbedescribedbythe
equation
(cid:2) (cid:3) (cid:2) (cid:3)
y d
=G
y sys u
p
where the uncertain state-space system G can be easily obtained by using the
sys
functionsysic.ThesystemisshowninFig.15.10andcontains10uncertainpa-
rameters(eightrealandtwoLTIdynamics).
15.3 DesignSpecifications
The block-diagram of the closed-loop system, which includes the triple inverted
pendulum model, the feedback structure and the controller, as well as the ele-
mentsreflectingthemodeluncertaintyandtheperformanceobjectives,isdepicted
inFig.15.11.Inordertoachievebetterperformance,weshallmakeuseofthecon-
figurationofa2-degree-of-freedom(2DOF)controller.
The system has a reference input (r), an input disturbance (d), a measurement
noise (η) and two output costs (e and e ). The system W is an ideal dynamics
y u m
model to which the designed closed-loop system has to match. The model of the
tripleinvertedpendulumsystemistheuncertainstate-spacesystemG .Thefeed-
sys
backsignalisgeneratedonthebasisofthepotentiometersoutputy =C y,which
p p
requires the reference r to be multiplied by the matrix C (the other way to deal
p
with the situation is to multiply y by C
−1).
The measurement of the arm angles
p p
isaccompaniedbyintroductionoffrequency-dependentnoisesthatareinevitablein
practiceandarethusaddedtothecorrespondingmeasurements.Thisiswhyatthe
outputsofthepotentiometersoneobtainsthesignaly =−(y +W η),whereW is
c p n n
aweightingfunction(shapingfilteronthemeasurementnoise)andη=[η η η ]T
1 2 3

15.3 DesignSpecifications 303
Fig.15.12 Measurementnoiseweightingfunction
isanarbitrarynoisesignalsatisfying(cid:5)η(cid:5) ≤1.BychoosinganappropriateW itis
2 n
possibletoformthedesiredspectralcontentsoftheactualnoisesignal(intheform
ofW n η).
| InthegivencasethematrixW |     | ischosenas |     |
| ------------------------ | --- | ---------- | --- |
n
|     |       | ⎡         | ⎤       |
| --- | ----- | --------- | ------- |
|     |       | w n (s) 0 | 0       |
|     | (s)=⎣ |           | ⎦       |
|     | W     | 0 w (s)   | 0       |
|     | n     | n         |         |
|     |       | 0 0       | w n (s) |
|     |       | =2×10     | −510s+1 |
wheretheweightingtransferfunctionw n 0.1s+1 isahighpassfilterthat
shapesthenoisespectraldensityforthetypeofpotentiometersunderconsideration.
ThemagnitudeplotofthisfilterisshowninFig.15.12.Thistransferfunctionmeans
that in the low-frequency range the magnitude of the measurement error is about
| −5                                           |     |                         | −3           |
| -------------------------------------------- | --- | ----------------------- | ------------ |
| 2×10 V,andinthehigh-frequencyrange,about2×10 |     |                         | V.           |
| Asforfeedbacksignals,weshallusey             |     | =−(y                    | +W η)andC r. |
|                                              |     | c                       | p n p        |
| Theweightedclosed-loopoutputse               |     | ande satisfytheequation |              |
y u
|     |         | ⎡       | ⎤   |
| --- | ------- | ------- | --- |
|     | (cid:2) | (cid:3) |     |
r
|     |     | e y ⎣   | ⎦   |
| --- | --- | ------- | --- |
|     |     | =Φ(s) d |     |
e
|     |     | u η |     |
| --- | --- | --- | --- |
wherethematrixΦ=Φ(G
)istheuncertainclosed-looptransferfunctionmatrix.
sys
The performance objective requires the transfer function matrix Φ(s) from r,
(cid:5)·(cid:5)
d and η to e y and e u to be small in the sense of ∞, for all possible (stable)

304 15 ATripleInvertedPendulumControlSystemDesign
uncertainties. The appropriately chosen weighting functions matrices W p and W u
areusedtoreflecttherelativesignificanceoverdifferentfrequencyrangesforwhich
theperformanceisrequired.
The design problem for the triple inverted pendulum system is to find a linear,
outputcontrollerK(s)togeneratetheoutputfeedback
|           | (cid:2) | (cid:3) |     |
| --------- | ------- | ------- | --- |
|           | y (s)   |         |     |
| u(s)=K(s) | c       |         |     |
|           | C r(s)  |         |     |
p
toensurethefollowingpropertiesoftheclosed-loopsystem.
15.3.1 Robust Stability
Theclosed-loopsystemachievesrobuststabilityiftheclosed-loopsystemisinter-
nallystableforeachpossible,perturbedplantdynamicsG .
sys
15.3.2 NominalPerformance
Theclosed-loopsystemachievesnominalperformanceifthefollowingperformance
objectiveissatisfiedforthenominalplantmodelG :
|     | (cid:24) (cid:24) | sysnom |        |
| --- | ----------------- | ------ | ------ |
|     | (cid:24) (cid:24) |        |        |
|     | Φ(G ) <1          |        | (15.3) |
sysnom ∞
ThisobjectiveissimilartothemixedS/KS sensitivityoptimization.
15.3.3 Robust Performance
Theclosed-loopsystemmustmaintain,foreachG ,theperformanceobjective
sys
(cid:24) (cid:24)
(cid:24) (cid:24)
|     | Φ(G sys ) ∞ <1 |     | (15.4) |
| --- | -------------- | --- | ------ |
Inadditiontotheaboverequirements,itisdesirablethatthecontrollerdesigned
wouldhaveacceptablecomplexity,i.e.itisofreasonablyloworder.
Theidealsystemmodeltobematchedwith,ischosenas
| ⎡     |            | ⎤     |     |
| ----- | ---------- | ----- | --- |
|       | w m1 (s) 0 | 0     |     |
| (s)=⎣ |            | ⎦     |     |
| W     | 0 w (s)    | 0     |     |
| m     | m2         |       |     |
|       | 0 0        | w (s) |     |
m3
where
1
| w   | (s)=        |     |     |
| --- | ----------- | --- | --- |
| m1  | 100s2+14s+1 |     |     |
1
(s)=
w m2
25s2+7s+1
1
(s)=
w m3
9s2+4.2s+1

15.3 DesignSpecifications 305
Fig.15.13 Modelfrequencyresponses
This model takes into account that the first arm has the slowest dynamics and the
thirdarm—thefastestone.
ThemagnituderesponsesofthemodelareshowninFig.15.13.
Inthegivencasetheweightingperformancefunctionsarechosenintheformsof
| ⎡   |     | ⎤   |     |     |
| --- | --- | --- | --- | --- |
(cid:2) (cid:3)
|         | w (s) 0 | 0     |        |         |
| ------- | ------- | ----- | ------ | ------- |
|         | p 1     |       |        | w (s) 0 |
| W (s)=⎣ | 0 w (s) | 0 ⎦ , | W (s)= | u       |
| p       | p2      |       | u      | w (s)   |
0 u
|     | 0 0 | w p3 (s) |     |     |
| --- | --- | -------- | --- | --- |
where
s2+2s+4
|     | (s)=1×10 | −2  |     |     |
| --- | -------- | --- | --- | --- |
w p1
s2+1.5s+0.1
s2+2s+4
|     | w (s)=2×10 | −2           |     |     |
| --- | ---------- | ------------ | --- | --- |
|     | p2         | s2+1.5s+0.01 |     |     |
s2+2s+4
−2
w (s)=4×10
|     | p3  | s2+1.5s+0.01 |     |     |
| --- | --- | ------------ | --- | --- |
−6 s+1
| andw (s)=10 | .        |     |     |     |
| ----------- | -------- | --- | --- | --- |
| u           | 0.001s+1 |     |     |     |
TheweightingfunctionsaresetintheM-filewts_pend.m.
−1
The magnitude responses of the inverse weighting function W are shown in
p
Fig.15.14.Itisseenfromthefigurethate istheleastpenalizedoutput,whilee
y1 y3
isthemostpenalizedone.Suchachoiceoftheweightingfunctionsisjustifiedby

306 15 ATripleInvertedPendulumControlSystemDesign
Fig.15.14 Frequencyresponsesoftheinverseweightingfunction
thefactthatthevariabley =Θ isnotcontrolleddirectlyandthaty hasthefastest
1 1 3
dynamics.
15.4 System Interconnections
Theinternalstructureofthe11-input,11-output30thorderopen-loopsystem,which
is saved as the variable pend_ic, is shown in Fig. 15.15. The reference, the dis-
turbanceandthenoisearesavedinthevariablesref,dist,noise,respectively.
Thecontrolsignalissavedinthevariablecontrol.
The variables ref, dist, noise, y, y_p, y_c, e_y have all three elements
andthevariablescontrol, e_uhavetwoelements.Theopen-loopconnection
isassignedbytheM-fileolp_pendusingthefunctionsysic.
The schematic diagram showing the specific input/output ordering for the vari-
ablepend_icisshowninFig.15.16.
The block-diagram used in the closed-loop system simulation is shown in
Fig. 15.17. The corresponding closed-loop interconnection, which is saved in the
variablepend_sm,isobtainedbytheM-filesim_pend.
Figure15.18showstheschematicdiagramofthespecificinput/outputordering
forthevariablepend_sm.

15.4 SystemInterconnections 307
Fig.15.15 Open-loopinterconnectionofthetripleinvertedpendulumsystem
Fig.15.16 Schematicdiagramoftheopen-loopsystem
Fig.15.17 Closed-loop
interconnectionstructureof
thependulumsystem

308 15 ATripleInvertedPendulumControlSystemDesign
Fig.15.18 Schematicdiagramoftheclosed-loopsystem
Fig.15.19 Blockdiagram
forH∞design
15.5 H ∞ Design
The design goal in this case is to find an H ∞ (sub)optimal control law for the in-
terconnection shown in Fig. 15.19, in which we make use of the nominal system
model.Thevariablehin_ic,whichcorrespondstothenominaltransferfunction
matrixP oftheaugmentedsystem,isobtainedbythecommandline
nom
hin_ic = pvget(pend_ic,’NominalValue’);
The H ∞ optimalcontrolminimizesthe (cid:5)·(cid:5) ∞ normof F L (P nom ,K) overthesta-
bilizingcontrollertransfermatrixK.InthegivencaseF (P ,K)isthenominal
L nom
closed-loopsystemtransfermatrixfromthereferences,disturbancesandnoises(the
signalsr,d,andη)totheweightedoutputse ande (Fig.15.19).
y u
TheH ∞ designisconductedbyusingtheM-filehinf_pend.m.Itutilizesthe
functionhinfsyn,whichdeterminesa(sub)optimalH ∞controllaw,basedonthe
prescribedopen-loopinterconnection.Theintervalforγ iterationischosenbetween
0and10withatolerancetol=0.001.Thecontrollerobtainedisof30thorderand
for this controller the closed-loop system achieves H ∞ norm equal to 0.4346. An
undesiredpropertyofthecontrolleristhatithasapoleat68.71,i.e.thiscontroller
isunstable,whichmakesitlessfavorableinpractice.
The singular value plot of the H ∞ controller transfer matrix is shown in
Fig.15.20.

15.5 H∞Design 309
Fig.15.20 SingularvaluesoftheH∞controller
Sincetheclosed-loopsystemdoesnotachieverobuststability,itismeaningfulto
obtainthesystemtransientresponsesonlyforthenominalparameters.Theclosed-
loop, transient responses (reference tracking) for the nominal model are obtained
byusingthefileclp_pend.Thetransientresponseoftheclosed-loopsystemwith
H ∞ controllerforthereferencevector
⎡ ⎤
0
r=⎣−0.1 ⎦
0.2
(the references are measured in radians) is shown in Fig. 15.21. The response is
characterized by small overshoots of the output variables. The steady-state errors
aresmall,exceptforasmallerroronthepositionofthefirstarm.
The disturbance rejection of the closed-loop system with the H ∞ controller is
showninFig.15.22.Thedisturbancevectorissetto
⎡ ⎤
0.1
d=⎣
0.1
⎦
0.1
andmeasuredinNm.
InFig.15.23weshowthesingularvaluesplotoftheuncertainclosed-looptrans-
fer matrix with the H ∞ controller. It is seen from the figure that for some values
oftheuncertainparametersthemagnituderesponseshaveveryhighpicksthatmay
indicatepotentialinstabilityoftheclosedloopsystem.

310 15 ATripleInvertedPendulumControlSystemDesign
Fig.15.21 Closed-looptransientresponseofH∞controller
Fig.15.22 DisturbancerejectionofH∞controller

15.5 H∞Design 311
| Fig.15.23 | Closed-loopsingularvalueswithH∞controller |     |     |     |     |     |     |
| --------- | ----------------------------------------- | --- | --- | --- | --- | --- | --- |
The robust stability analysis of the closed-loop system is done by the file
mu_pend implementing the function robuststab. A a result one obtains the
followingreport:
report =
| Uncertain | System | is  | NOT robustly |     | stable | to modeled |     |
| --------- | ------ | --- | ------------ | --- | ------ | ---------- | --- |
uncertainty.
| -- It              | can tolerate |         | up to       | 38.2%        | of the         | modeled | uncertainty. |
| ------------------ | ------------ | ------- | ----------- | ------------ | -------------- | ------- | ------------ |
| -- A destabilizing |              |         | combination |              | of 38.3%       | of      | the modeled  |
| uncertainty        |              | exists, | causing     |              | an instability |         |              |
| at                 | 10.5 rad/s.  |         |             |              |                |         |              |
| -- Sensitivity     |              | with    | respect     | to           | uncertain      | element | ...          |
| ’Delta_act1’       |              | is 54%. | Increasing  |              | ’Delta_act1’   |         | by 25%       |
|                    |              | leads   | to a        | 14% decrease |                | in the  | margin.      |
| ’Delta_act2’       |              | is 21%. | Increasing  |              | ’Delta_act2’   |         | by 25%       |
|                    |              | leads   | to a        | 5% decrease  |                | in the  | margin.      |
| ’c1’               |              | is 0%.  | Increasing  |              | ’c1’           | by 25%  | leads        |
|                    |              | to a    | 0% decrease |              | in the         | margin. |              |
| ’c2’               |              | is 0%.  | Increasing  |              | ’c2’           | by 25%  | leads        |
|                    |              | to a    | 0% decrease |              | in the         | margin. |              |
| ’c3’               |              | is 0%.  | Increasing  |              | ’c3’           | by 25%  | leads        |
|                    |              | to a    | 0% decrease |              | in the         | margin. |              |
| ’cm1’              |              | is 15%. | Increasing  |              | ’cm1’          | by      | 25% leads    |
|                    |              | to a    | 4% decrease |              | in the         | margin. |              |

| 312       |                                   |         |             | 15 ATripleInvertedPendulumControlSystemDesign |                |           |     |
| --------- | --------------------------------- | ------- | ----------- | --------------------------------------------- | -------------- | --------- | --- |
| Fig.15.24 | RobuststabilitytestofH∞controller |         |             |                                               |                |           |     |
| ’cm2’     |                                   | is 0%.  | Increasing  |                                               | ’cm2’ by       | 25% leads |     |
|           |                                   | to a    | 0% decrease |                                               | in the margin. |           |     |
| ’i1’      |                                   | is 23%. | Increasing  |                                               | ’i1’ by        | 25% leads |     |
|           |                                   | to a    | 6% decrease |                                               | in the margin. |           |     |
| ’i2’      |                                   | is 7%.  | Increasing  |                                               | ’i2’ by        | 25% leads |     |
|           |                                   | to a    | 2% decrease |                                               | in the margin. |           |     |
| ’i3’      |                                   | is 31%. | Increasing  |                                               | ’i3’ by        | 25% leads |     |
|           |                                   | to a    | 8% decrease |                                               | in the margin. |           |     |
The upper and lower bounds of the structured singular value μ (over the fre-
quencyrange)areshowninFig.15.24.Theclosed-loopsystemwithH
∞controller
doesnotachieverobuststability,themaximumvalueofμexceeding2.6.Itfollows
fromthereportthattheuncertainparametersC ,C ,C ,andC practicallydonot
|     |     |     |     |     | 1 2 3 | m2  |     |
| --- | --- | --- | --- | --- | ----- | --- | --- |
affecttherobuststability.
Therobustperformanceoftheclosed-loopsystemwithH ∞controllerischecked
withthefunctionrobustperf.Asaresultweobtainthefollowingreport:
| report    | =      |          |     |     |                    |     |        |
| --------- | ------ | -------- | --- | --- | ------------------ | --- | ------ |
| Uncertain | System | achieves |     | a   | robust performance |     | margin |
of 0.3822.
| -- A model     |               | uncertainty |         | exists | of size      | 38.1%   | resulting |
| -------------- | ------------- | ----------- | ------- | ------ | ------------ | ------- | --------- |
| in             | a performance |             | margin  |        | of 2.62 at   | 10.5    | rad/s.    |
| -- Sensitivity |               | with        | respect |        | to uncertain | element | ...       |

15.6 μ-Synthesis 313
Fig.15.25 RobustperformanceofH∞controller
Theμvaluescorrespondingtothecaseofrobustperformanceanalysisareshown
in Fig. 15.25. Again, the closed-loop system does not achieve robust performance
either.
Hence,itisconcludedthatthedesignedH ∞controllerleadstogoodclosed-loop
transientresponses,butdoesnotensurethenecessaryrobustnessoftheclosed-loop
systemasrequired.
15.6 μ-Synthesis
LetusdenotebyP(s)thetransferfunctionmatrixofthe11-input,11-output,open-
loopsystemconsistingofthependulumsystemmodelplustheweightingfunctions,
andlettheblockstructureΔ ofuncertaintiesbedefinedby
P
%(cid:2) (cid:3) &
Δ := Δ 0 :Δ∈R10×10, Δ ∈C9×5
P 0 Δ F
F
ThefirstblockofthematrixΔ ,theuncertaintyblockΔ,correspondstothepara-
P
metric and LTI uncertainties modeled in the triple inverted pendulumsystem. The
secondblock,Δ ,isafictitiousuncertaintyblock,introducedtoincludetheperfor-
F
manceobjectivesintheframeworkoftheμ-approach.Theinputstothisblockare
the weighted error signals e and e the outputs being the exogenous inputs r, d,
y u
andη.

| 314       |               |     |           | 15 ATripleInvertedPendulumControlSystemDesign |                 |     |                 |     |
| --------- | ------------- | --- | --------- | --------------------------------------------- | --------------- | --- | --------------- | --- |
| Table15.3 | D–Kiterations |     |           |                                               |                 |     |                 |     |
|           |               |     | Iteration |                                               | Controllerorder |     | Maximumvalueofμ |     |
resultsinμ-synthesis
|     |     |     | 1   |     | 30  |     | 2.400 |     |
| --- | --- | --- | --- | --- | --- | --- | ----- | --- |
|     |     |     | 2   |     | 68  |     | 0.810 |     |
|     |     |     | 3   |     | 82  |     | 0.525 |     |
|     |     |     | 3   |     | 80  |     | 0.458 |     |
TomeetthedesignobjectivesastabilizingcontrollerK istobefoundsuchthat,
ateachfrequencyω∈[0,∞],thestructuredsingularvalueμsatisfiesthecondition
|     |     |     | (cid:4) |               |     | (cid:5) |     |     |
| --- | --- | --- | ------- | ------------- | --- | ------- | --- | --- |
|     |     |     | μ ΔP    | F L (P,K)(jω) |     | <1      |     |     |
Thefulfillmentofthisconditionguaranteesrobustperformanceoftheclosed-loop
system,i.e.,
|                                               |     |     | (cid:24) |         | (cid:24) |     |     |     |
| --------------------------------------------- | --- | --- | -------- | ------- | -------- | --- | --- | --- |
|                                               |     |     | (cid:24) |         | (cid:24) |     |     |     |
|                                               |     |     |          | Φ(G sys | ) ∞ <1   |     |     |     |
| forallstableperturbationsΔwith(cid:5)Δ(cid:5) |     |     |          | ∞<1.    |          |     |     |     |
The μ-synthesis is conducted by using the M-file ms_pend.m implementing
thefunctiondksyn.
The μ-synthesis is done for the same performance and control action weight-
H
ing functions as the ∞ design. The progress of the D–K iteration is shown in
Table15.3.
Four iterations are done reducing the maximum value of μ to 0.458. The final
controllerobtainedisof80thorder.Notethatthiscontrollerisstable.
Thesingularvalueplotoftheμ-controllerisshowninFig.15.26.
The robust stability and robust performance analysis of the closed-loop system
withμ-controlleryieldsthefollowingresults:
report =
| Uncertain          | System       | is      | robustly    | stable |                | to modeled | uncertainty. |     |
| ------------------ | ------------ | ------- | ----------- | ------ | -------------- | ---------- | ------------ | --- |
| -- It              | can tolerate |         | up to       | 266%   | of the         | modeled    | uncertainty. |     |
| -- A destabilizing |              |         | combination |        | of 273%        | of         | the modeled  |     |
| uncertainty        |              | exists, | causing     |        | an instability |            |              |     |
| at                 | 3.43 rad/s.  |         |             |        |                |            |              |     |
| -- Sensitivity     |              | with    | respect     | to     | uncertain      |            | element ...  |     |
report =
| Uncertain | System | achieves |     | a robust | performance |     | margin |     |
| --------- | ------ | -------- | --- | -------- | ----------- | --- | ------ | --- |
of 2.238.
| -- A model     | uncertainty |        | exists  |       | of size   | 223%   | resulting   | in a |
| -------------- | ----------- | ------ | ------- | ----- | --------- | ------ | ----------- | ---- |
| performance    |             | margin | of      | 0.448 | at 0.1    | rad/s. |             |      |
| -- Sensitivity |             | with   | respect | to    | uncertain |        | element ... |      |
Thestructuredsingularvaluesfortherobuststabilitystudy(overthefrequency
range)areshowninFig.15.27.

15.6 μ-Synthesis 315
Fig.15.26 Singularvaluesoftheμ-controller
Fig.15.27 Robuststabilityofμcontroller

316 15 ATripleInvertedPendulumControlSystemDesign
Fig.15.28 Robustperformanceofμcontroller
Theμvaluesoverthefrequencyrangeforthecaseofrobustperformanceanaly-
sisareshowninFig.15.28.
Considernowtheclosed-looptransientresponses.Sincetheclosed-loopsystem
achieves robust stability and performance, it is possible to obtain the transient re-
sponsesfordifferentvaluesoftheuncertainparameters.Thisisdonebyusingthe
M-filemcs_pend.m.Thesamereferencesignalasusedinthe H ∞ simulationis
usedhere.Thatis,
⎡ ⎤
0
r=⎣−0.1 ⎦
0.2
Thetransientresponseoftheuncertainclosed-loopsystemisshowninFig.15.29.
TheresponseisslightlyslowerthaninthecaseofH ∞ controller.
Thecontrolactioninthecaseofaμ-controllerisshowninFig.15.30.Themotor
voltagesarekeptwithin0.14Vforallpossibleperturbations.
The disturbance rejection of the uncertain closed-loop system with the μ-
controller is shown in Fig. 15.31. We see that the overshoot of the third output is
almost5timeslargerthaninthecaseoftheH ∞ controller.
Hence, it is clear that the (nominal) transient responses in terms of reference
trackinganddisturbanceattenuationareworseinthecaseoftheμ-controller.This
isthepricethathastobepaidtoensuretherobuststabilityandrobustperformance
oftheclosed-loopsystem.

15.6 μ-Synthesis 317
Fig.15.29 Closed-looptransientresponseofμ-controller
Fig.15.30 Controlactionofμ-controller
InFig.15.32,weshowthenoisew η ,whichactsattheoutputofthethirdpo-
n 3
tentiometer,andthecorrespondingresponseoftheoutputy .Fromthemagnitudes
3
of w η and y , one may conclude that the closed-loop system is susceptible to
n 3 3
noises.

318 15 ATripleInvertedPendulumControlSystemDesign
Fig.15.31 Disturbancerejectionofμ-controller
Theclosed-loopfrequencyresponsesoftheuncertainclosed-loopsystemareob-
tainedbytheM-filefrs_pend.m.Thesingularvaluesoftheclosed-looptransfer
matrix with the μ-controller are plotted in Fig. 15.33. The comparison with the
plotshowninFig.15.23revealsthattheclosed-loopbandwidthinthecaseofaμ-
controllerisslightlysmaller,whichleadstoaslowerresponseandworsedisturbance
attenuation.IncontrasttothecaseofH ∞ controller,theclosed-loopfrequencyre-
sponsesdonothavepeaks.
Thesingularvaluesofthetransferfunctionmatrixconcerningdisturbancerejec-
tion are shown in Fig. 15.34. We see that the disturbance attenuation is worst for
frequenciesaround1rad/s.
From the singular values plot of the transfer function matrix concerning noise
attenuation,showninFig.15.35,weseethattheinfluenceofnoisesonthesystem
outputwouldbemaximalforfrequenciesbetween1rad/sand10rad/s.
Asmentionedearlier,the controllerobtainedby μ-synthesis is initiallyof 80th
order, which makes its implementation in practice very difficult. Therefore, it is
necessary to reduce the controller order. For this purpose, we implements the M-
filered_pend.mimplementingthefunctionreduce.Thisfunctionallowsusto
reduce the controller order to 25. Further reduction of the controller order leads
to deterioration of the closed-loop transient responses and would even cause the
instabilityoftheclosed-loopsystem.
In Fig. 15.36 we compare the singular values frequency responses of the full-
orderandreduced-orderμ-controllers.Uptothefrequency104 rad/sthefrequency
plotsofbothcontrollerscoincidewitheachother,whichimpliesverysimilarperfor-
manceoftheclosed-loopsystems.Infact,theclosed-looptransientresponseswith

15.6 μ-Synthesis 319
Fig.15.32 Sensornoiseandclosed-loopnoiseresponse
thefull-ordercontrollerandthosewiththereduced-ordercontroller(notincludedin
thebook)arepracticallyundistinguishable.
A discrete-time controller may be obtained by sampling the already designed
continuous-time controller for a sampling frequency f =1/T . This can be con-
s s
ductedbytheM-filedcl_pend.m,whichutilizesthefunctionc2d.Theresulting,
sampled-dataclosed-loopsystemcanbesimulatedbyusingthefunctionsdlsim.

320 15 ATripleInvertedPendulumControlSystemDesign
Fig.15.33 Closed-loopsingularvalueplot
Fig.15.34 Singularvaluesofthedisturbancerejectiontransferfunctionmatrix

15.6 μ-Synthesis 321
Fig.15.35 Singularvaluesofthenoise-attenuationtransferfunctionmatrix
Fig.15.36 Frequencyresponsesofthefull-andreduced-ordercontrollers

322 15 ATripleInvertedPendulumControlSystemDesign
Since the inverted pendulum is a relatively slow system, the sampling frequency
maybechosentobesmall.Forinstance,ifthisfrequencyis100Hzthenthetran-
sientresponsesofthesampled-datasystemareclosetothecorrespondingresponses
ofthecontinuous-timesystem.
15.7 NonlinearSystem Simulation
The nonlinear,closed-loop system of the triple inverted pendulum is simulated by
using the Simulink® models c_pend.mdl (for the continuous-time system) and
d_pend.mdl(forthesampled-datasystem).Bothmodelsallowustosimulatethe
closed-loop system for different references, disturbances and noise signals. Both
modelsutilizetheM-fileS-functions_pend.mthatincludesthenonlineardiffer-
entialequations(15.1)ofthetripleinvertedpendulum.Theinitialconditionsofthe
pendulumareassignedintheM-fileinc_pend.m.
Thesampled-datamodelconsistsofthediscretizedcontroller,a14-bitanalogue-
to-digital converter with maximum input voltage 5 V, and a 14-bit digital-to-
analogue converter with maximum output voltage 5 V. It is assumed that the cal-
culationofthecontrolactionrequiresnolongerthanonesamplingperiodT .
s
Before simulating the system it is necessary to set the model parameters by
using the M-file init_c_pend.m (in the continuous-time case) or the M-file
init_d_pend.m(inthediscrete-timecase).
The simulation of the nonlinear system for small references and disturbances
producesresultsthatareveryclosetotheresultsobtainedforthelinearizedmodel.
TheSimulink®modelc_pend.mdlofthecontinuous-time,nonlinear,pendu-
lumsystemisshowninFig.15.37.
In Fig. 15.38 we show the transient response of the continuous-time, nonlinear
systemforareferencer=[0−0.10.2]T.Thetransientresponseisclosetothatof
thelinearsystem(Fig.15.29).
Sincethetripleinvertedpendulumisessentiallynonlinear,thesimulationresults
maydifferinthecaseoflargereferencesanddisturbances.Toillustratethispoint,in
Fig.15.39weshowthetransientresponseofthecontinuous-time,nonlinearsystem
forareferencer=[000.6]T.
15.8 Conclusions
Theexperiencegainedinthedesignofthetripleinvertedpendulumcontrolsystem
makesitpossibletomakethefollowingcomments.
• Theuncertaintymodelofthetripleinvertedpendulumsysteminvolvesstructured
(parametric) as well as unstructured uncertainty. Some care is necessary in de-
riving the pendulum uncertainty model in order to minimize the number of the
uncertainparameters.

15.8 Conclusions 323
metsysraenilnonehtfoledomnoitalumiS
73.51.giF

324 15 ATripleInvertedPendulumControlSystemDesign
Fig.15.38 Transientresponseofthenonlinearsystem—smallreference
Fig.15.39 Transientresponseofthenonlinearsystem—largereference

15.9 NotesandReferences 325
• Theuseofa2-degree-of-freedomcontrolstructureallowsustoobtainacceptable
performanceaswellasrobustnessoftheclosed-loopsystem.
• The necessity to achieve robust stability and robust performance of the closed-
loop system leads to decrease of the closed-loop bandwidth that in turn leads
to slower response and worse disturbance attenuation. Thus, there is a trade-off
between nominal performance and robustness of the closed-loop system. In the
givencaseanacceptabletrade-offisachievedbyusingaμ-controller.
• The order of the μ-controlleris very high that thus requires controller order re-
duction to preserve the closed-loop performance and robustness while making
implementationofthecontrollereasierandmorereliable.
• The triple inverted pendulum is an essentially nonlinear system and the results
obtained by using the linearized model are valid only for sufficiently small arm
anglesandarmvelocities.
15.9 Notesand References
TheinvertedpendulumisintroducedintoControlEngineeringbytheJapanesesci-
entistKatsuhisaFurutaandhiscolleaguesfromTokyoInstituteofTechnology[47]
and is frequently called Furuta pendulum. As noted in [187] the inverted pendu-
lum is frequently used as a good example to show the power of modern control
theory.Thedesignofinvertedpendulumcontrolsystemsisinitiallydonebyusing
state-spacemethods[122].
Thesingleanddoubleinvertedpendulumsarerelativelyeasytostabilizebyusing
linearcontrollers[47,91,182].Thetripleinvertedpendulumismoredifficulttocon-
trolanditisverysensitivetotorquedisturbances,jointfrictionsandmeasurement
noises[164].Thedesignofanalogueanddigitalcontrollersfortripleinvertedpen-
dulumsystemshasbeenconsideredinseveralpapers(see,forinstance,[48,115]).
References[37,113]addressthechallengingproblemofstabilizingatripleinverted
pendulum,acartsystemthatusesonlyoneactuator.
Therobustcontrolofdifferenttypesofinvertedpendulumisconsideredinsev-
eralpublications,see,forinstance,[81,114,164,167].

Chapter 16
Robust Control of a Distillation Column
In this chapter we present the design of a robust control system for a high-purity
distillation column. The original nonlinear model of the column is of high order
anditincludesparametricgainandtime-delayuncertainty.Alow-orderlinearized
distillationcolumnmodelisusedinthedesignofa1-degree-of-freedomH ∞ loop-
shapingcontrolleranda2-degree-of-freedom(2DOF)μ-controller.Bothcontrollers
ensure robust stability of the closed-loop system and fulfillment of a mixture of
time-domainandfrequency-domainspecifications.Areducedorderμ-controlleris
thenfoundthatpreservestherobuststabilityandrobustperformanceoftheclosed-
loopsystem.Thesimulationoftheclosed-loopsystemwiththenonlineardistillation
columnmodelshowsverygoodperformancefordifferentreferenceanddisturbance
signalsaswellasfordifferentvaluesoftheuncertainparameters.
16.1 Introduction
Distillationisanimportantprocessintheseparationandpurificationofchemicals.
Theprocessexploitsthedifferenceatboilingpointsofmulticomponentliquids.The
controlofdistillationcolumnsisdifficult,becausethedistillationprocessishighly
nonlinearandthecorrespondinglinearizedmodelsareoftenill-conditionedaround
theoperatingpoint.
The aim of the design, presented in this chapter, is to find a controller that
achievesrobuststabilityandrobustperformanceoftheclosed-loopcontrolsystem
of a high-purity distillation column. The original nonlinear model of the column
is of 82nd order and it includes uncertainties in the form of parametric gains and
timedelay.Theuncertaintymodelisconsideredintheformofaninputmultiplica-
tivecomplexuncertainty.Inourdesignexerciseswetrytoachievethedesiredper-
formance of the closed-loop system using 1-degree-of-freedom H ∞ loop-shaping
design procedure and 2-degree-of-freedom μ-synthesis/analysis method. The de-
signsarebasedonasixth-orderlinearizeddistillationcolumnmodel.Bothdesigned
controllers ensure robust stability of the closed-loop system and achieve a mixed
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 327
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_16,©Springer-VerlagLondon2013

328 16 RobustControlofaDistillationColumn
Fig.16.1 Thedistillationcolumnsystem
setoftime-domainandfrequency-domainspecifications.Wepresentseveraltime-
domainandfrequency-domaincharacteristicsofthecorrespondingclosed-loopsys-
tems that makes possible the comparison of controllers efficiency. A 12th-order
reduced-order μ-controller is found that preserves the stability and performance
of the closed-loop system in the presence of uncertainties. The simulation of the
closed-loop system with this μ-controller and with the nonlinear distillation col-
umnmodelisconductedinSimulink®andshowsverygoodperformancefordiffer-
entreferenceanddisturbancesignalsaswellasfordifferentvaluesoftheuncertain
parameters.
16.2 DynamicModelofthe DistillationColumn
Atypicaltwo-productdistillationcolumnisshowninFig.16.1.Theobjectiveofthe
distillationcolumnistosplitthefeedF,whichisamixtureofalightandaheavy
componentwithcomposition z ,intoadistillateproductD withcompositiony ,
F D

16.2 DynamicModeloftheDistillationColumn 329
| Table16.1 Columnnomenclature |                                                   |     |     |     |
| ---------------------------- | ------------------------------------------------- | --- | --- | --- |
| Symbol                       | Description                                       |     |     |     |
| F                            | Feedrate[kmol/min]                                |     |     |     |
| zF                           | feedcomposition[molefraction]                     |     |     |     |
| qF                           | fractionofliquidinfeed                            |     |     |     |
| DandB                        | distillate(top)andbottomproductflowrate[kmol/min] |     |     |     |
yDandxB distillateandbottomproductcomposition(usuallyoflightcomponent)
[molefraction]
| L   | refluxflow[kmol/min]              |     |     |     |
| --- | --------------------------------- | --- | --- | --- |
| V   | boilupflow[kmol/min]              |     |     |     |
| N   | numberofstages(includingreboiler) |     |     |     |
=N+1
| Ntot    | totalnumberofstages(includingcondensor)              |     |     |     |
| ------- | ---------------------------------------------------- | --- | --- | --- |
| i       | stagenumber(1—bottom,NF—feedstage,NT—totalcondensor) |     |     |     |
| LiandVi | liquidandvaporflowfromstagei[kmol/min]               |     |     |     |
| xiandyi | liquidandvaporcompositionoflightcomponentonstagei    |     |     |     |
Mi liquidholduponstagei[kmol](MB—reboiler,MD—condensorholdup)
| α                    | relativevolatilitybetweenlightandheavycomponent   |                   |              |                |
| -------------------- | ------------------------------------------------- | ----------------- | ------------ | -------------- |
| τL                   | timeconstantforliquidflowdynamicsoneachstage[min] |                   |              |                |
| Table16.2 Columndata |                                                   |                   |              |                |
| N Ntot NF            | F zF                                              | qF D B L          | V yD         | xB Mi τL       |
| 40 41 21             | 1 0.5                                             | 1 0.5 0.5 2.70629 | 3.20629 0.99 | 0.01 0.5 0.063 |
whichcontainsmostofthelightcomponent,andabottomproductB withcompo-
sition z , which contains most of the heavy component. For this aim, the column
B
containsaseriesoftraysthatarelocatedalongitsheight.Theliquidinthecolumn
flowsthroughthetraysfromtoptobottom,whilethevaporinthecolumnrisesfrom
bottomtotop.Theconstantcontactbetweenthevaporandliquidleadstoincreasing
concentrationofthemore-volatilecomponentinthevapor,whilesimultaneouslyin-
creasingconcentrationofthelessvolatilecomponentintheliquid.Theoperationof
thecolumnrequiresthatsomeofthebottomproductisreboiledatarateV toensure
thecontinuityofthevaporflowandsomeofthedistillateisrefluxedtothetoptray
atarateLtoensurethecontinuityoftheliquidflow.
The notations used in the derivation of the column model are summarized in
Table16.1andthecolumndataaregiveninTable16.2.
The index i denotes the stages numbered from the bottom (i =1) to the top
(i=N )of thecolumn.Index B denotesthebottomproductand D thedistillate
tot
product.Aparticularhigh-puritydistillationcolumnwith40stages(39traysanda
reboiler)plusatotalcondensorisconsidered.

330 16 RobustControlofaDistillationColumn
Thenonlinearmodelequationsare:
1. Totalmaterialbalanceonstagei
dM i /dt=L i+1 −L i +V i−1 −V i
2. Materialbalanceforthelightcomponentoneachstagei
d(M i x i )/dt=L i+1 x i+1 +V i−1 y i−1 −L i x i −V i y i
This equation leads to the following expression for the derivative of the liquid
molefraction:
(cid:6) (cid:7)+
dx /dt= d(M x )/dt−x (dM /dt) M
i i i i i i
3. Algebraicequations
The vapor composition y is related to the liquid composition x on the same
i i
stagethroughthealgebraicvapor–liquidequilibrium
+(cid:6) (cid:7)
y =αx 1+(α−1)x
i i i
Fromtheassumptionofconstantmolarflowsandnovapordynamics,oneobtains
thefollowingexpressionforthevaporflows:
V i =V i−1
The liquidflows dependonthe liquidholdupon the stage aboveand the vapor
flowasfollows:
L i =L0 i +(M i −M0 i )/τ L +λ(V i−1 −V0 i−1 )
whereL0 [kmol/min]andM0 [kmol]arethenominalvaluesfortheliquidflow
i i
andholduponstagei andV0 isthenominalboilupflow.Ifthevaporflowinto
i
thestageeffectstheholdupthentheparameterλisdifferentfromzero.Forthe
columnunderinvestigationλ=0.
Theaboveequationsapplyatallstagesexceptinthetop(condensor),feedstage
andbottom(reboiler).
1. Forthefeedstage,i=N (itisassumedthatthefeedismixeddirectlyintothe
F
liquidatthisstage)
dM i /dt=L i+1 −L i +V i−1 −V i +F
d(M i x i )/dt=L i+1 x i+1 +V i−1 y i−1 −L i x i −V i y i +Fz F
2. Forthetotalcondensor,i=N (M =M ,L =L )
tot Ntot D Ntot T
dM i /dt=V i−1 −L i −D
d(M i x i )/dt=V i−1 −L i x i −Dx i
3. Forthereboiler,i=1(M =M ,V =V =V)
i B i B
d(M i x i )/dt=L i+1 x i+1 −V i y i −Bx i

16.2 DynamicModeloftheDistillationColumn 331
Asaresult,weobtainanonlinearmodelofthedistillationcolumnof82ndorder.
Therearetwostatespertray,onerepresentingtheliquidcompositionandtheother
representingtheliquidholdup.Themodelhasfourmanipulatedinputs(L ,V ,D
T B
andB)andthreedisturbances(F,z andq ).
F F
Inordertofindalinearmodelofthedistillationcolumnitisnecessarytohavea
steady-stateoperatingpointaroundwhichthecolumndynamicsistobelinearized.
However, the model contains two integrators, because the condensor and reboiler
levelsarenotundercontrol.Tostabilizethecolumn,wemakeuseofthesocalled
LV-configuration of the distillation column where we use D to control M and B
D
to control M . This is done by two proportionalcontrollers with both gains equal
B
to10.
ThenonlinearmodelislinearizedattheoperatingpointgiveninTable16.2(the
valuesofF,L,V,D,B,y ,x andz ).Thesesteady-statevaluescorrespondto
D B F
aninitialstatewhereallliquidcompositionsare equalto 0.5 andthe trayholdups
are also equal to 0.5 [kmol]. The steady-state vector is obtained for t =5000 min
bynumericalintegrationofthenonlinearmodelequationsoftheLV-configuration
given in the M-file cola_lv.m. The linearization is carried out by implement-
ing the M-file cola_lin, which makes use of the equations given in the file
cola_lv_lin.m.The82nd-order,linearmodelisstoredinthevariableG uand
4
hasfourinputs(thelattertwoareactuallydisturbances),
[L V F z ]
T B F
andtwooutputs,
[y x ]
D B
Before reducing the model order, the model G u is scaled in order to make all
4
inputs/disturbances and all outputs at about the same magnitude. This is done by
dividingeachvariablebyitsmaximumchange,i.e.
u=U/U ; y=Y/Y
max max
whereU,Y aretheinputandoutputofthemodelG uinoriginalunits,U ,Y
4 max max
arethecorrespondingmaximumvaluesallowed,andu, y arethescaledvariables.
Thescalingisachievedbyusingtheinputscalingmatrix
⎡ ⎤
1 0 0 0
⎢ ⎥
S i
=⎢
⎣
0
0 0
1
0
0
.2 0
0 ⎥
⎦
0 0 0 0.1
andoutputscalingmatrix
(cid:2) (cid:3)
100 0
S =
o 0 100
ThescaledmodelisthenfoundasG =S G uS .
4 o 4 i
Thefinalstageinselectingthecolumnmodelistheorderreductionofthescaled
model G . This is done by using the function reduce. As a result, we obtain a
4
sixth-ordermodelsavedinthevariableG.

| 332 | 16  | RobustControlofaDistillationColumn |
| --- | --- | ---------------------------------- |
Fig.16.2 SingularvaluesofGandG4
Allcommandsforfindingthesixth-orderlinearmodelofthedistillationcolumn
arecontainedinthefilemod_col.m.
ThefrequencyresponsesofthesingularvaluesofGarecomparedwiththesin-
gularvaluesofthe82ndorderlinearizedmodel G 4 inFig.16.2.Itisseenthatthe
behaviorofbothmodelsiscloseuntilthefrequencybecomes2rad/min.
16.3 UncertaintyModeling
The uncertainties considered in the distillation column control systems are a gain
uncertaintyof±20%andatimedelayofupto1minineachinputchannel.Thus,
theuncertaintymayberepresentedbythetransfermatrix
|     | (cid:2)   | (cid:3) |
| --- | --------- | ------- |
|     | k e − Θ1s | 0       |
= 1
| W u |     | − Θ2s |
| --- | --- | ----- |
|     | 0 k | 2 e   |
where k ∈[0.81.2]; Θ ∈[0.01.0]; i=1,2.Itisconvenienttorepresentthisun-
i i
certaintybyaninputmultiplicativeuncertainty,asshowninFig.16.3,with
|     | (cid:2) | (cid:3) |
| --- | ------- | ------- |
Δ 0
Δ= 1
0 Δ
2
where|Δ |≤1,|Δ |≤1.Theuncertaintyweightingfunction
| 1 2 | (cid:2) | (cid:3) |
| --- | ------- | ------- |
|     | W       | 0       |
W = Δ1
Δ
|     | 0   | W Δ2 |
| --- | --- | ---- |

| 16.4 Closed-LoopSystemPerformanceSpecifications |     |     |     |     |     |     |     | 333 |
| ----------------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
Fig.16.3 Distillationcolumnwithinputmultiplicativeuncertainty
isdeterminedinthefollowingway.
|     |     | =1  |     |     |     |     |     | =1  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
Denote by W ui the nominal transfer function in the ith channel for k i
andΘ =0;i=1,2.
i
AccordingtoFig.16.3wehave
|     |     | W   | =(1+W | Δ   | )W , | i=1,2 |     |     |
| --- | --- | --- | ----- | --- | ---- | ----- | --- | --- |
|     |     |     | ui    | Δi  | i ui |       |     |     |
Takingintoaccountthat|Δ |≤1itfollowsthattherelativeuncertaintyshouldsat-
i
isfy
|     |     | |W (jω)−W |     | (jω)| | (cid:18)   | (cid:18) |       |     |
| --- | --- | --------- | --- | ----- | ---------- | -------- | ----- | --- |
|     |     | ui        |     | ui    | ≤ (cid:18) | (cid:18) | i=1,2 |     |
|     |     |           |     |       | W Δi       | (jω) ,   |       |     |
|W (jω)|
ui
|       |           | = −jωΘi | =   | (cos(−ωΘ | +   | jsin(−ωΘ |       |                 |
| ----- | --------- | ------- | --- | -------- | --- | -------- | ----- | --------------- |
| where | W ui (jω) | k i e   |     | k i      | i ) |          | i )). | In this way, to |
choose the uncertainty weight W is equivalent to determining an upper bound
Δi
ofthefrequencyresponseoftherelativeuncertainty
$
|     |           |     |       | (cid:6)    |     | (cid:7) | (cid:6)  | (cid:7) |
| --- | --------- | --- | ----- | ---------- | --- | ------- | -------- | ------- |
|     | |W (jω)−W |     | (jω)| |            |     |         |          |         |
|     | ui        | ui  |       | = k cos(ωΘ |     | )−1 2+  | k sin(ωΘ | ) 2 .   |
|     |           |     |       | i          | i   |         | i        | i       |
|W (jω)|
ui
Thefrequencyresponsesoftherelativeuncertainty
|     |     |     | |W  | (jω)−W | (jω)| |     |     |     |
| --- | --- | --- | --- | ------ | ----- | --- | --- | --- |
|     |     |     |     | ui     | ui    |     |     |     |
|     |     |     |     | |W     | (jω)| |     |     |     |
ui
arecomputedbythefileunc_col.mandshowninFig.16.4.Theseresponsesare
then approximated by third-order transfer functions using the file wfit.m. As a
result,oneobtains
2.2138s3+15.9537s2+27.6702s+4.9050
|     | =    |     |     |     |     |     | i=1,2 |     |
| --- | ---- | --- | --- | --- | --- | --- | ----- | --- |
|     | W Δi |     |     |     |     |     | ,     |     |
1.0000s3+8.3412s2+21.2393s+22.6705

334 16 RobustControlofaDistillationColumn
Fig.16.4 Approximationoftheuncertaintimedelay
16.4 Closed-Loop System PerformanceSpecifications
Theaimofthedistillationcolumncontrol-systemdesignistodetermineacontroller
thatmeetsrobuststabilityandrobustperformancespecificationsfortheLVconfig-
uration. We try to satisfy these requirements by using a 1-degree-of-freedom H ∞
loop-shapingcontrolleranda2-degree-of-freedomμ-controller.Inthegivencase,
therobuststabilitymeansguaranteedclosed-loopstabilityforall0.8≤k ,k ≤1.2
1 2
and0≤Θ ,Θ ≤1min.Thetime-domainspecificationsaregivenintermsofstep-
1 2
response requirements, which must be met for all values of k , k , Θ and Θ .
1 2 1 2
Specifically,foraunitstepcommandtothefirstinputchannelat t =0,thescaled
plantoutputsy (tracking)andy (interaction)shouldsatisfy:
1 2
• y (t)≥0.9forallt≥30min;
1
• y (t)≤1.1forallt;
1
• 0.99≤y (∞)≤1.01;
1
• y (t)≤0.5forallt;
2
• −0.01≤y (∞)≤0.01.
2
Correspondingly,similarrequirementsshouldbemetforaunitstepcommandatthe
secondinputchannel.
Inaddition,thefollowingfrequency-domainspecificationshouldbemet:
• σ(K ˆ S ˆ )(jω)<316,foreach ω,where K ˆ denotesthefeedbackpartoftheun-
y y
scaledcontroller.(Hereandlatter,avariablewithahatreferstothecaseofun-

16.4 Closed-LoopSystemPerformanceSpecifications 335
Fig.16.5 Closed-loopinterconnectionstructureofthedistillationcolumnsystemwith1DOFcon-
troller
scaledplant.)Thisspecificationisincludedmainlytoavoidsaturationoftheplant
inputs.
• σ(G ˆ K ˆ )(jω)<1,forω≥150;orσ(K ˆ S ˆ )(jω)≤1,forω≥150.
y y
In the above, σ denotes the largest singular value, and S ˆ =(I +G ˆ K ˆ )<1 is the
y
ˆ
sensitivityfunctionforG.
Theblockdiagramsoftheclosed-loopsystemswith1-degree-of-freedomand2-
degree-of-freedomcontrollers,incorporatingthedesignrequirementsconsideration
represented by weights, are shown in Figs. 16.5 and 16.6, respectively. The plant
˜
G,enclosedbythedashedrectangle,consistsofthenominalscaledmodelG plus
theinputmultiplicativeuncertainty.ThecontrollerK implementsafeedbackfrom
outputsy andx andafeedforwardfromthereferencesignalr.Themeasurement
D B
of thedistillateandbottomproductscompositionis corruptedby thenoise n.The
desireddynamicsoftheclosed-loopsystemissoughtbyimplementationofasuit-
ablychosenmodelM.ThemodelM representsthedesireddynamicbehaviorofthe
closed-loopsystemfromthereferencesignaltotheoutputs.Theusageofamodelof
thedesireddynamicsallowsustotakeeasilyintoaccountthedesignspecifications.
ThetransferfunctionmatrixofthemodelM isselectedas
(cid:30) (cid:31)
1 0
M= Ts2+2ξTs+1
0 1
Ts2+2ξTs+1
The coefficients of the transfer functions (T =6,ξ =0.8) in both channels of the
modelarechosensuchastoensureanoverdampedresponsewithasettlingtimeof
about 30 min. The off-diagonal elements of the transfer matrix are set as zeros in
ordertominimizetheinteractionbetweenthechannels.

336 16 RobustControlofaDistillationColumn
Fig.16.6 Closed-loopinterconnectionstructureofthedistillationcolumnsystemwith2DOFcon-
troller
Fig.16.7 Modelfrequencyresponse

16.4 Closed-LoopSystemPerformanceSpecifications 337
ThefrequencyresponseofthemodelM isshowninFig.16.7.
Consider first the closed-loop system with 1-degree-of-freedom controller. It is
easytoshowthat
(cid:2) (cid:3) (cid:2) (cid:3)(cid:2) (cid:3)
e W (T −M) −W TW r
p = p p n
e W KS −W KSW n
u u u n
where S =(I +G ˜ K) −1 is the sensitivity function for the scaled plant, T =(I +
G ˜ K) −1G ˜ K isthecomplementarysensitivityfunctionandG ˜ =G(I+W Δ)isthe
Δ
uncertain,scaledplantmodel.
Theperformanceobjectiveistosatisfy
(cid:24)(cid:2) (cid:3)(cid:24)
(cid:24) (cid:24) (cid:24) W p W (T K − S M) − − W W p K T S W W n (cid:24) (cid:24) (cid:24) <1 (16.1)
u u n ∞
˜
foreachuncertainG.
Letthescaled,2-degree-of-freedomcontrollerbepartitionedas
(cid:4) (cid:5)
K(s)= K (s) K (s)
y r
whereK isthefeedbackpartofthecontrollerandK isthepre-filterpart.Thenit
y r
ispossibletoshowthat
(cid:2) (cid:3) (cid:2) (cid:3)(cid:2) (cid:3)
e W (SG ˜ K −M) −W TW r
p = p r p n
e u W u (I +K y G ˜ ) −1K r −W u K y SW n n
whereS=(I +G ˜ K ) −1 isthesensitivityfunctionandT =(I +G ˜ K ) −1G ˜ K is
y y y
thecomplementarysensitivityfunction.
Theperformanceobjectiveinthegivencaseistosatisfy
(cid:24)(cid:2) (cid:3)(cid:24)
(cid:24) (cid:24) (cid:24) W W ( p I (S + G ˜ K K r G ˜ − ) − M 1K ) − − W W K p T S W W n (cid:24) (cid:24) (cid:24) <1 (16.2)
u y r u y n ∞
˜
foreachuncertainG.
The performance and control action weighting functions for both type of the
controllerarechosenas
(cid:30) (cid:31) (cid:30) (cid:31)
0.55 9.5s+3 0.3 0.87 s+1 0
W = 9.5s+10−4 , W = 0.01s+1
p
0.3 0.55
9.5s+3 u
0 0.87
s+1
9.5s+10−4 0.01s+1
The implementation of the performance weighting function W aims to ensure
p
closenessofthesystemdynamicstothemodeloverthelow-frequencyrange.Note
that this function contains nonzero off-diagonal elements, which make it easier to
meetthetime-domainspecifications.Asmallconstantequalto10
−4isaddedinthe
denominatorineachchanneltomakethedesignproblemregular.
TheusageofthecontrolweightingfunctionW allowsustolimitthemagnitude
u
ofcontrolactionsoverthespecifiedfrequencyrange(ω≥150).
The magnitude plot of the inverse of the performance weighting function W
p
is shown in Fig. 16.8 and the magnitude plot of the control weighting function is
showninFig.16.9.

338 16 RobustControlofaDistillationColumn
Fig.16.8 Inverseofperformanceweightingfunction
Fig.16.9 Control-actionweightingfunction

16.5 Open-LoopandClosed-LoopSystemInterconnections 339
Fig.16.10 Noiseweightingfunction
Thenoiseshapingfilter
(cid:2) (cid:3)
10 −2 s 0
W = s+1
n 0 10 −2 s
s+1
isdeterminedaccordingtothespectralcontentsofthesensornoisesaccompanying
themeasurementofthedistillateandbottomproductcomposition.
ThemagnitudeplotofthenoiseshapingfilterisshowninFig.16.10.
Themodeltransferfunction,theperformanceandcontrolweightingfunctionsas
wellasthenoiseshapingfilterareallsetinthefilewts_col.m.
16.5 Open-Loop and Closed-LoopSystem Interconnections
Theopen-loopsysteminterconnectionsforbothtypesofcontrollerareobtainedby
theM-fileolp_col.
The internal structure of the six-input, six-output 22nd-order open-loop system
with1-degree-of-freedomcontroller,whichissavedasthevariablesys_ic_1dof,
isshowninFig.16.11.Thereferencesandthenoisesaresavedasthevariablesref
andnoise,respectively,andthecontrolsasthevariablecontrol.
Allvariableshavetwoelements(i.e.theyare2-dimensionalvectors).
The schematic diagram showing the specific input/output ordering for the vari-
ablesys_ic_1dofisgiveninFig.16.12.

340 16 RobustControlofaDistillationColumn
Fig.16.11 Open-loopinterconnectionstructureofthedistillationcolumnsystemfor1DOFcon-
troller
Fig.16.12 Schematicdiagramoftheopen-loopinterconnectionfor1DOFcontroller
Fig.16.13 Open-loopinterconnectionstructureofthedistillationcolumnsystemfor2DOFcon-
troller
Theinternalstructureofthesix-input,eight-output22nd-orderopen-loopsystem
with2-degree-of-freedomcontroller,whichissavedasthevariablesys_ic_2dof,
isshowninFig.16.13.
The schematic diagram showing the specific input/output ordering for the vari-
ablesys_ic_2dofisgiveninFig.16.14.

16.5 Open-LoopandClosed-LoopSystemInterconnections 341
Fig.16.14 Schematicdiagramoftheopen-loopinterconnectionfor2DOFcontroller
Fig.16.15 Closed-loopinterconnectionstructureofthedistillationcolumnsystemfor1DOFcon-
troller
The block-diagram used in the simulation of the closed-loop system with
1-degree-of-freedom controller is shown in Fig. 16.15. The corresponding closed-
loop interconnection is saved in the variable clp_ic. The uncertain delays are
representedbythetransferfunctionmatrix
(cid:2) (cid:3)
k del 0
W = 1 1
del 0 k del
2 2
wherek ∈[0.81.2]i=1,2anddel isasixorderPadéapproximationofthetime
i i
delaye −Θis,Θ
i
∈[0.01.0];i=1,2.
The schematic diagram showing the specific input/output ordering for the vari-
ableclp_icisshowninFig.16.16.
The block-diagram used in the simulation of the closed-loop system with
2-degree-of-freedomcontroller,isshowninFig.16.17,andtheschematicdiagram
showing the specific input/output ordering for the variable clp_ic is shown in
Fig.16.18.

342 16 RobustControlofaDistillationColumn
Fig.16.16 Schematicdiagramoftheclosed-loopinterconnectionfor1DOFcontroller
Fig.16.17 Closed-loopinterconnectionstructureofthedistillationcolumnsystemfor2DOFcon-
troller
Fig.16.18 Schematicdiagramoftheclosed-loopinterconnectionfor2DOFcontroller
16.6 ControllerDesign
Successful design of the distillation column control system may be obtained by
using the H ∞ loop-shaping design procedure (LSDP) and the μ-synthesis. Note
thatinthecaseofLSDPwedonotusetheperformancespecificationsimplemented
in the case of μ-synthesis. Instead of these specifications we use a pre-filter W
1

16.6 ControllerDesign 343
Fig.16.19 Singularvaluesoftheoriginalsystemandshapedsystem
andapost-filterW inordertoshapeappropriatelytheopen-looptransferfunction
2
W GW .
1 2
16.6.1 Loop-Shaping Design
Inthepresentcase,wechooseapre-filterwithtransferfunction
(cid:2) (cid:3)
1.71.1s+1
0
W = 10s .
1
0
1.71.1s+1
10s
Thechoiceofthegainequalto1.7isdonetoensureasufficientlysmallsteady-state
error.Largergainleadstosmallersteady-stateerrorsbutworsetransientresponse.
Thepost-filteristakensimplyasW =I .
2 2
The singular value plots of the original and shaped systems are shown in
Fig.16.19.
Thedesignof1-degree-of-freedomLSDPcontrollerisdonebyusingtheM-file
lsh_col.m,whichimplementsthefunctionncfsyn.Thecontrollerobtainedis
ofordernine.
The robust stability analysis of the closed-loop system is done by the file
mu_col.Asaresultoneobtainsthefollowingreport:

| 344       |                                          |     |     |     | 16 RobustControlofaDistillationColumn |     |     |
| --------- | ---------------------------------------- | --- | --- | --- | ------------------------------------- | --- | --- |
| Fig.16.20 | Robuststabilityforloop-shapingcontroller |     |     |     |                                       |     |     |
report =
| Uncertain          | System       |                | is robustly |       | stable to      | modeled | uncertainty. |
| ------------------ | ------------ | -------------- | ----------- | ----- | -------------- | ------- | ------------ |
| -- It              | can tolerate |                | up to       | 154%  | of the modeled |         | uncertainty. |
| -- A destabilizing |              |                | combination |       | of 154%        | of the  | modeled      |
|                    | uncertainty  |                | exists,     |       |                |         |              |
| causing            |              | an instability |             | at    | 0.534 rad/s.   |         |              |
| -- Sensitivity     |              | with           | respect     |       | to uncertain   | element | ...          |
| ’Delta_1’          |              | is 42%.        | Increasing  |       | ’Delta_1’      | by      | 25% leads    |
|                    |              |                | to          | a 11% | decrease       | in the  | margin.      |
| ’Delta_2’          |              | is 67%.        | Increasing  |       | ’Delta_2’      | by      | 25% leads    |
|                    |              |                | to          | a 17% | decrease       | in the  | margin.      |
The frequency response plot of the structured value μ with respect to the ro-
buststabilityisshowninFig.16.20.Theclosed-loopsystempreservesstabilityfor
allperturbationswithnormlessthan1.54.Asusual,therequirementsfornominal
performanceandrobustperformancearenotfulfilledwiththiscontroller.
Theclosed-loopfrequencyresponsesareobtainedbyusingthefilefrs_col.m.
The singular value plot of the unscaled closed-loop system transfer function is
shown in Fig. 16.21. Both low-frequency gains are equal to 1 that ensures zero
steady-stateerrorsinbothchannels.
In Fig. 16.22 we show the singular-value plot of the unscaled sensitivity func-
ˆ
tionS.

16.6 ControllerDesign 345
Fig.16.21 Frequencyresponseoftheclosed-loopsystemwithloop-shapingcontroller
Fig.16.22 Frequencyresponsesofthesensitivityfunction

346 16 RobustControlofaDistillationColumn
Fig.16.23 Frequencyresponsetothenoises
Thesingularvalueplotsofthetransferfunctionmatrixwithrespecttothenoises
(Fig.16.23)showthatthenoisesareattenuatedbyatleastafactorof 104 timesat
thesystemoutput.
ˆ ˆ ˆ ˆ
The singular-value plots of the transfer function matrices GK and K S are
y y
shown in Figs. 16.24 and 16.25, respectively. The maximum of the largest singu-
lar value of G ˆ K ˆ is far less than 1 for ω≥150 and the maximum of the largest
y
ˆ ˆ
singularvalueofK S islessthan200sothatthecorrespondingfrequency-domain
y
specificationismet.
In Figs. 16.26, 16.27, 16.28 and 16.29 we show the transient responses of the
scaledclosed-loopsystemobtainedbythefilemcs_col.mfordifferentvaluesof
the uncertain gain and time delay. The time-domain specification is met and the
closed-loopsystemtransientresponsehasasmallsettlingtime.
The control action in the closed-loop system for the same variations of the un-
certainparametersisshowninFigs.16.30,16.31,16.32and16.33.
16.6.2 μ-Synthesis
Let us denote by P(s) the transfer function matrix of the six-input, eight-output
open-loop system consisting of the distillation column model plus the weighting
functionsandlettheblockstructureΔ isdefinedas
%(cid:2) (cid:3)P &
Δ := Δ 0 :Δ∈C2×2,Δ ∈C4×4
P 0 Δ F
F

16.6 ControllerDesign 347
ˆ ˆ
Fig.16.24 Singular-valueplotofGKy
ˆ ˆ
Fig.16.25 Singular-valueplotofKyS

348 16 RobustControlofaDistillationColumn
Fig.16.26 Perturbedtransientresponsey11forloop-shapingcontroller
Fig.16.27 Perturbedtransientresponsey12forloop-shapingcontroller

16.6 ControllerDesign 349
Fig.16.28 Perturbedtransientresponsey21forloop-shapingcontroller
Fig.16.29 Perturbedtransientresponsey22forloop-shapingcontroller

350 16 RobustControlofaDistillationColumn
Fig.16.30 Perturbedcontrolactionu11forloop-shapingcontroller
Fig.16.31 Perturbedcontrolactionu12forloop-shapingcontroller

16.6 ControllerDesign 351
Fig.16.32 Perturbedcontrolactionu21forloop-shapingcontroller
Fig.16.33 Perturbedcontrolactionu22forloop-shapingcontroller

| 352       |              |     |           |     |                 | 16 RobustControlofaDistillationColumn |     |                 |     |
| --------- | ------------ | --- | --------- | --- | --------------- | ------------------------------------- | --- | --------------- | --- |
| Table16.3 | Resultsofthe |     |           |     |                 |                                       |     |                 |     |
|           |              |     | Iteration |     | Controllerorder |                                       |     | Maximumvalueofμ |     |
μ-synthesis
|     |     |     | 1   |     | 22  |     |     | 1.091 |     |
| --- | --- | --- | --- | --- | --- | --- | --- | ----- | --- |
|     |     |     | 2   |     | 28  |     |     | 0.991 |     |
|     |     |     | 3   |     | 28  |     |     | 0.978 |     |
ThefirstblockofthismatrixcorrespondstotheuncertaintyblockΔ,usedinmod-
elingtheuncertaintyofthedistillationcolumn.ThesecondblockΔ F isafictitious
uncertainty 4×4 block, introduced to include the performance objectives in the
framework of the μ-approach.The inputsto this block are the weightederror sig-
| nalse | ande | ,theoutputsbeingtheexogenousinputsr |     |     |     |     | andn. |     |     |
| ----- | ---- | ----------------------------------- | --- | --- | --- | --- | ----- | --- | --- |
| p     | u    |                                     |     |     |     |     |       |     |     |
To meet the design objectives a 2-degree-of-freedom stabilizing controller
| K(s)=[K |     | (s)] |       |          |      |          |                | ω∈[0,∞], |     |
| ------- | --- | ---- | ----- | -------- | ---- | -------- | -------------- | -------- | --- |
|         | (s) | K    | is to | be found | such | that, at | each frequency |          | the |
y r
structuredsingularvaluesatisfiesthecondition
|     |     |     |     | (cid:4) |           | (cid:5) |     |     |     |
| --- | --- | --- | --- | ------- | --------- | ------- | --- | --- | --- |
|     |     |     |     | μ F     | (P,K)(jω) |         | <1. |     |     |
ΔP L
Thefulfillmentofthisconditionguaranteesrobustperformanceoftheclosed-loop
system,i.e.,
|     |     | (cid:24)(cid:2) |      |       |     |       | (cid:3)(cid:24) |             |        |
| --- | --- | --------------- | ---- | ----- | --- | ----- | --------------- | ----------- | ------ |
|     |     | (cid:24)        |      | ˜     |     |       |                 | (cid:24)    |        |
|     |     |                 | W (S | G K − | M ) | − W T | W               |             |        |
|     |     | (cid:24)        | p    | r     |     | p     | n               | (cid:24)    |        |
|     |     | (cid:24)        | +    | ˜     | − − |       |                 | (cid:24) <1 | (16.3) |
|     |     | W               | ( I  | K G ) | 1K  | W K   | S W             |             |        |
|     |     |                 | u    | y     | r   | u     | y n             | ∞           |        |
Theμ-synthesisisdonebyusingtheM-filems_col.m,whichimplementsthe
functiondkitopt.
| TheprogressoftheD–K |     |     |     | iterationisshowninTable16.3. |     |     |     |     |     |
| ------------------- | --- | --- | --- | ---------------------------- | --- | --- | --- | --- | --- |
InthegivencaseanappropriatecontrollerisobtainedafterthethirdD–K itera-
tion.Thecontrollerisstableanditsorderisequalto28.
ItcanbeseenfromTable16.3thatafterthethirditerationthemaximumvalueof
μisequalto0.978.
Theμ-analysisoftheclosed-loopsystemisdonebythefilemu_col.According
to the reports, given below, the system achieve robust stability and robust perfor-
mance.
report =
| Uncertain      | System        |                | is robustly |            | stable       | to        | modeled | uncertainty. |     |
| -------------- | ------------- | -------------- | ----------- | ---------- | ------------ | --------- | ------- | ------------ | --- |
| -- It          | can           | tolerate       | up          | to         | 145% of      | the       | modeled | uncertainty. |     |
| -- A           | destabilizing |                | combination |            | of           | 145%      | of      | the modeled  |     |
|                | uncertainty   |                | exists,     |            |              |           |         |              |     |
| causing        |               | an instability |             |            | at 0.614     | rad/s.    |         |              |     |
| -- Sensitivity |               |                | with        | respect    | to uncertain |           | element | ...          |     |
| ’Delta_1’      |               | is             | 54%.        | Increasing |              | ’Delta_1’ |         | by 25% leads |     |
|                | to            | a 14%          | decrease    |            | in the       | margin.   |         |              |     |
| ’Delta_2’      |               | is             | 68%.        | Increasing |              | ’Delta_2’ |         | by 25% leads |     |
|                | to            | a 17%          | decrease    |            | in the       | margin.   |         |              |     |

| 16.6 ControllerDesign |                                |                 |     |          |             |     | 353    |
| --------------------- | ------------------------------ | --------------- | --- | -------- | ----------- | --- | ------ |
| Fig.16.34             | Robuststabilityforμ-controller |                 |     |          |             |     |        |
| report                | =                              |                 |     |          |             |     |        |
| Uncertain             |                                | System achieves |     | a robust | performance |     | margin |
of 1.023.
| -- A           | model | uncertainty    | exists     |        | of size   | 102%    | resulting |
| -------------- | ----- | -------------- | ---------- | ------ | --------- | ------- | --------- |
|                | in    | a performance  | margin     |        |           |         |           |
| of             | 0.978 | at 0.0433      | rad/s.     |        |           |         |           |
| -- Sensitivity |       | with           | respect    | to     | uncertain | element | ...       |
| ’Delta_1’      |       | is 52%.        | Increasing |        | ’Delta_1’ | by      | 25% leads |
|                | to    | a 13% decrease |            | in the | margin.   |         |           |
| ’Delta_2’      |       | is 46%.        | Increasing |        | ’Delta_2’ | by      | 25% leads |
|                | to    | a 12% decrease |            | in the | margin.   |         |           |
The frequency-response plot of the structured singular value for the case of ro-
buststabilityisshowninFig.16.34.Thestabilityofthesystemispreservedunder
| perturbationsthatsatisfy(cid:5)Δ(cid:5) |     |     | ∞<1.45. |     |     |     |     |
| --------------------------------------- | --- | --- | ------- | --- | --- | --- | --- |
Thefrequencyresponseofμforthecaseofrobustperformanceanalysisisshown
inFig.16.35.Theclosed-loopsystemachievesrobustperformance,themaximum
valueofμbeingequalto0.978.
Theunscaledclosed-loopsystemsingular-valueplotisshowninFig.16.36.The
closed-loopbandwidthisabout0.1rad/min.
In Fig. 16.37 we show the singular-value plot of the unscaled sensitivity func-
ˆ
tionS.

354 16 RobustControlofaDistillationColumn
Fig.16.35 Robustperformanceforμ-controller
Fig.16.36 Closed-loopsingular-valueplots

16.6 ControllerDesign 355
Fig.16.37 Frequencyresponsesofthesensitivityfunction
ThefrequencyresponseswithrespecttothenoiseareshowninFig.16.38.Itis
seenfromthefigurethatthenoisesinmeasuringthedistillateandbottom-product
compositionhaveaverysmalleffectonthesystemoutput.
Thesingular-valueplotsoftheunscaledμ-controllerareshowninFig.16.39.
ˆ ˆ ˆ ˆ
The singular-valueplots of GK and K S are shownin Figs.16.40and16.41,
y y
ˆ ˆ
respectively.Themaximumofthelargestsingularvalueof GK islessthan1for
y
ω≥150 and the maximum of the largest singular value of K ˆ S ˆ is less than 300,
y
thusthefrequency-domainspecificationismet.
The perturbed transient responses of the scaled closed-loop system with a μ-
controller are shown in Figs. 16.42, 16.43, 16.44 and 16.45. The responses to the
corresponding references have no overshoots and the interaction of channels is
weakerthaninthecaseofusingloop-shapingcontroller.
Thecontrolactioninthecaseofperturbedsystemwiththeμ-controllerisshown
inFigs.16.46,16.47,16.48and16.49.
Consider now the reduction of controller order. For this aim we implement the
M-file red_col.m. Using the function reduce the controller order is reduced
to12.
InFig.16.50wecomparethefrequencyresponsesofthemaximumsingularval-
uesofthescaledfull-orderandreduced-ordercontrollers.Thefrequencyresponses
of both full-order and reduced-order controllers coincide up to 23 rad/min, which
ismuchmorethantheclosed-loopbandwidthofthesystem.Thisiswhythetran-

356 16 RobustControlofaDistillationColumn
Fig.16.38 Frequencyresponseswithrespecttonoises
Fig.16.39 Singularvaluesofthecontroller

16.6 ControllerDesign 357
ˆ ˆ
Fig.16.40 FrequencyresponsesofGKy
ˆ ˆ
Fig.16.41 FrequencyresponsesofKyS

358 16 RobustControlofaDistillationColumn
Fig.16.42 Perturbedtransientresponsey11forμ-controller
Fig.16.43 Perturbedtransientresponsey12forμ-controller

16.6 ControllerDesign 359
Fig.16.44 Perturbedtransientresponsey21forμ-controller
Fig.16.45 Perturbedtransientresponsey22forμ-controller

360 16 RobustControlofaDistillationColumn
Fig.16.46 Perturbedcontrolactionu11forμ-controller
Fig.16.47 Perturbedcontrolactionu12forμ-controller

16.6 ControllerDesign 361
Fig.16.48 Perturbedcontrolactionu21forμ-controller
Fig.16.49 Perturbedcontrolactionu22forμ-controller

362 16 RobustControlofaDistillationColumn
Fig.16.50 Frequencyresponsesofthefull-orderandreduced-ordercontrollers
sient responses of the closed-loop system with full-order and with reduced-order
controllersarepracticallyundistinguishable.
16.7 NonlinearSystem Simulation
The μ-controllerdesignedisinvestigatedbysimulationofthecorrespondingnon-
linear closed-loop system. The simulation is carried out by the Simulink® model
nls_col.mdl,whichimplementsthenonlinearplantmodelgiveninSect.16.2.
TosimulatethenonlinearplantweusetheM-filescolamodandcolasbykind
permissionoftheauthor,SigurdSkogestad.
The Simulink® model of the distillation column control system shown in
Fig. 16.51 allows us to carry out a number of simulations for different set points
anddisturbances.Notethattheinputstothecontrollerareformedasdifferencesbe-
tweenthevaluesofthecorrespondingvariablesandtheirnominal(steady-state)val-
uesusedinthelinearization.Incontrast,thecontrolleroutputsareaddedtothecor-
respondingnominalinputsinordertoobtainthefullinputstothenonlinearmodel
ofthecolumn.
Before simulation of the system it is necessary to set the model parameters by
usingtheM-fileinit_col.m.Also,thecontrollerisrescaledsoastoimplement
theunscaledinput/outputvariables.
Thenonlinearsystemsimulationisdoneforthefollowingreferenceanddistur-
bancesignals.Att=10minthefeedrateF increasesfrom1to1.2,att=100min

16.7 NonlinearSystemSimulation 363
metsysraenilnonehtfoledomnoitalumiS
15.61.giF

364 16 RobustControlofaDistillationColumn
Fig.16.52 Transientresponseofthenonlinearsystem—yD
thefeedcompositionz increasesfrom0.5to0.6andatt =200minthesetpoint
F
iny increasesfrom0.99to0.995.
D
The time response of the distillate y for the case of the reduced-order μ-
D
controller is given in Fig. 16.52. It is seen from the figure that the disturbances
areattenuatedwellandthedesiredsetpointisachievedexactly.
Thetimeresponseofthebottom-productcompositionx forthesamecontroller
B
isgiveninFig.16.53.
Thesimulationresultsshowthattherobustdesignmethodisappropriatelycho-
senandconfirmsthevalidityoftheuncertainmodelused.
16.8 Conclusions
Theresultsfromtheanalysisanddesignofadistillationcolumncontrolsystemmay
besummarizedasfollows.
• Itispossibletouseasufficientlylow-orderlinearizedmodelofthegivennonlin-
earplant,sothatthedesignedlinearcontrollersallowtobeachievedsatisfactory
dynamicsofthenonlinearclosed-loopsystem.Thelinearizedmodelisscaledin
ordertoavoidverysmallorverylargesignals.
• Two controllers are designed—one by using a 1-degree-of-freedom H ∞ loop-
shapingdesignmethodandtheotherbyusinga2-degree-of-freedomμ-synthesis
method.Bothcontrollerssatisfythetime-domainandfrequency-domainspecifi-
cations and ensure robust stability of the corresponding closed-loop systems. It

16.9 NotesandReferences 365
Fig.16.53 Transientresponseofthenonlinearsystem—xB
isimpressivehowthelow-order,easilydesignedloop-shapingcontrollerallows
us to obtain practically the same characteristics of the closed-loop systems as
theμ-controller,whilethelatterrequiresmuchmoreexperimentsfortuningthe
weightingfunctions.
• The nonlinear system simulation results confirm the ability of the controller to
achievedisturbanceattenuationandgoodresponsestoreferencesignals.Thesim-
ulationconfirmsthevalidityoftheuncertainmodelused.
16.9 Notesand References
The distillation column control problem presented in this chapter was introduced
byLimebeer[97]asabenchmarkproblematthe1991ConferenceonDecisionand
Control. In [97] the uncertainty is defined in terms of parametric gain and delay
uncertaintyandthecontrolobjectivesareamixtureoftime-domainandfrequency-
domain specifications. The problem originates from Skogestad et al. [156] where
a simple model of a high-purity distillation column was used and uncertainty and
performancespecificationsweregivenasfrequency-dependentweightingfunctions.
A tutorial introduction to the dynamics of the distillation column is presented in
[154].
A design of a 2-degree-of-freedom loop-shaping controller for the distillation
column is presented in [62] where an eighth-order model of the column is used.
A2-degree-of-freedomcontrollerforthedistillationcolumnsystemisproposedin

366 16 RobustControlofaDistillationColumn
[106] with a reference model and using μ-synthesis. In that paper, one may find
a selection procedure for the weighting functions described in detail. Our design
differsfromthedesignin[106]inseveralrespects.First,insteadofasecond-order
model with time delay we use a sixth-order model that is justified by the results
fromnonlinearsystemsimulation.Second,weusemodifiedweightingfunctionsin
orderto obtainbetterresults. Inparticular,weuse a performanceweightingtrans-
ferfunctionmatrixwithnonzerooff-diagonalelementsthatmeetsthetime-domain
specificationsmuchbetter.Also,thecontrolweightingfunctionsaretakenasfirst-
order,low-passfilters.
Various design methods have been reported, in addition to the above, to tackle
thisdistillationcolumnproblem[126,139,155,160,178].In[178],thedesignprob-
lem is formulated as a mixed optimization problem. It is well known that control-
system design problems can be formulated as constrained optimization problems.
Design specifications in both the time and frequency domains as well as stability
canbenaturallyformulatedasconstraints.Numericaloptimizationapproachescan
beuseddirectlyandasolutionobtained,ifthereisone,willcharacterizeanaccept-
abledesign.However,theoptimizationproblemssoderivedareusuallyverycom-
plicatedwithmanyunknowns,manynonlinearities,manyconstraints,andinmost
cases,theyaremultiobjectivewithseveralconflictingdesignaimsthatneedtobesi-
multaneouslyachieved.Furthermore,adirectparameterizationofthecontrollerwill
increasethecomplexityoftheoptimizationproblem.In[178],theH ∞loop-shaping
designprocedureisfollowed.Insteadofdirectparameterizationofcontrollers,the
pre-andpost-weightingfunctionsusedtoshapetheopen-loop,augmentedsystem
arechosenasdesign(optimization)parameters.Theloworderandsimplestructure
ofsuchweightingfunctionsmakethenumericaloptimizationmuchmoreefficient.
TheH ∞ normrequirementisalsoincludedinthecost/constraintset.Thestability
oftheclosed-loopsystemisnaturallymetbysuchdesignedcontrollers.Satisfactory
designsarereportedinthatpaper.Reference[160]furtherextendstheoptimization
approach in [178] by using a Genetic Algorithm to choose the weighting function
parameters.

Chapter 17
Robust Control of a Flexible-Link Manipulator
Inthischapterwediscusstherobustcontrolsystemdesignofaflexible-linkmanip-
ulatorthatmovesinthehorizontalplane.
Lightweight manipulators possess many advantages over the traditional bulky
manipulators.Themostimportantbenefitsincludehighpayload-to-armweightra-
tio, faster motion, safer operation, improved mobility, low cost, longer reach and
betterenergyefficiency,etc.However,thereductionofweightleadstotheincrease
of the link elasticity that significantly complicates the control of the manipulator.
Thedifficultyincontroliscausedbythefactthatthelinkmodelisadistributedpa-
rameterplant.Inthiscase,severalelasticmodesarerequiredtoachievesufficiently
highaccuracy.Also,theplanthasseveraluncertainparameters(payloadmass,hub
andstructuraldampingfactors, etc.)thatinfluencesignificantlythesystemperfor-
mance. The inherent, non-minimum phase behavior of the flexible manipulator is
another obstacle to achieving simultaneously a high-level performance as well as
goodrobustness.
Theaimofthepresentcasestudyistodesignacontrolsystemforasingle-link
flexible manipulator. A two-mode dynamic model of the manipulator is first ob-
tained by using the Lagrangian-assumed modes method. This is followed by the
modelingofuncertaintiesinvolvedinthemanipulator.Theuncertaintiesincludethe
realparametricuncertaintiesinthepayloadmassaswellasinthehubandstructural
dampingfactors.Theseparametersarethebasicuncertaintysourceinthedynamic
behaviorsoftheflexible-linkmanipulators.Theμ-synthesismethodisthenapplied
to design a robust, noncollocated controller on the feedback signals of joint angle
andtipacceleration.Inthedesign,inordertoobtainafeasiblesolution,asimplified
uncertaintydescriptionisconsideredintheD–K iterations.Appropriateweighting
functionsarechoseninthedesigntoensurerobuststabilityandrobustperformance.
Itisshowninthischapterthatgoodrobustperformancehasbeenachievedinthede-
sign.Theclosed-loopsystemexhibitsexcellenttip-motionperformanceforawide
range of payload mass and the system efficiently suppresses the elastic vibrations
during the fast motion of the manipulator tip. For the sake of implementation and
reliabilityinpractice,areduced-ordercontrollerisfoundthatmaintainstherobust
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 367
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_17,©Springer-VerlagLondon2013

368 17 RobustControlofaFlexible-LinkManipulator
Fig.17.1 Schematicdiagram
oftheflexible-link
manipulator
stabilityandrobustperformanceoftheclosed-loopsystem.Finally,theadvantages
oftheμ-controlleroveraconventional,collocatedPDcontrolleraredemonstrated.
17.1 DynamicModelofthe FlexibleManipulator
Figure17.1showstheschematicmodelusedtoderivetheequationsofmotionfor
theflexible-linkmanipulator.Themanipulatormovesinthehorizontalplane.Frame
x –O –y isthefixed-baseframe.Framex–O–yisthelocalframerotatingwiththe
0 0 0
hub. The x-axis coincides with the undeformed longitudinal axis of the link. The
rotatinginertiaoftheservomotor,thegearbox,andtheclampinghubaremodeled
asasinglehubinertiaJ .Thedistancebetweenthehubcenterandtherootofthe
h
link is denoted by R. The flexible link is assumed to be a homogeneous rod with
a constant cross-sectional area. L is the length of the link, m is the mass per unit
lengthofthelink,I isthelinkcross-sectionalmomentofinertiaandE isYoung’s
modulusofelasticityforthematerialofthelink.Thepayloadismodeledasapoint
mass m . The variables τ(t) and θ(t) are the driving torque and the joint angle,
L
respectively.Theelasticdeflectionofapointlocatedatadistancex fromO along
thelinkisdenotedbyw(x,t).Itisassumedthattheelasticdeflectionsofthelinklie
inthehorizontalplane,andareperpendiculartothex-axisandsmallinmagnitude
comparedtothelinklength.
Themotionequationsoftheflexiblemanipulatoraretobederivedbyusingthe
Lagrangian approach combined with the assumed-modes method [25]. The flexi-
ble link is modeled as an Euler–Bernoulli beam. The free vibration of the link is
describedbythepartialdifferentialequation[116]
∂4w(x,t) ∂2w(x,t)
EI +m =0
∂x4 ∂t2
withboundaryconditions
∂w(0,t)
w(0,t)=0, =0
∂x

| 17.1 DynamicModeloftheFlexibleManipulator |     |     |     |     |     |     |     | 369 |
| ----------------------------------------- | --- | --- | --- | --- | --- | --- | --- | --- |
∂2w(L,t)
=0
∂x2
|     |     |     | ∂3w(L,t) |     | m ∂2w(L,t) |     |     |     |
| --- | --- | --- | -------- | --- | ---------- | --- | --- | --- |
|     |     |     |          | −   | L          | =0  |     |     |
|     |     |     |          | ∂x3 | EI         | ∂t2 |     |     |
Accordingtotheassumed-modesmethodtheelasticdeflectioncanbeexpressed
as
(cid:14)n
w(x,t)=
|     |     |     |     |     | ϕ i (x)η | i (t) |     | (17.1) |
| --- | --- | --- | --- | --- | -------- | ----- | --- | ------ |
i=1
whereη (t)isthegeneralizedcoordinateoftheithmode,ϕ (x)isthespaceeigen-
|     | i   |     |     |     |     |     | i   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
function of the ith mode, and n is the number of the modes that describe the link
=1,...,n,
deflection. The mode angular frequencies ω i , i of the flexible link are
givenby
,
EI
|     |     |     |     | ω =β2 |     |     |     | (17.2) |
| --- | --- | --- | --- | ----- | --- | --- | --- | ------ |
i i
m
,i=1,...,n,arethefirstnpositiverootsofthetranscendentalequation
whereβ i
|                    |     |     |     | (cid:4)                              |     |     |     | (cid:5) |
| ------------------ | --- | --- | --- | ------------------------------------ | --- | --- | --- | ------- |
|                    |     |     | m   | L                                    |     |     |     |         |
| 1+cosh(βL)cos(βL)+ |     |     |     | (βL) sinh(βL)cos(βL)−cosh(βL)sin(βL) |     |     |     | =0      |
mL
(17.3)
Theshapefunctionsϕ (x),i=1,...,n,satisfytheorthogonalitycondition
i
(cid:17)
L
|     |     | m   | ϕ (x)ϕ | (x)dx+m | ϕ (L)ϕ | (L)=0, | i(cid:3)=j |     |
| --- | --- | --- | ------ | ------- | ------ | ------ | ---------- | --- |
|     |     |     | i      | j       | L i    | j      |            |     |
0
andcanbewrittenintheform
%
|     |     |       | (cid:4)  |          |      | (cid:5) |     |     |
| --- | --- | ----- | -------- | -------- | ---- | ------- | --- | --- |
|     |     | (x)=λ |          | x)−cos(β |      |         |     |     |
|     | ϕ i |       | i cosh(β | i        | i x) |         |     |     |
&
|     |     |     |        | L)+cos(β |      | (cid:4)         | (cid:5) |        |
| --- | --- | --- | ------ | -------- | ---- | --------------- | ------- | ------ |
|     |     |     | cosh(β | i        | i L) |                 |         |        |
|     |     |     | −      |          |      | sinh(β x)−sin(β | x)      | (17.4) |
|     |     |     | sinh(β | L)+sin(β | L)   | i               | i       |        |
|     |     |     |        | i        | i    |                 |         |        |
Anormalizationoftheshapefunctionsconvenientfortheuncertaintymodelingis
accomplishedbydeterminingthecoefficientsλ ,i=1,...,n,in(17.4)onthebasis
i
oftherelation
(cid:17)
L
|     |     |     | m   | ϕ2(x)dx+m |     | ϕ2(L)=1 |     |     |
| --- | --- | --- | --- | --------- | --- | ------- | --- | --- |
|     |     |     |     | i         | L   | i       |     |     |
0
,i=1,...,n,areusedasgener-
| Thejointangleθ |     |     | andthedeflectionvariablesη |     |     |     |     |     |
| -------------- | --- | --- | -------------------------- | --- | --- | --- | --- | --- |
i
alizedcoordinatesinthederivationoftheequationofmotion.Asaresultofapplying
the Lagrangian procedure, the following nonlinear dynamic model of the flexible
manipulatorisobtained:
|     |     | (cid:2) |      | (cid:3)(cid:2) (cid:3) | (cid:2) | (cid:3)(cid:2) (cid:3) |     |     |
| --- | --- | ------- | ---- | ---------------------- | ------- | ---------------------- | --- | --- |
|     |     |         |      | ¨                      |         | ˙                      |     |     |
|     |     | m       | (η)  | mT θ                   | d       | 0T θ                   |     |     |
|     |     |         | r    | rf                     | + r     | n                      |     |     |
|     |     |         |      | η¨                     | 0       | D η˙                   |     |     |
|     |     |         | m rf | I n                    | n       | f                      |     |     |

| 370 |     |         |     | 17                     | RobustControlofaFlexible-LinkManipulator |         |                 |     |
| --- | --- | ------- | --- | ---------------------- | ---------------------------------------- | ------- | --------------- | --- |
|     |     | (cid:2) |     | (cid:3)(cid:2) (cid:3) | (cid:2)                                  | (cid:3) | (cid:2) (cid:3) |     |
˙
|     |     |     | 0 0T    | θ   | h (θ ,η,η˙) |     | 1   |        |
| --- | --- | --- | ------- | --- | ----------- | --- | --- | ------ |
|     |     | +   | n       |     | + r         |     | =   |        |
|     |     |     |         |     | ˙           |     | τ   | (17.5) |
|     |     |     | 0 n C f | η   | h f (θ,η)   |     | 0 n |        |
where
|     | η=[η |       | ]T  |     |     |     |     |     |
| --- | ---- | ----- | --- | --- | --- | --- | --- | --- |
|     |      | 1 ... | η n |     |     |     |     |     |
(cid:14)n
|     | m (η)=a | +   | η2  |     |     |     |     |     |
| --- | ------- | --- | --- | --- | --- | --- | --- | --- |
|     | r       | 0   | i   |     |     |     |     |     |
i=1
|     |      | 1     | (cid:4)   |     | (cid:5) |        |     |     |
| --- | ---- | ----- | --------- | --- | ------- | ------ | --- | --- |
|     | =J   | +     | (L+R)3−R3 |     | +m      | (L+R)2 |     |     |
|     | a    | m     |           |     |         |        |     |     |
|     | 0    | a 3   |           |     | L       |        |     |     |
|     | =[a  |       | ]T        |     |         |        |     |     |
|     | m rf | 1 ... | a n       |     |         |        |     |     |
(cid:17)
L
|     | =m  | (x+R)ϕ |     | (x)dx+m | (L+R)ϕ |     | i=1,...,n |        |
| --- | --- | ------ | --- | ------- | ------ | --- | --------- | ------ |
|     | a i |        | i   |         | L      |     | i (L),    | (17.6) |
0
|     |       | (cid:6)   |     | (cid:7) |     |     |     |     |
| --- | ----- | --------- | --- | ------- | --- | --- | --- | --- |
|     | =diag | ω2,...,ω2 |     |         |     |     |     |     |
C f
|     |           | 1      | n   |     |     |     |     |     |
| --- | --------- | ------ | --- | --- | --- | --- | --- | --- |
|     | D =diag(d | ,...,d | )   |     |     |     |     |     |
|     | f         | 1      | n   |     |     |     |     |     |
(cid:14)n
|        | ˙ ,η,η˙)= | ˙ η˙ |     |     |     |     |     |     |
| ------ | --------- | ---- | --- | --- | --- | --- | --- | --- |
| h r (θ |           | 2θ i | η i |     |     |     |     |     |
i=1
|     |         | (cid:4) |     |     | (cid:5) |     |     |     |
| --- | ------- | ------- | --- | --- | ------- | --- | --- | --- |
|     | ˙       | ˙2η     |     | ˙2η | T       |     |     |     |
| h   | (θ ,η)= | −θ      | ... | −θ  |         |     |     |     |
| f   |         | 1       |     | n   |         |     |     |     |
I denotes the n × n identity matrix, 0 is the n-dimensional null vector, and
| n   |     |     |     |     | n   |     |     |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
d ,d ,...,d aredampingcoefficients.Thetermsd θ ˙ andD η˙havebeenincluded
| r 1 | n   |     |     |     |     | r   | f   |     |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
toaccountfortheviscousfrictionatthehubandforthestructuraldampingofthe
flexiblelink,respectively.
Theangle
w(L,t)
|     |     |     | α=θ+arctan |     |     |     |     | (17.7) |
| --- | --- | --- | ---------- | --- | --- | --- | --- | ------ |
L+R
ischosenasthecoordinatethatdeterminesthepositionofthemanipulatortip.
Thefollowingnumericalvaluesofthemanipulatorparametersareused:L=1m,
R =0.4 m, J =0.1 kgm2, m=0.54 kg/m, flexural rigidity of the flexible link
h
EI =18.4 Nm2. The values of m and EI correspond to an aluminum link with
E=6.9×1010Nm2,densityρ=2700kg/m3,andarectangularcross-sectionwith
| dimensionss | =0.05mands |     | =0.004m,s |     | beinginthemotionplane. |     |     |     |
| ----------- | ---------- | --- | --------- | --- | ---------------------- | --- | --- | --- |
|             | 1          |     | 2         |     | 2                      |     |     |     |
Itisassumedthatinperformingagivenmotionthepayloadmasshasaconstant
butunknownvalueintherangefrom0.15kgto0.35kg.
The first two natural frequencies of the flexible link, calculated for the average
valueofthepayloadaccordingto(17.2)and(17.3),are ω =12.1rad/s and ω =
|     |     |     |     |     |     |     | 1   | 2   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
=302.5rad/sandso
99.2rad/s.Sincetherestnaturalfrequenciesareverylarge(ω
3
on),atwo-modemodeloftheflexiblemanipulatorisusedinthecontrollerdesign.
Usually,thefrictioncoefficientscannotbedeterminedexactlyandalsochanges
in their values are possible with the time. It is assumed that the coefficient of the

17.2 ALinearModeloftheUncertainSystem 371
friction at the hub has a nominal value d =0.15 kgm2/s and a relative uncer-
r
tainty 20 %, and the coefficients of the structural damping of the first two gener-
alized coordinates of the flexible link have nominal values d =0.4 kgm2/s and
1
d
2
=10kgm2/sandarelativeuncertainty40%.(cid:26)
Afterneglectingin(17.5)thenonlinearterms n η2,h (θ ˙ ,η,η˙),andh (θ ˙ ,η),
i=1 i r f
whose effect is relatively small, and after setting arctan(z) = z in (17.7), since
w(L,t)(cid:8)L,oneobtainsalinearmodelofthemanipulator.Thetransferfunctions
ofthemanipulatorwithinputthedrivingtorqueτ andoutputsthejointangleθ and
the coordinate angle α, determined for n=2, m =0.25 kg, d =0.12 kgm2/s,
L r
d =0.24kgm2/sandd =6kgm2/s,maybewritten,respectively,intheform
1 2
9.793(s2+0.24s+145.8)(s2+6s+9839)
W =
θτ s(s+0.2095)(s2+2.067s+741.9)(s2+6.799s+10850)
and
0.1239(s−172.1)(s−66.2)(s+173.1)(s+57.5)
W =
ατ s(s+0.2095)(s2+2.067s+741.9)(s2+6.799s+10850)
ThetransferfunctionW haspositivezerosandhencethemanipulator,consid-
ατ
ered with the tip position as output, represents a non-minimum phase plant. It is
knownthattoensurehighperformanceforsuchplantsisadifficultproblem.
ThesecondorderpolynomialsinthetransferfunctionsW andW havevery
θτ ατ
smalldampingfactors (between 0.01 and 0.04),whichcausesintensivevibrations
of the flexible link when performing fast motions. The undamped frequencies of
thenumeratorpolynomialofW areequaltothenaturalfrequenciesω andω of
θτ 1 2
theflexiblelink.Thenonzeronaturalfrequenciesofthemanipulator(includingthe
flexiblelinkandthedrivingpart)aredeterminedfromthesecondorderpolynomial
inthedenominatorsofthetransferfunctionsandforthegivennumericalvaluesof
theparametersareequalto27.2rad/sand104.2rad/s.
To illustrate the effect of uncertainty, in Figs. 17.2 and 17.3 we show the Bode
plotsoftheflexiblemanipulatorwithinputthedrivingtorqueτ andoutputsthejoint
angle θ and the coordinate angle α, respectively, determined for several values of
thepayloadmassintheintervalfrom0.15kgto0.35kg.
17.2 ALinearModeloftheUncertainSystem
Inthissectionwefirstconsiderhowtomodeltheuncertaintiesoftheflexible-link
manipulatorandthendevelopalineardynamicmodeloftheuncertainsystem.As
mentionedearlier,theuncertaintiesconsideredarerelatedtothepayloadmass,hub
damping factors and the damping levels of the first two modes. It is important to
notethattheseparametersarethebasicsourceofuncertaintydynamicbehaviorof
flexible-linkmanipulators.
Theplantinputisthedrivingtorqueτ.Thecontrolledvariableisthetipposition
αandthemeasuredvariablesarethejointangleθ andthetipaccelerationα¨.

372 17 RobustControlofaFlexible-LinkManipulator
Fig.17.2 Bodeplotoftheflexible-linkmanipulatorwithinputτ andoutputΘ
Fig.17.3 Bodeplotoftheflexible-linkmanipulatorwithinputτ andoutputα

| 17.2 ALinearModeloftheUncertainSystem |     |     |     |     |     | 373 |
| ------------------------------------- | --- | --- | --- | --- | --- | --- |
Thebuildingoftheuncertaintymodelisdoneonthebasisofthelinearmodelof
theflexiblemanipulator,obtainedafterneglectingthenonlineartermsin(17.5)and
aftersettingarctan(z)=zin(17.7).Inthiswayoneobtainstheequations
|     | ¨+d   | ˙+a   | η¨ +a  | η¨ =τ |       |        |
| --- | ----- | ----- | ------ | ----- | ----- | ------ |
|     | a θ   | θ     |        |       |       |        |
|     | 0     | r     | 1 1    | 2 2   |       |        |
|     | η¨ +d | η˙ +c | +a     | ¨=0,  | i=1,2 |        |
|     | i     | i i   | i η i  | i θ   |       |        |
|     | α=θ+b |       | η +b η |       |       | (17.8) |
|     |       | 1     | 1 2    | 2     |       |        |
¨+b
|     | α¨ =θ |         | η¨ +b η¨ |         |       |     |
| --- | ----- | ------- | -------- | ------- | ----- | --- |
|     |       | 1       | 1 2      | 2       |       |     |
|     |       | =(L+R)b |          | +(L+R)b |       |     |
|     | w L   |         | 1 η 1    |         | 2 η 2 |     |
wherethefollowingnotationisused:
=w(L,t)
w L
ϕ (L)
|     |     | =   | i   | i=1,2 |     |     |
| --- | --- | --- | --- | ----- | --- | --- |
|     |     | b i |     | ,     |     |     |
L+R
Inthegivencasethecoefficientsa 0 ,a 1 ,a 2 ,b 1 ,b 2 ,c 1 ,andc 2 in(17.8)arefunc-
tions of the uncertain real parameter m . According to (17.6), the coefficient a
|     |     |     | L   |     |     | 0   |
| --- | --- | --- | --- | --- | --- | --- |
dependsinanaffinewayonm L andinbuildingthemodelitmayberepresentedas
|     |     | a   | =a +a | m    |     | (17.9) |
| --- | --- | --- | ----- | ---- | --- | ------ |
|     |     |     | 0 01  | 02 L |     |        |
with
|      |      | 1 (cid:4) |     | (cid:5) |         |     |
| ---- | ---- | --------- | --- | ------- | ------- | --- |
|      | =J + | (L+R)3−R3 |     |         | =(L+R)2 |     |
| a 01 | a    | m         |     | ,       | a 02    |     |
3
Incontrasttoa ,therestcoefficientsdependnonlinearlyandimplicitlyonm ac-
| 0   |     |     |     |     |     | L   |
| --- | --- | --- | --- | --- | --- | --- |
cording to complicated relationships that cannot be used to obtain the uncertainty
model.However,theinvestigationoftheserelationshipsshowsthatwithsufficient
accuracythecoefficientsa ,a ,b ,b ,c ,andc areapproximatedbythefollowing
|     |     | 1 2 1 | 2 1 | 2   |     |     |
| --- | --- | ----- | --- | --- | --- | --- |
rationalfunctionsofm L :
|     |     | a ≈a | +a m | ,   |     |     |
| --- | --- | ---- | ---- | --- | --- | --- |
|     |     | i i1 | i2   | L   |     |     |
1
|     |     | b ≈ |       |       |     | (17.10) |
| --- | --- | --- | ----- | ----- | --- | ------- |
|     |     | i b | +b m  |       |     |         |
|     |     |     | i1 i2 | L     |     |         |
|     |     | ≈   | 1     | i=1,2 |     |         |
|     |     | c   |       | ,     |     |         |
|     |     | i c | +c m  |       |     |         |
|     |     |     | i1 i2 | L     |     |         |
Theconstantsa ,a ,b ,b ,c ,c ,i=1,2,in(17.10)aredeterminedbyleast
| i1  | i2 i1 | i2 i1 | i2  |     |     |     |
| --- | ----- | ----- | --- | --- | --- | --- |
=0.25kg
squaresapproximation,donesothatfor m L thecorrespondingrelation-
ships are fulfilled exactly. Hence, for the nominal value of the payload mass the
manipulatormodelwillbeexact.Theplotsoftheexactandthedeterminedinthis
way approximate dependencies of the coefficients a , b , and c on the payload
|     |     |     |     |     | 1 1 1 |     |
| --- | --- | --- | --- | --- | ----- | --- |

| 374 |     | 17 RobustControlofaFlexible-LinkManipulator |
| --- | --- | ------------------------------------------- |
Fig.17.4 Approximationofa1
mass are shown in Figs. 17.4, 17.5, and 17.6. Similar results are obtained also for
a , b , and c . The relative error in approximatingeach dependenceis biggest for
2 2 2
m =0.15kg.
L
Intheexpressions(17.9)and(17.10)theuncertainparameterm L appearsonce.
Since in (17.8) the coefficients a and a are repeated twice, and b and b three
1 2 1 2
times, it appears that as a whole the parameter m L is repeated in (17.8) 13 times.
However, in the manipulator model, built on the basis of the state space represen-
tationof(17.8),theuncertainparameterm L isrepeated32times,whichmakesthe
robust analysis and design of the system difficult. This number may be reduced
significantly, building the manipulator model by using the function sysic repre-
sentingappropriately(17.8).
Forthisaimthemanipulatorequations(17.8)arewrittenintheform
|     | My¨+N | y˙+N y=Tτ, |
| --- | ----- | ---------- |
1 2
z=P
1 y, (17.11)
|     | α¨ =P | y¨  |
| --- | ----- | --- |
2
where
| (cid:4) | (cid:5) | (cid:4) (cid:5) |
| ------- | ------- | --------------- |
| y=      | T z=    | T               |
| θ η 1   | η 2 ,   | α w L           |

17.2 ALinearModeloftheUncertainSystem 375
Fig.17.5 Approximationofb1
Fig.17.6 Approximationofc1

376 17 RobustControlofaFlexible-LinkManipulator
Fig.17.7 Blockdiagramof
themanipulatormodel
Fig.17.8 Input–output
representationofthe
manipulatormodel
⎡ ⎤ ⎡ ⎤ ⎡ ⎤
a a a d 0 0 0 0 0
0 1 2 r
M=⎣
a 1 0
⎦
, N
=⎣
0 d 0
⎦
, N
=⎣
0 c 0
⎦
,
1 1 1 2 1
a 0 1 0 0 d 0 0 c
2 2 2
⎡ ⎤
(cid:2) (cid:3)
1 (cid:4) (cid:5)
T =⎣ 0 ⎦ , P = 1 b 1 b 2 , P = 1 b b
1 0 (L+R)b (L+R)b 2 1 2
0 1 2
Ablockdiagramcorrespondingtothematrix–vectorequations(17.11)isshown
inFig.17.7.
Themodelwithuncertainparametersisobtainedonthebasisofthegivenblock
diagrambyusingtheM-filemod_flm.mandissavedinthevariableG.Thecon-
stants a , a , a , a , b , b , c , c , i =1,2, are determined by the M-file
01 02 i1 i2 i1 i2 i1 i2
par_flm.m.
AschematicdiagramfortheoutputorderingisshowninFig.17.8.
Asaresultfromtheexecutionofthefilemod_flm.moneobtains
G
USS: 6 States, 4 Outputs, 1 Input, Continuous System
d_1: real, nominal = 0.4, variability = [-40 40]%,
1 occurrence
d_2: real, nominal = 10, variability = [-40 40]%,
1 occurrence
d_r: real, nominal = 0.15, variability = [-20 20]%,
1 occurrence

17.2 ALinearModeloftheUncertainSystem 377
Fig.17.9 Bodeplotsofexactandapproximatedmanipulatormodelswithinputτ andoutputΘ
formL =0.125kg
m_L: real, nominal = 0.25, variability = [-40 40]%,
10 occurrences
Gisanuncertainsystemoftheclassuss,dependingonfouruncertainrealpa-
rameters,m_Lbeingrepeatedtentimes.Theaccuracyofthemodelderivediscon-
firmedbytheclosenessofthe“exact”and“approximated”Bodeplotsofthemanip-
ulatorwithinputthedrivingtorqueτ andoutputthejointangleθ andangleposition
αshowninFigs.17.9and17.10,respectively.Theseplotsareobtainedforthemost
unfavorablecasem =0.15kg.Theexactplotsarecomputedfrom(17.8)usingthe
L
exactvaluesofthecoefficientsandtheapproximated—fromthederiveduncertainty
model.Itcanbeseenthatthematchbetweenthosetwomodelsisverygood.
In the design and analysis of the noncollocated controller, presented latter on,
wetakethreeofthefiveoutputsofthederivedmanipulatormodel.Thatiswhythe
parameterm_Lwilloccur8timesinsteadof10timesasinthefullmodel.Thus,the
totalnumberoftheuncertainparametersisequalto11.
Itisinterestingtonotethatinusingtheoption’full’insteadof’basic’in
urealorinusingthecommandsimplifyitisnotpossibletoachievepositive
result in building the model. For some versions of the model the multiplicity of
theuncertainparameterm isreducedbutthebehaviorofthemodeliscompletely
L
changed.

378 17 RobustControlofaFlexible-LinkManipulator
Fig.17.10 Bodeplotsofexactandapproximatedmanipulatormodelswithinputτ andoutputα
formL =0.125kg
17.3 System Performance Specifications
In this flexible-link manipulator control-system design exercise, the purpose is to
findacontrollerthatsuppressesefficientlytheelasticvibrationsoftheflexiblelink
infastmotionsandmovesthetiptoadesiredpositioninthepresenceofuncertain-
ties in the payload mass, hub and structural damping factors. Since the uncertain-
ties considered are real and structured, the most appropriate robust control design
methodtobeappliedinthepresentcaseisμ-synthesis.
The block diagram of the closed-loop system incorporating the design require-
mentsisshowninFig.17.11.Thecontrolledvariableistheangularpositionαofthe
manipulatortip. Thereference variable,the controlvariable,andthe motortorque
aredenoted,respectively,byr,u,andτ .ThecontrollerK worksonthereference
a
r andfeedbacksignalsofthejointangleΘ andthetipaccelerationα¨.Theinclusion
ofthetipaccelerationinthecontrolschemeaimstoachievebettertip-motionper-
formanceandleadstoanoncollocatedcontrollerstructure.Inputdisturbanceisthe
resistanttorque d.Bytheuseofthesignals n and n andtheshapingfilters W
1 2 n1
andW itispossibletotakeintoaccounttheinfluenceofthenoise,accompanying
n2
themeasurementofθ andα¨,respectively.Furthermore,inthegivendesigncase,we
selectasuitabledynamicmodelandtargetthedynamicsofthedesignedclosed-loop

17.3 SystemPerformanceSpecifications 379
Fig.17.11 Closed-loopinterconnectionstructureoftheflexible-linkmanipulatorsystem
systemtobeclosetothatmodel.Theuseofsuchamodeltorepresentthedesired
dynamics allows us to take into account the requirements on system performance
moreeasilyanddirectly.Inotherwords,suchamodel(namedM inFig.17.11)pre-
scribesthedesireddynamicbehavioroftheclosed-loopsystemfromthereference
signaltothetipposition.TheuncertaintyplantisdenotedbyGinFig.17.11.The
internal, current control loop of the servo drive W is modeled as a first order lag
a
withthetimeconstant0.004sandgainequalto1.
Letthe3×1transfermatrixGbepartitionedas
⎡ ⎤
G (s)
ατ
G(s)=⎣
G (s)
⎦
θτ
G α¨τ (s)
where G ατ , G θτ , G α¨τ are the transfer functions from the control torque τ to the
outputsα,θ,andα¨,respectively,andletthecontrollerisrepresentedas
(cid:4) (cid:5)
K(s)= K
r
(s) K
Θ
(s) K α¨(s)
where K
r
(s), K
Θ
(s), and K α¨(s) are the transfer functions of the controller with
respecttothecorrespondinginputs.Itcanbeshownbydirectmanipulationsthat
⎡ ⎤
(cid:2) (cid:3) r
⎢ ⎥
e p =Φ ⎢
⎣
d⎥
⎦
e n
u 1
n
2

| 380 |     |     | 17  | RobustControlofaFlexible-LinkManipulator |     |     |     |
| --- | --- | --- | --- | ---------------------------------------- | --- | --- | --- |
where
(cid:30)
| W    | (SG W | K −M) | −W   | SG   |           |     |     |
| ---- | ----- | ----- | ---- | ---- | --------- | --- | --- |
| Φ= p | ατ a  | r     |      | p ατ |           |     |     |
|      | W SK  | −W    | S(G  | K +G | α¨τ K α¨) |     |     |
|      | u     | r     | u θτ | θ    |           |     |     |
(cid:31)
|     |     |     | W p SG | ατ W   | a K θ W n1 | W p SG ατ | W a K α¨W n2 |
| --- | --- | --- | ------ | ------ | ---------- | --------- | ------------ |
|     |     |     | W u    | SK θ W | n1         | W u SK    | α¨W n2       |
(17.12)
and
1
S=
|                                     |     | 1−G | W K  | −G              | W K  |     |     |
| ----------------------------------- | --- | --- | ---- | --------------- | ---- | --- | --- |
|                                     |     |     | θτ a | θ α¨τ           | a α¨ |     |     |
| ThedesignobjectiveforthecontrollerK |     |     |      | isthustobesetas |      |     |     |
|                                     |     |     |      |                 | ⎡    | ⎤   |     |
G (s)
ατ
|     |     | (cid:5)Φ(cid:5) |                 |     | ⎣        | ⎦   |         |
| --- | --- | --------------- | --------------- | --- | -------- | --- | ------- |
|     |     | ∞<1             | forallperturbed |     | G θτ (s) |     | (17.13) |
G α¨τ (s)
It is clear that, with appropriately chosen weighting functions, a controller K
satisfyingtheaboveequation(17.13)makestheclosed-loopsystemrobustlystable,
robustly achieving good matching to the dynamic model M (in terms of e ), and
p
| withrestrictedcontroleffort(intermsofe |     |     | u   | ).  |     |     |     |
| -------------------------------------- | --- | --- | --- | --- | --- | --- | --- |
Themodeltransferfunctiontobematchedistakeninthisdesignas
625
M=
s2+50s+625
Thecoefficientsofthistransferfunctionarechosentoensureoverdampedresponse
withasettlingtimeofabout0.19s.Theperformanceweightingfunctionsarechosen
as
s2+25s+150
|     |     | =   |     |     | =0.001 |     |     |
| --- | --- | --- | --- | --- | ------ | --- | --- |
|     |     | W p |     | ,   | W u    |     |     |
s2+22s+0.15
ThecriterionfortheperformanceweightingfunctionW aimstoensuretheclose-
p
nessofthesystemdynamicstothatofthemodelM overthelow-frequencyrange.
The use of the control weighting function W allows us to bound the magnitude
u
of the control action in the frequency range containing the natural frequencies of
the flexible link. The magnitude plot of the inverse of the performance weighting
functionisshowninFig.17.12.
Thenoiseshapingfilters
|     |       | 0.5s+1   |     |     | s+1     |     |     |
| --- | ----- | -------- | --- | --- | ------- | --- | --- |
|     | W =10 | −5       | ,   | W   | =10 −3  |     |     |
|     | n1    | 0.005s+1 |     | n2  | 0.01s+1 |     |     |

17.4 SystemInterconnections 381
Fig.17.12 Inverseofperformanceweightingfunction
aredeterminedaccordingtothespectralcontentsofthesensornoisesn andn at
1 2
the measurements of joint angle and the tip acceleration signals, respectively. The
magnitudeplotsofthenoiseshapingfiltersareshowninFig.17.13.
Themodeltransferfunction,theperformanceandcontrolweightingfunctionsas
wellasthenoiseshapingfiltersareassignedinthefilewts_flm.m.
17.4 System Interconnections
The open-loop interconnection is obtained by the M-file olp_flm. The internal
structure of the 13 states, five-input/five-output open-loop system, which is saved
in the variable sys_ic, is shown in Fig. 17.14. The reference and the noises are
savedinthevariablesref,noise1,andnoise2,thedisturbanceissavedinthe
variabledistandthecontrolsignalinthevariablecontrol.
A schematic diagram of the specific input/output ordering for the variable
sys_icisshowninFig.17.15.
Theblock-diagramusedinthesimulationoftheclosed-loopsystemisshownin
Fig. 17.16. The corresponding closed-loop interconnection, which is saved in the
variablesim_ic,isobtainedbytheM-filesim_flm.
A schematic diagram of the specific input/output ordering for the variable
sim_icisshowninFig.17.17.

382 17 RobustControlofaFlexible-LinkManipulator
Fig.17.13 Noiseweightingfunctions

17.5 ControllerDesignandAnalysis 383
Fig.17.14 Open-loopinterconnectionstructureoftheflexible-linkmanipulatorsystem
Fig.17.15 Schematic
diagramoftheopen-loop
interconnection
17.5 ControllerDesignand Analysis
Let us denote by P(s) the transfer function matrix of the five-input, five-output
open-loopsystemconsistingoftheflexible-linkmanipulatormodelandtheactuator
andweightingfunctions(Fig.17.14).Wemayrepresentthistransferfunctionas
P(s)=F
|     | U (P nom ,Δ | P ) |
| --- | ----------- | --- |
whereP nom isthenominaltransferfunctionandtheuncertaintyΔ P isgivenby
| %(cid:2) | (cid:3)        | &     |
| -------- | -------------- | ----- |
|          | Δ 0 :Δ∈R11×11, | ∈C3×2 |
| Δ :=     |                | Δ     |
| P        | 0 Δ            | F     |
F
Thefirstpartofthismatrixcorrespondstothe11×11uncertainblockΔthatcon-
sistsoftheuncertaintiesintheflexiblemanipulator.ThesecondblockΔ
F isaficti-
tiousuncertainty3×2blockandisintroducedtorepresenttherobustperformance

384 17 RobustControlofaFlexible-LinkManipulator
Fig.17.16 Closed-loop
interconnectionstructureof
theflexible-linkmanipulator
system
Fig.17.17 Schematic
diagramoftheclosed-loop
interconnection
objectiveintheframeworkofthe μ-approach.Theinputstotheblock Δ arethe
F
weightederrorsignalse ande andtheoutputsfromΔ aretheexogenoussignals
p u F
r,n ,andn (inputstothemanipulatorclosed-loopsystem).
1 2
As discussed in previous sections, in order to meet the design objectives a sta-
bilizingcontroller K =[K
r
(s) K
θ
(s) K α¨(s)] is tobefoundsuch that,at eachfre-
quencyω∈[0,∞],thestructuredsingularvaluesatisfiesthecondition
(cid:4) (cid:5)
μ F (P,K)(jω) <1
ΔP L
The fulfillment of the above condition guarantees the robust performance of the
closed-loopsystem,i.e.
(cid:5)Φ(cid:5) ∞<1 (17.14)
In the computation of a μ-controller, there is, however, a numerical problem.
Thatis,withtheinclusionofthemultiple8×8realuncertaintyblock(correspond-
ing to the uncertainty in m ) the D–K iteration algorithm does not converge. In
L
particular,itisdifficulttoobtaintheapproximationofa8×8scalingfunctionma-
trix in the D-step. Hence, in our computation that multiple 8×8 real uncertainty
blockwasremovedintheuncertaintymatrixduringtheD–K iteration.Itshouldbe

17.5 ControllerDesignandAnalysis 385
| Table17.1 | Resultsofthe |     |           |                 |     |                 |
| --------- | ------------ | --- | --------- | --------------- | --- | --------------- |
|           |              |     | Iteration | Controllerorder |     | Maximumvalueofμ |
μ-synthesis
|     |     |     | 1   | 13  |     | 2.035 |
| --- | --- | --- | --- | --- | --- | ----- |
|     |     |     | 2   | 15  |     | 0.970 |
|     |     |     | 3   | 17  |     | 0.585 |
stressedthattherobuststabilityandrobustperformanceanalysisoftheclosed-loop
systemofthedesignedcontroller,whichwillbepresentednext,istestedwithregard
tothewholeuncertaintystructure,i.e.withtheinclusionofthatmultiple8×8real
uncertaintyblock.
Theμ-synthesisiscarriedoutbyusingtheM-filems_flm.mimplementingthe
functiondksyn. In the synthesis, the uncertaintyparameter m is replaced by its
L
nominalvalue,asdescribedabove.
| TheprogressoftheD–K |     |     | iterationisshowninTable17.1. |     |     |     |
| ------------------- | --- | --- | ---------------------------- | --- | --- | --- |
Inthedesignexercise,anappropriatecontrollerisobtainedafterthethirdD–K
iteration. The controller is stable and has an order of 17. The Bode plots of the
μ-controllerareshowninFig.17.18.
It can be seen from Table 17.1 that after the third iteration the maximum value
of μ isequalto 0.585.Notethatthis,however,doesnotnecessarilymeanthatthe
robust performance has been achieved since we neglected the multiple 8×8 real
uncertaintyblockinthecomputation.Hence,additionalrobustperformanceanalysis
isneededasbelow.
The robust stability analysis of the closed-loop system is conducted by the file
rbs_flm,whichtakesintoaccountalluncertaintyblocksdiscussedinSect.17.2.
Theresultfromtheexecutionofthisfileis
| stabmarg                | =   |             |             |     |     |     |
| ----------------------- | --- | ----------- | ----------- | --- | --- | --- |
|                         |     | UpperBound: | 3.4178      |     |     |     |
|                         |     | LowerBound: | 1.9081      |     |     |     |
| DestabilizingFrequency: |     |             | 6.2803e+003 |     |     |     |
report =
| Uncertain          | System       | is      | robustly    | stable to modeled |        | uncertainty. |
| ------------------ | ------------ | ------- | ----------- | ----------------- | ------ | ------------ |
| -- It              | can tolerate |         | up to 191%  | of the modeled    |        | uncertainty. |
| -- A destabilizing |              |         | combination | of 342%           | of the | modeled      |
| uncertainty        |              | exists, | causing     | an instability    |        | at           |
| 6.28e+003          |              | rad/s.  |             |                   |        |              |
Thisresultconfirmsthattheclosed-loopsystemachievesrobuststability.
The frequency response plot of the structured singular value corresponding to
robuststabilityanalysisisshowninFig.17.19.

386 17 RobustControlofaFlexible-LinkManipulator
Fig.17.18 ControllerBodeplots
Fig.17.19 Robuststabilityforμ-controller

17.5 ControllerDesignandAnalysis 387
Fig.17.20 Robustperformanceforμ-controller
Therobustperformanceanalysisisdonebyusingthefilerbp_flm.Asaresult
oneobtains
| perfmarg           | =           |         |     |     |     |
| ------------------ | ----------- | ------- | --- | --- | --- |
|                    | UpperBound: | 1.2612  |     |     |     |
|                    | LowerBound: | 1.2456  |     |     |     |
| CriticalFrequency: |             | 51.7092 |     |     |     |
report =
Uncertain System achieves a robust performance margin of 1.261.
| - A model   | uncertainty | exists   | of size | 125%   | resulting in a |
| ----------- | ----------- | -------- | ------- | ------ | -------------- |
| performance | margin      | of 0.803 | at 51.7 | rad/s. |                |
The frequency response of μ for the robust performance analysis is shown in
Fig.17.20.
Considernowtheclosed-looptransientresponsesthatarecomputedbyusingthe
M-filemcs_flm.
The reference trajectory for the manipulator tip movement in the simulation is
chosenintheform
(cid:21)
|     | at−(a/ψ)sin(ψt)+r |     |     | , 0≤t≤t |     |
| --- | ----------------- | --- | --- | ------- | --- |
|     | r=                |     |     | 0       | m   |
|     | r(t               | ),  |     | t <t≤t  |     |
|     |                   | m   |     | m       | f   |

| 388                                                   |     | 17 RobustControlofaFlexible-LinkManipulator |     |
| ----------------------------------------------------- | --- | ------------------------------------------- | --- |
| Fig.17.21 Referencesignalr(t),velocityandacceleration |     |                                             |     |
Thistrajectoryallowsthetiptobemovedsmoothlyfromanarbitraryinitialposition
| r toadesiredfinalpositionr(t |     | )=at ,withanappropriateψ. |     |
| ---------------------------- | --- | ------------------------- | --- |
| 0                            |     | m m                       |     |
In the simulation, the following numerical values of the parameters are taken:
| =0.1π       | =2.5π | −1;r =0rad;t =0.8s;t | =3s.Theyarechosen |
| ----------- | ----- | -------------------- | ----------------- |
| a r rad/s;ω | r s   | 0 m                  | f                 |
such that to obtain a fast changing reference, that is, settling in the desired final
positionπ/12.5radfor0.8s.
Theplotsofthereferencer(t),velocity,andaccelerationfor30randomcombi-
nationsoftheuncertainparametersareshowninFig.17.21.
In Fig. 17.22 we show the transient response of the tip position α along with
thejointangleθ andthereferencer,computedfor30randomcombinationsofthe
uncertainplantparameters.
The transient response corresponding to the tip deflection w(L,t) is shown in
Fig.17.23.
Thecontrolactiongeneratedbythedesignedμ-controllerisshowninFig.17.24.
The closed-loop frequency responses of the uncertain closed-loop system are
obtainedbytheM-filefrs_flm.m.
The Bode plot of the closed-loop system is shown in Fig. 17.25. The closed-
loop bandwidth is about 10 rad/s. Note that a good match in magnitude between
theclosed-loopsystemandthedynamicmodelM isachievedforfrequenciesupto
100rad/s.
The Bode plots of the tip-deflection transfer function are shown in Fig. 17.26.
Themaximumamplitudeofthetipdeflectionisobservedfortheinputsignalwith
frequency50rad/s.

17.5 ControllerDesignandAnalysis 389
Fig.17.22 Closed-looptransientresponseforμ-controller
Fig.17.23 Tip-deflectiontransientresponseforμ-controller

390 17 RobustControlofaFlexible-LinkManipulator
Fig.17.24 Controlactionforμ-controller
Fig.17.25 Bodeplotoftheuncertainsystem

17.5 ControllerDesignandAnalysis 391
Fig.17.26 Bodeplotsforthetipdeflection
Fig.17.27 Bodeplotsforthedisturbance

392 17 RobustControlofaFlexible-LinkManipulator
Fig.17.28 Magnitudeplotsforthefirstandsecondnoise

17.5 ControllerDesignandAnalysis 393
Fig.17.29 Frequencyresponsesofthefull-orderandreduced-ordercontrollers
InFig.17.27weshowtheBodeplotsoftheuncertainsystemobtainedfromthe
transferfunctionwithrespecttothedisturbance.
Finally,inFig.17.28weshowthemagnitudeplotswithrespecttothefirst and
second noise. It is seen from the figure that the noise in measuring the joint angle
hasanegligibleeffectonthesystemoutput.
Weconsidernowtheorderreductionofthedesignedcontroller.Asindicatedin
Table17.1,theorderoftheμ-controlleris17.Itwouldbegoodforimplementation
if the order could be reduced while essentially keeping the achieved performance.
Forthisaim,weusetheM-filered_flm.m.Afterthebalancedrealizationtrans-
formationofthecontrollerandbyneglectingthesmallHankelsingularvalues,the
orderofthecontrollercanbereducedto12withoutlosingtoomuchperformance.
In Fig. 17.29 we compare the frequency responses of the maximum singular
values of the full-order and reduced-order controllers. The frequencyresponses of
bothfull-orderandreduced-ordercontrollerspracticallycoincide.Thetransientre-
sponsesoftheclosed-loopsystemwithfull-orderandwithreduced-ordercontroller
arealsopracticallyindistinguishable.(Figuresarenotincludedhere.)
Itisinterestingtocomparetheresultsobtainedwiththeμ-controllerwiththose
fromtheconventionalcollocatedPDcontrollerintheformof
u=k (r−θ)−k θ ¨
P D
Theproportionalandderivativecoefficientsarechosenask =358Nm/radand
P
k =28.5Nm/(rad/s).Thevaluesofk andk areselectedsuchthatafterneglect-
D P D

394 17 RobustControlofaFlexible-LinkManipulator
Fig.17.30 Closed-looptransientresponseforthePDcontroller
ingthelinkflexibilitytheclosed-looptransferfunctioncoincideswiththetransfer
functionofthemodel.Theresultsbyusingtheμ-analysismethodinthiscase(i.e.
with the PD controller) are 3.4212 and 0.1398 for the stability margin and perfor-
mancemargin,respectively.Therefore,thePDcontrollerleadstopoorrobustperfor-
manceincomparisontotheμ-controllerdesigned.Thiscanbeseenbycomparing
Figs.17.30and17.31withFigs.17.22and17.23,respectively.
Ithastobenoticedthatgoodresultsinthedesignmayalsobeobtainedbyusing
˙
a collocated controller on the feedback from the joint angle θ and the velocity θ.
Theuseofthetipaccelerationα¨,however,allowsbetterresultswithrespecttothe
robustperformancetobeobtained.
17.6 NonlinearSystem Simulations
Theperformanceoftheμ-controllerdesignedintheprevioussectionisfurtherin-
vestigated by simulations of the nonlinear closed-loop system with this controller.
The simulation is carried out by the Simulink® model nls_flm.mdl using the
nonlinearplantmodel(17.5).Anumberofsimulationsmaybeperformedforsev-
eral values of the payload mass and of the damping coefficients. The Simulink®
modelnls_flm.mdlisshowninFig.17.32.
Before running the simulation, it is necessary to set the model parameters by
usingtheM-fileinit_flm.m.Thevaluesofthedampingcoefficientscorrespond
tothecaseoflightdampingofthemechanicalstructure.Inparticular,thevalueof

17.7 Conclusions 395
Fig.17.31 Tip-deflectiontransientresponseforthePDcontroller
thehubdampingcoefficientd correspondstoarelativeuncertaintyof−20%.The
r
dampingcoefficientsd andd aretakensothattherespectiverelativeperturbations
1 2
ind andd forthenominalpayloadareequalto−40%.
1 2
Thetimeresponseofthetipposition α(t),alongwiththejointangle θ andthe
reference r, for the case of the reduced-order μ-controller and nominal payload
massisgiveninFig.17.33.
Apart from the Simulink® model, in this section we also present the M-files
s3d_flmandp3d_flm,whichallowtoanimatethemotionoftheflexiblemanip-
ulatorwithμ-controllerandPDcontroller,respectively.Thesefilesalsoutilizethe
nonlinearmanipulatormodel.
InFigs.17.34and17.35weshowtheelasticdeflectionw(x,t)asafunctionof
x andt,obtainedfortheμ-controllerandPDcontrollerbythefiless3d_flmand
p3d_flm,respectively.
Inthenonlinearsystemsimulations,itisshownthattheμ-controllerefficiently
suppressestheelasticvibrationsduringthefastmotionofthemanipulatortip.Itthus
justifiesthattheμ-synthesisisanappropriaterobustdesignmethodinthisexercise.
Italsoconfirmsthevalidityoftheuncertainmodelderived.
17.7 Conclusions
Afewconclusionsmaybedrawnasthefollowing,basedontheanalysisanddesign
oftheflexiblemanipulatorcontrolsystem:

396 17 RobustControlofaFlexible-LinkManipulator
metsysraenilnonehtfoledomnoitalumiS
23.71.giF

17.7 Conclusions 397
Fig.17.33 Transientresponseofthenonlinearsystem
• Inapplyinglinearrobustcontrolsystemdesigntechniquesforanonlinearplantit
isusuallyunavoidabletoderiveacomplicateduncertaintymodel,becauseofthe
requirementofasufficientlyaccuratelinearapproximation.Thatwould,however,
adversely affect the controller design and analysis. It is important, therefore, to
simplifythemodelofuncertainty.Methodssuchasthenumericalapproximation
usedinthisstudycanbeconsidered.
• The uncertainty model derived in this study for the flexible manipulator system
containsrealparametricuncertaintiesinahighlystructuredform.Suchamodel
appeals naturally to the application of μ-synthesis and analysis method, which
greatlyreducestheconservativenessinthecontrollerdesign.
• A robust noncollocatedcontroller on the feedback signals of joint angle and tip
acceleration is designed in this study on the basis of the uncertainty model de-
rived and by using the μ-synthesis. The μ-controller shows very good robust
performanceonthetipmotionforawiderangeofpayloadmass.Thecontroller
efficientlysuppressestheelasticvibrationsduringthefastmotionofthemanipu-
latortip.
• Thenonlinearsystemsimulationresultsconfirmthehighperformanceofthecon-
trollerdesignedandalsoverifythevalidityoftheuncertainmodelused.
• It is also possible to investigate various noncollocated and collocated controller
structures on different output feedback signals, with the uncertainty model and
linearizedplantderivedinthisstudy.

398 17 RobustControlofaFlexible-LinkManipulator
Fig.17.34 Elasticdeflectionw(x,t)forthecaseofμ-controller
Fig.17.35 Elasticdeflectionw(x,t)forthecaseofPD-controller

17.8 NotesandReferences 399
17.8 Notesand References
Thecontrolofflexiblemanipulatorshasbeenanareaofintensiveresearchinrecent
years. An efficient approach to improve the manipulator performance is to use a
feedbackfromthemanipulatortipposition[53],tipacceleration[51]orbase-strain
[52]. The usage of such feedbacks leads to a noncollocated control scheme that
mayincreasetheclosed-loopsystemsensitivitytomodelingerrorsortoparameter
uncertainties[137].
The necessity to achieve robustness of the manipulator control system in the
presence of uncertainties makes it appropriate to apply the robust control design
methods.Inafewrecentpaperstheauthorsdevelopdifferent H ∞ controllers[54,
96,159]andμ-synthesiscontrollers[82]forflexible-linkmanipulators.Acommon
disadvantageinthepreviousrobustdesignsforflexiblemanipulatorsistheuseofan
unstructureduncertaintymodelthatleadstopotentiallyveryconservativeresults.

Chapter 18
Robust Control of a Twin-Rotor Aerodynamic
System
This chapter presents the design and experimental evaluation of a 2-degree-of-
freedom,discrete-time,μ-controllerforalaboratoryTwin-RotorAerodynamicSys-
temwithtenuncertainparameters.Thecontrollerimplementedisof24thorderand
ensures robust stability and robust performance of the closed-loop, sampled-data
system.ThiscontrollerisrealizedonaPCbyusingSimulinkCoder®withsampling
frequencyof100Hz.Theexperimentalresultsareclosetotheresultspredictedby
usingthelinearizedmodelofthesystemandhighlightsomeofthedifficultiesasso-
ciatedwithimplementationofrobustcontrollaws.
18.1 Twin-RotorAerodynamicSystem
The Twin-Rotor Aerodynamic System (TRAS) is a laboratory set-up designed for
control experiments whose behavior resembles that of helicopters. The set-up is
showninFig.18.1.Therearetwopropellersateitherendofabeam,drivenbyDC
motors, joined to the base with an articulation. The articulation allows the beam
to be rotated such that its ends move on a spherical surface.The main propeller
(thepropellerwithlargerdiameter)controlsthebeampositionintheverticalplane,
while the tail propeller controls the beam position in the horizontal plane. There
are two counter-weights fixed to the beam that determine the stable equilibrium
position.Thesystemisbalancedinsuchawaythat,whenthemotorsareswitched
off,themainrotorendofbeamislowered.Thecontrolactionsarethemotorsupply
voltages.Themeasuredsystemoutputsarethetwoanglesofbeamdeviationinthe
horizontalplane(azimuthangle)andintheverticalplane(pitchangle).Themotor
controlisrealizedinPulse-WidthModulation(PWM)mode.
TheTRAScontrolaimsatstabilizationofthebeaminanarbitrary(withinpracti-
callimits)desiredposition(pitchandazimuth)ortrackingofadesiredtrajectory.In
thegivencaseweconsiderasmeasurableoutputsthepitchandazimuthanglesonly.
In the general case it is possible also to use the information of propeller angular
velocities.
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 401
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_18,©Springer-VerlagLondon2013

| 402 | 18 RobustControlofaTwin-RotorAerodynamicSystem |     |     |     |
| --- | ---------------------------------------------- | --- | --- | --- |
Fig.18.1 Twin-RotorAerodynamicSystem
| 18.2 NonlinearSystem | Model |     |     |     |
| -------------------- | ----- | --- | --- | --- |
ThemathematicalmodelofTRASisderivedundersomesimplifyingassumptions.
First of all, it is supposed that the dynamics of the propeller subsystem may be
describedbyfirstorderdifferentialequations.Next,itisassumedthatthefrictionin
thesystemisofviscoustype(i.e.,proportionaltotheangularvelocity).Furthermore,
itissupposedthatthe“propeller–air”subsystemmaybedescribedaccordingtothe
principlesofflowtheory.
Considerfirsttherotationofthebeamintheverticalplane,i.e.,aroundthehor-
izontal axis. Taking into accountthat the control torques are produced by the pro-
pellers,thebeamrotationmotionisdescribedas
d2α
v =M
|     | J v | v   |     | (18.1) |
| --- | --- | --- | --- | ------ |
dt2
whereM isthetotalmomentofforcesintheverticalplane,J isthesumofmo-
| v   |     |     | v   |     |
| --- | --- | --- | --- | --- |
mentsofinertiarelativetothehorizontalaxis,andα isthepitchangleofthebeam
v
(thebeamrotationangleintheverticalplane).
| ThetotalmomentofforcesmayberepresentedasthesumM |     |     | =M   | +M + |
| ----------------------------------------------- | --- | --- | ---- | ---- |
|                                                 |     |     | v v1 | v2   |
| +M +M +M                                        |     |     |      |      |
M v3 v4 v5 vd ,inwhichtheindividualtermsaredescribedasfollows.
1. Returntorquecorrespondingtothegravitationalforces
|     | M =−k cos(α | )−k sin(α | )   |     |
| --- | ----------- | --------- | --- | --- |
|     | v1 1        | v 2       | v   |     |
where the coefficients k and k are determined by the mass and geometrical
1 2
sizesofthebeamandthedevicesmountedonit.

| 18.2 NonlinearSystemModel |     |     |     | 403 |
| ------------------------- | --- | --- | --- | --- |
2. Momentofthepropulsiveforceproducedbythemainpropeller
|     | M =l | F (ω ) |     |     |
| --- | ---- | ------ | --- | --- |
|     | v2   | m v v  |     |     |
wherel m isthelengthofthemainpartofthebeam,ω v istheangularvelocityof
themainpropeller,andF (ω )isthedependenceofthepropulsiveforceonthe
v v
angularvelocityofthemainrotor.
3. Momentofcentrifugalforcescorrespondingtothebeammotionaroundthever-
ticalaxis
|     | M =−k Ω2sin(α | )cos(α ) |     |     |
| --- | ------------- | -------- | --- | --- |
|     | v3 3 h        | v v      |     |     |
=dα
whereΩ h h /dt istheangularvelocityofthebeamaroundtheverticalaxis,
α isthebeamazimuthangle(thebeamrotationangleinthehorizontalplane),
h
andk isacoefficient,dependentonthemassandgeometricalsizesofthebeam
3
anddevicesmountedonit.
4. Frictionmomentdependingontheangularvelocityofthebeamaroundthehor-
izontalaxis
|     | M =−k | Ω    |     |     |
| --- | ----- | ---- | --- | --- |
|     | v4    | fv v |     |     |
=dα
whereΩ v v /dt istheangularvelocityaroundthehorizontalaxisandk fv is
aconstant.
5. Crossmomentfromthecontrolforceinthehorizontalplane
|     | M =k | u   |     |     |
| --- | ---- | --- | --- | --- |
v5 hv h
| whereu istheazimuthcontrolactionandk |                     | isaconstant. |     |     |
| ------------------------------------ | ------------------- | ------------ | --- | --- |
| h                                    |                     | hv           |     |     |
| 6. DisturbancetorqueM                | intheverticalplane. |              |     |     |
vd
ThedependenceofthemainpropellerpropulsiveforceF (ω ) ontherotoran-
v v
gular velocity, obtained experimentally, is shown in Fig. 18.2. This dependence is
approximatedusingtheM-fileapprox_char.mbythefifthorderpolynomial
| ˜ =−7.31×10 | −19ω5−3.79×10 | −16ω4+2.41×10 | −11ω3 |     |
| ----------- | ------------- | ------------- | ----- | --- |
F v
|          | v            | v           | v   |     |
| -------- | ------------ | ----------- | --- | --- |
| +1.87×10 | −8ω2+2.89×10 | −5ω −0.0142 |     |     |
|          | v            | v           |     |     |
Inthesameway,itispossibletodescribethebeamrotationaroundthevertical
axis. Taking into account that the control torque is produced by the tail rotor and
thatthemomentofinertiadependsonthepitchangle,therotationinthehorizontal
planeisdescribedby
d2α
h =M
|     | J h | h   |     | (18.2) |
| --- | --- | --- | --- | ------ |
dt2
where M is the total moment of forces in the horizontal plane, J is the sum of
| h   |     |     | h   |     |
| --- | --- | --- | --- | --- |
momentofinertiaaroundtheverticalaxis,J =k cos2(α )+k ,wherethecoeffi-
|     |     | h 4 v | 5   |     |
| --- | --- | ----- | --- | --- |
cientsk 4 andk 5 aredeterminedbythemassandgeometricalsizesofthebeamand
devicesmountedonit.
| ThetotalmomentofforcesmayberepresentedbythesumM |     |     | =M +M | +   |
| ----------------------------------------------- | --- | --- | ----- | --- |
|                                                 |     |     | h h1  | h2  |
+M
M ,inwhichtheindividualtermsaredescribedinthefollowingway.
h3 hd

404 18 RobustControlofaTwin-RotorAerodynamicSystem
Fig.18.2 Mainpropellerthrust
1. Momentofthepropulsiveforceproducedbythetailrotor
|     | M =l F | (ω )cos(α ) |     |
| --- | ------ | ----------- | --- |
|     | h1 t h | h v         |     |
where l is the lengthof the tail part of the beam, ω is the angularvelocityof
| t   |     | h   |     |
| --- | --- | --- | --- |
the tail rotor, and F h (ω h ) is the dependence of the tail propulsive force on the
rotorangularvelocity.
2. Friction moment, depending on the beam angular velocity around the vertical
axis
=−k
|     | M h2 | fh Ω h |     |
| --- | ---- | ------ | --- |
wherek isaconstant.
fh
3. Crossmomentfromthecontrolactioninthehorizontalplane
|                                           | M =k  | cos(α )u     |     |
| ----------------------------------------- | ----- | ------------ | --- |
|                                           | h3 vh | v v          |     |
| whereu isthepitchcontrolactionandk        |       | isaconstant. |     |
| v                                         |       | vh           |     |
| 4. DisturbancetorqueinthehorizontalplaneM |       | hd .         |     |
ThedependenceofthepropulsiveforceF (ω )ofthetailpropellerontherotor
h h
angularvelocity,obtainedexperimentally,isshowninFig.18.3.Thisdependenceis
approximatedbythefifthorderpolynomial
| F ˜ =−2.56×10 | −20ω5−4.10×10 | −17ω4+3.17×10 | −12ω3 |
| ------------- | ------------- | ------------- | ----- |
| h             | h             | h             | h     |
| −7.34×10      | −9ω2+2.13×10  | −5ω −9.14     |       |
h
h

| 18.2 NonlinearSystemModel |     |     |     | 405 |
| ------------------------- | --- | --- | --- | --- |
Fig.18.3 Tailpropellerthrust
Considernowthepropellermotionequations.Sincethedrivemotorsarecontrolled
byPulseWidthModulation,thecontrolactionsarenormalizedsothattheyvaryin
[−1,+1],
the range which corresponds to the variation of the input voltage in the
interval[−24V,+24V].Theequationdescribingthemotionofthemainpropeller
iswrittenintheform
dω
|     | v =u | −H −1(ω |     |        |
| --- | ---- | ------- | --- | ------ |
|     | I v  | v v )   |     | (18.3) |
|     | dt   | v       |     |        |
where I is the moment of inertia of the main propeller and ω =H (u ) is the
| v   |     |     | v   | v v |
| --- | --- | --- | --- | --- |
staticvelocitycharacteristicofthispropeller.
=H
The experimentally obtained characteristic ω (u ) is shown in Fig. 18.4.
|     |     | v   | v v |     |
| --- | --- | --- | --- | --- |
Thisdependenceisapproximatedbytheseventhorderpolynomial
ω˜ =−6.17×103u7−1.30×102u6+1.37×104u5+1.50×102u4
| v                                | v   | v   | v     | v   |
| -------------------------------- | --- | --- | ----- | --- |
| −1.10×104u3−3.76×101u2+7.33×103u |     |     | −5.36 |     |
v
|     | v   | v   |     |     |
| --- | --- | --- | --- | --- |
Similarly,theequationdescribingthemotionofthetailpropelleriswrittenas
|     | dω     | −1(ω  |     |        |
| --- | ------ | ----- | --- | ------ |
|     | I h =u | −H )  |     | (18.4) |
|     | h      | h h h |     |        |
dt
=H
whereI h isthemomentofinertiaoftailrotorandω h h (u h )isthestaticvelocity
characteristicofthispropeller.
The experimentallyobtainedcharacteristic ω =H (u ) is shown in Fig. 18.5.
|     |     | h   | h h |     |
| --- | --- | --- | --- | --- |
Thischaracteristicisapproximatedbythefifthorderpolynomial

406 18 RobustControlofaTwin-RotorAerodynamicSystem
Fig.18.4 Mainrotorvelocitycharacteristic
Fig.18.5 Tailrotorvelocitycharacteristic

18.3 LinearizedSystemModel 407
Table18.1 Parametersofthe
| Parameter |     | Value | Units |
| --------- | --- | ----- | ----- |
nonlinearmodel
kgm2
| Ih  |     | 1/37000 |      |
| --- | --- | ------- | ---- |
| Iv  |     | 1/6100  | kgm2 |
3.00581×10−2
| Jv  |     |              | kgm2      |
| --- | --- | ------------ | --------- |
| k1  |     | 5.00576×10−2 | Nm        |
| k2  |     | 9.36008×10−2 | Nm        |
|     |     | 2.12485×10−2 | Nms2/rad2 |
k3
| k4  |     | 2.37904×10−2 | kgm2 |
| --- | --- | ------------ | ---- |
3.00962×10−3
| k5  |     |              | kgm2    |
| --- | --- | ------------ | ------- |
| kfh |     | 5.88996×10−3 | Nms/rad |
1.27095×10−2
| kfv |     |     | Nms/rad |
| --- | --- | --- | ------- |
4.17495×10−3
| khv |     |               | Nm  |
| --- | --- | ------------- | --- |
| kvh |     | −1.78200×10−2 | Nm  |
| lm  |     | 0.202         | m   |
| lt  |     | 0.216         | m   |
ω˜ =−6.17×103u5−1.30×102u4+1.37×104u3
| h                     | h   | h     | h   |
| --------------------- | --- | ----- | --- |
| +1.50×102u2−1.10×104u |     | −37.6 |     |
|                       | h   | h     |     |
Equations(18.1)–(18.4)togetherwiththeequations
dα
v =Ω
|     |     | v   | (18.5) |
| --- | --- | --- | ------ |
dt
dα
h =Ω
|     |     | h   | (18.6) |
| --- | --- | --- | ------ |
dt
constitutethesixthordernonlinearmodeloftheTwin-RotorAerodynamicSystem.
Theinputvariablesarethevoltagesu andu ofthetailrotorandmainrotormo-
|     | h   | v   |     |
| --- | --- | --- | --- |
tors,respectively,andoutputvariablesaretheazimuthangleα h andpitchangleα v .
The plant is two-channel and there is an interaction between the two channels. In
ordertorevealinfullthedynamicbehavioroftheplantitshouldbeconsideredas
multivariable,i.e.,thetwochannelscannotbeconsideredasindependent.
The nominal values of the coefficients participating in the model are given in
Table18.1.
| 18.3 LinearizedSystem | Model |     |     |
| --------------------- | ----- | --- | --- |
ThemodeloftheTwin-RotorAerodynamicSystemislinearizedanalyticallyunder
theusualassumptionforsmalldeviationsofthevariables,describingthesystembe-
havior,aroundtheirtrimvalues.Thevariablesdescribingthebeamangularposition
arerepresentedintheform

408 18 RobustControlofaTwin-RotorAerodynamicSystem
Table18.2 Propeller
Parameter Value Units
coefficients
kHh 9.83891×103 rad/s
kFh 2.12932×10−5 Ns/rad
kHv 4.87457×103 rad/s
kFv 3.07723×10−4 Ns/rad
α =α +δα , ω =ω +δω , Ω =Ω +δΩ
v v,nom v v v,nom v v v,nom v
α =α +δα , ω =ω +δω , Ω =Ω +δΩ
h h,nom h h h,nom h h h,nom h
where α , ω , Ω , α , ω , Ω denote the nominal values
v,nom v,nom v,nom h,nom h,nom h,nom
of the corresponding parameters and δα , δω , δΩ , δα , δω , δΩ denote the
v v v h h h
deviations from their nominal values. In a similar way the motor control voltages
arerepresentedas
u =u +δu , u =u +δu
v v,nom v h h,nom h
Thelinearizationisdonearoundsteadyoperationpointassumingthat
Ω =0, Ω =0
v,nom h,nom
Itissupposedthatthepositionofthecounter-weightsischosensothatforaninput
signal u =0.3 the beam is in strictly horizontal position. In this equilibrium
v,nom
position of the beam the main rotor thrust is balanced by the gravitational forces
actingonthebeamandthedevicesmountedonit.
Considerfirstthelinearizationofthestaticcharacteristicsoftwopropellers.Itis
donebyusingtheM-fileapprox_char.m.
The operation point of the main propeller is determined for motor voltage
u =0.3. The velocity characteristic of this propeller is approximated by the
v,nom
linear relationship ω =k u . The coefficient k is found by differentiatingthe
v Hv v Hv
approximatingpolynomialω˜ inu andsubstitutingthemotorvoltagebythevalue
v v
u =0.3 in the result obtained. Since the linear relationship obtained may be
v,nom
written as u = 1 ω , then it follows that the inverse function H −1 is approxi-
v kHv v v
matedbythecoefficient1/k .
Hv
From the polynomial ω˜ , approximating the velocity characteristic of the main
v
propeller,itisfoundthatforu =0.3onehasω =1926.4r.p.m.Thestaticcharac-
v v
teristicF (ω )ofthemainthrustisapproximatedbythelinearrelationshipk ω .
v v Hv
˜
v
Thecoefficientk isdetermineddifferentiatingtheapproximatingpolynomialF
Hv v
in ω and substituting the rotor angular velocity by the value ω =1926.4 in the
v v
resultobtained.
The static characteristics of the tail rotor are linearized in a similar way deter-
miningthepropelleroperationpointforu =0.
h
Thecoefficientsobtainedfromthelinearizationofthepropellerstaticcharacter-
isticsareshowninTable18.2.

18.3 LinearizedSystemModel 409
Consider next the linearization of plant differential equations. There are some
trigonometricfunctionsofthepitchangleintheseequationsthathavetobeapprox-
imatedbylinearrelationships.Wehave
sin(α +δα )≈sin(α )+cos(α )δα
v,nom v v,nom v,nom v
and
cos(α +δα )≈cos(α )−sin(α )δα
v,nom v v,nom v,nom v
ReplacingtheseapproximationsintheexpressionforthetorqueM ,participating
v1
in(18.1),oneobtains
M =M +R δα
v1 v1,nom v v
where M = −k cos(α ) − k sin(α ), R = k sin(α ) −
v1,nom 1 v,nom 2 v,nom v 1 v,nom
k cos(α ).
2 v,nom
ThetorqueM isrepresentedintheform
v2
M =M +l k δω
v2 v2,nom m Fv v
whereM =l k (ω ).
v2,nom m Fv v,nom
ThetorqueM isrepresentedas
v3
M =M −2k Ω sin(α )cos(α )δΩ
v3 v3,nom (cid:6)3 h,nom v,nom v,n(cid:7)om h
−k Ω2 cos2(α )−sin2(α ) δα
3 h,nom v,nom v,nom v
where M = k Ω sin(α )cos(α ). Taking into account that
v3,nom 3 h,nom v,nom v,nom
Ω =0, further on the dependence of the torque M on δΩ and on δα is
h,nom v3 h v
neglected.
ThetorquesM andM aregivenintheformoflinearrelationshipsandtheir
v4 v5
linearizationisobvious.
Considernowthelinearizationof(18.2).ThetorqueM isrepresentedas
h1
M =M +l k cos(α )δω −l k sin(α )δα
h1 h1,nom t Fh v,nom h t Fh v,nom v
whereM =l k ω cos(α ).
h1,nom t Fh h,nom v,nom
ThetorqueM isrepresentedas
h3
M =M −k sin(α )u δα +k cos(α )δu
h3 h3,nom vh v,nom v,nom v vh v,nom v
whereM =k cos(α )u .
h3,nom vh v,nom v,nom
Equations(18.3)and(18.4)arelinearized,respectively,as
dδω
I v =δu −(1/k )δω
v
dt
v Hv v
dδω
I h =δu −(1/k )δω
h
dt
h Hh h
TheobtainedlinearizedmodeloftheTwin-RotorAerodynamicSystemisshown
inFig.18.6.(Hereandnextthevariabledeviationsaredenotedbythesamenamesas
thecorrespondingvariables.)Theplanthastwochannelsandthereisaninteraction
between these channels. In order to reveal in full the plant behavior the system
should be considered as multivariable, i.e., the two channels cannot be considered
independently.

| 410 | 18  | RobustControlofaTwin-RotorAerodynamicSystem |     |
| --- | --- | ------------------------------------------- | --- |
Fig.18.6 Block-diagramofthelinearizedmodel
18.4 UncertaintyModeling
Foruncertainparametersinthemathematicaldescriptionoftheaerodynamicalsys-
temweconsiderthemomentofinertiaJ withrespecttotheverticalaxis,thrustco-
h
efficientsk Fh ,k Fv ofbothrotors,velocitygainsk Hh ,k Hv ofthetworotors,friction
coefficients k , k , cross momentcoefficients k , k , as wellas the coefficient
|     | fh fv | vh hv |     |
| --- | ----- | ----- | --- |
R ofthereturntorque,altogether10parameters.Theuncertaintiesinthemoment
v
ofinertiaJ h andinthecoefficientR v areduetotheirdependenceonthepitchangle
α , the uncertainties in the coefficients k , k , k , and k are introduced as a
| v   |     | Fh Fv Hh | Hv  |
| --- | --- | -------- | --- |
resultofthemeasuringandapproximationofthestaticcharacteristicsoftherotors,
theuncertaintiesinthecoefficients k fh and k fv areduetotheerrorsindetermina-
tion of the friction moments, and the uncertainties in the coefficients k and k
vh hv
resultfromsimplificationoftheaerodynamicinteractionbetweenthetwochannels.
FurthermoreweassumethatthemomentofinertiaJ h andthecoefficientsk Fh ,k Fv ,
k ,andk areknownwitherrorsupto10%whiletherestcoefficientscomewith
Hh Hv
errorsupto5%.
ThetenrealuncertainparametersJ h ,k Hh ,k Hv ,k Fh ,k Fv ,k fh ,k fv ,k hv ,k vh ,and
R aresetbyusingthefollowingcommandlines:
v
| J_h_nom | = 0.023790*(cos(alpha_v))^2                      | + 0.0030096; |     |
| ------- | ------------------------------------------------ | ------------ | --- |
| J_h     | = ureal(’J_h’,J_h_nom,’Percentage’,10);          |              |     |
| k_H_h   | = ureal(’k_H_h’,9.8389*10^3,’Percentage’,10);    |              |     |
| k_F_h   | = ureal(’k_F_h’,2.1293*10^(-5),’Percentage’,10); |              |     |
| k_f_h   | = ureal(’k_f_h’,0.00589,’Percentage’,5);         |              |     |
| k_v_h   | = ureal(’k_v_h’,-0.01782,’Percentage’,5);        |              |     |

18.4 UncertaintyModeling 411
Fig.18.7 Uncertainmodel
ofthetwin-rotoraerodynamic
system
Fig.18.8 Schematicdiagram
ofthemodelinput–output
connection
| k_H_v   | = ureal(’k_H_v’,4.8746*10^3,’Percentage’,10);     |     |     |     |                        |     |
| ------- | ------------------------------------------------- | --- | --- | --- | ---------------------- | --- |
| k_F_v   | = ureal(’k_F_v’,3.07726*10^(-4),’Percentage’,10); |     |     |     |                        |     |
| k_f_v   | = ureal(’k_f_v’,0.01271,’Percentage’,5);          |     |     |     |                        |     |
| k_h_v   | = ureal(’k_h_v’,0.004175,’Percentage’,5);         |     |     |     |                        |     |
| R_v_nom | = 0.050058*sin(alpha_v)                           |     |     | -   | 0.093601*cos(alpha_v); |     |
| R_v     | = ureal(’R_v’,R_v_nom,’Percentage’,5);            |     |     |     |                        |     |
TheuncertainTRASmodelisobtainedonthebasisoftheblock-diagram,shown
in Fig. 18.6, implementing the function sysic. This system model is created by
theM-filemod_tras.m.
TheuncertainTRASsystemisdescribedasacontrolplantbytheequation
|     |     |     |     | (cid:2) | (cid:3) |     |
| --- | --- | --- | --- | ------- | ------- | --- |
M
|     |     |     | y=G | d   |     |     |
| --- | --- | --- | --- | --- | --- | --- |
u
where
|     |     | (cid:2) (cid:3) |     | (cid:2) (cid:3) |     | (cid:2) (cid:3) |
| --- | --- | --------------- | --- | --------------- | --- | --------------- |
|     |     | α               |     | u               |     | M               |
|     |     | y= h ,          | u=  | h ,             | M   | = hd            |
|     |     | α               |     | u               |     | d M             |
|     |     | v               |     | v               |     | vd              |
The uncertain model of the Twin-Rotor Aerodynamic System is shown in
Fig.18.7.
The schematic diagram of the model input–output connection is shown in
Fig.18.8.
Letusintroducetherepresentation
|     |     |     | G=[G | G   | ]   |     |
| --- | --- | --- | ---- | --- | --- | --- |
|     |     |     |      | d   | u   |     |
suchthat
|     |     |     | y=G | M +G | u   |     |
| --- | --- | --- | --- | ---- | --- | --- |
|     |     |     |     | d d  | u   |     |
InthelastexpressionG d istheplanttransferfunctionmatrixwithrespecttodistur-
bancesandG isthetransferfunctionmatrixwithrespecttothecontrolsignals.
u
Thefrequencyresponseplotoftheuncertainplantsingularvalues,obtainedfrom
| thetransferfunctionG |     | ,isshowninFig.18.9. |     |     |     |     |
| -------------------- | --- | ------------------- | --- | --- | --- | --- |
u

412 18 RobustControlofaTwin-RotorAerodynamicSystem
Fig.18.9 Frequencyresponsesoftheuncertainplant
Fig.18.10 Closed-loopsystemwith2-degree-of-freedomcontroller
18.5 Closed-Loop System PerformanceRequirements
The block-diagramof the closed-loopsystem with 2-degree-of-freedomcontroller
isshowninFig.18.10.

18.5 Closed-LoopSystemPerformanceRequirements 413
Fig.18.11 Block-diagramoftheclosed-loopsystemwithperformancerequirements
To obtain good performance of the system response we shall implement a
2-degree-of-freedomcontroller.Thecontrolactionsaregeneratedaccordingtothe
expression
(cid:2) (cid:3)
r
|     | u=[K | ]        | =K r−K |     |
| --- | ---- | -------- | ------ | --- |
|     |      | r K y −y | r y y  | c   |
c
where K is the output feedback transfer function matrix and K is the pre-filter
| y   |     |     |     | r   |
| --- | --- | --- | --- | --- |
transferfunctionmatrix.
Theblock-diagramoftheclosed-loopsystemthatincludestheuncertainTRAS
model,thefeedbackandthecontroller,aswellastheelementsreflectingtheperfor-
mance requirements, is shown in Fig. 18.11. The system has reference inputs (r),
input disturbances (d) and noise (n) introduced in measurement of the angles α
h
α d.)
and v . (Here and further on the disturbance vector is denoted for brevity by
TheTRASuncertainmodelisthestatespaceobjectG.
Thesystemhastwooutputsignals(e ande ).TheblockMistheidealdynamics
|     |     | y   | u   |     |
| --- | --- | --- | --- | --- |
model that the designed closed-loop system should match to. The feedback of the
systemisrealizedbythevectory =y+W n,wherethemeasurementnoisenisa
c n
randomvectorwithunit2-normandW isthetransfermatrixofthenoiseshaping
n
filters.
| Theweightedclosed-loopsystemoutputse |     |     | ande satisfytheequation |     |
| ------------------------------------ | --- | --- | ----------------------- | --- |
y u
⎡ ⎤
| (cid:2) (cid:3) (cid:2) |     |     |     | (cid:3) |
| ----------------------- | --- | --- | --- | ------- |
r
| e W | (S G K −M) | W S G    | −W S G | K W ⎣ ⎦        |
| --- | ---------- | -------- | ------ | -------------- |
| y = | p o u r    | p o d    | p o    | u y n d (18.7) |
| e   | W S K      | −W S K G | −W S   | K W            |
| u   | u i r      | u i y    | d u i  | y n            |
n
wherethematrixS =(I+K G ) −1istheinputsensitivitytransferfunctionmatrix
|        | i                                                     | y u |     |     |
| ------ | ----------------------------------------------------- | --- | --- | --- |
| =(I +G | −1                                                    |     |     |     |
| andS o | u K y ) istheoutputsensitivitytransferfunctionmatrix. |     |     |     |

414 18 RobustControlofaTwin-RotorAerodynamicSystem
Table18.3 H∞functionsto
Function Description
beminimized
Wp(SoGuKr −M) Weighteddifferencebetweenidealandreal
closed-loopsystem
WpSoGd Weightedsensitivitytodisturbance
WpSoGuKyWn Weightedsensitivitytonoise
WuSiKr Weightedcontrolactionduetoreference
WuSiKyGd Weightedcontrolactionduetodisturbance
WuSiKyWn Weightedcontrolactionduetonoise
Theperformancecriterionrequiresthetransferfunctionmatrixfromtheexoge-
nousinputsignalsr,d,andntotheoutputsignalse ande tobesmallinthesense
y u
of(cid:5)·(cid:5) ∞,forallpossibleuncertainplantmodelsG.Thetransferfunctionmatrices
W and W are used to reflect the relative importance of the different frequency
p u
rangesforwhichtheperformancerequirementsshouldbefulfilled.Thesixtransfer
functionmatriceswhichconstitutethetransfer functionmatrixbetweenthe inputs
andoutputsoftheextendedsystemaredescribedinTable18.3.
ThedesignproblemfortheTwin-RotorAerodynamicSystemistofindalinear
controllerK(s)inthereferenceandmeasurableoutput
K=[K K ]
r y
thathastoensurethefollowingpropertiesoftheclosed-loopsystem:
18.5.1 Robust Stability
The closed-loop system achieves robust stability if this system is internally stable
forallpossibleplantmodelsG.
18.5.2 NominalPerformance
Theclosed-loopsystemachievesnominalperformanceiftheperformancecriterion
issatisfiedforthenominalplantmodel
(cid:24)(cid:2) (cid:3)(cid:24)
(cid:24) (cid:24) Wp(So,nomGu,nomKr −M) WpSo,nomGd,nom −WpSo,nomGu,nomKyWn (cid:24) (cid:24)
(cid:24) WuSi,nomKr −WuSi,nomKyGd,nom −WuSi,nomKyWn (cid:24)
∞
<1
18.5.3 Robust Performance
Theclosed-loopsystemshouldremaininternallystableforallGandinadditionthe
performancecriterion

18.6 SystemInterconnections 415
Fig.18.12 Open-loopsystemstructure
| (cid:24)(cid:2) |     |     |     | (cid:3)(cid:24) |
| --------------- | --- | --- | --- | --------------- |
| (cid:24)        | −M) |     | −   | (cid:24)        |
(cid:24) W p (S o G u K r W p S o G d W p S o G u K y W n (cid:24)
| (cid:24) |       |          |           | (cid:24) <1 (18.8) |
| -------- | ----- | -------- | --------- | ------------------ |
|          | W S K | −W S K G | − W S K W |                    |
|          | u i r | u i y    | d u i y   | n ∞                |
shouldbesatisfiedforeachG.
| 18.6 System | Interconnections |     |     |     |
| ----------- | ---------------- | --- | --- | --- |
Theinternalstructureoftheeight-input,eight-outputopen-loopsystemof16thor-
der,whichissavedasthevariablesys_ic,isshowninFig.18.12.Thereference,
disturbance, and noise are saved as the variables ref, dist and noise, respec-
tively. The control action is saved as the variable control. All variables shown
inthefigurehavetwoelements.Theopen-loopsysteminterconnectionissetbythe
M-filedlp_trasimplementingthefunctionsysic.
The schematic diagram showing the specific input/output arrangement of the
variablesys_ic,isshowninFig.18.13.
The block-diagram used in the closed-loop system simulation is shown in
Fig.18.14.Thecorrespondingclosed-loopinterconnectionthatissavedinthevari-
ablesim_icisobtainedbytheM-filesim_tras.
Figure 18.15 shows the schematic diagram of the input/output arrangement of
thevariablesim_ic.
18.7 μ-Synthesis
ItispossibletoimplementdifferentmethodsintheTRAScontrollerdesigninclud-
ingseveralversionsofH
∞-optimizationandμ-synthesis.Accordingtotheexper-

416 18 RobustControlofaTwin-RotorAerodynamicSystem
Fig.18.13 Schematicinput–outputdiagramoftheopen-loopsystemstructure
Fig.18.14 Closed-loopsystemstructure
Fig.18.15 Schematicinput–outputdiagramoftheclosed-loopsystemstructure

18.7 μ-Synthesis 417
Fig.18.16 Block-diagramof
μ-synthesis
iments performed best results are obtained by using μ-synthesis of a 2-degree-of-
freedom controller. For this reason we represent in this section only the design of
suchatypeofcontroller.
The closed-loop system block-diagram corresponding to the μ-synthesis prob-
lem is shown in Fig. 18.16. The matrix P is the transfer function matrix of the
extendedopen-loopsystemshowninFig.18.12.
The control actions to the plant are realized by a computer in real time with
samplingfrequencyf =100Hz.Forthisreasontheμ-synthesisisimplementedto
s
designadiscrete-timecontrolleratthissamplingfrequency.
Let us denote by P (z)=F (N ,Δ) the transfer function matrix of the dis-
| d U | d   |     |
| --- | --- | --- |
cretizedeight-inputeight-outputopen-loopsystemsys_ic,whichconsistsofthe
uncertainplantmodelplustheweightingfunctions,andlettheblock-structureΔ
Pd
isdefinedas
| %(cid:2) | (cid:3) | &   |
| -------- | ------- | --- |
Δ 0
| Δ := | :Δ∈R10×10,Δ | ∈C6×4 |
| ---- | ----------- | ----- |
| Pd   |             | F     |
0 Δ F
The first block of the matrix Δ , the block Δ, corresponds to the parametric un-
Pd
certainties,includedinthemodeloftheaerodynamicsystem.ThesecondblockΔ
F
isafictitiousuncertaintyblock,usedtoincludetheperformancerequirementsinto
the framework of the μ-approach. The inputs of this block are the weighted error
signalse y ande u ,andtheoutputsaretheexogenoussignalsr,d,andn.
The aim of the μ-synthesis is to find a discrete stabilizing controller K , such
d
that for each frequency ω∈[0,π/T ], where T =2π/f , the structured singular
|     | s s | s   |
| --- | --- | --- |
valueμsatisfiesthecondition
| (cid:4) | (cid:5)     |     |
| ------- | ----------- | --- |
| μ F     | (N ,K )(jω) | <1  |
ΔPd L d d
where F L (N d ,K d ) is the closed-loop transfer function matrix. The fulfillment of
thisconditionguaranteestherobustperformanceoftheclosed-loopsystem,i.e.
| (cid:24) | (cid:5)(cid:24) |     |
| -------- | --------------- | --- |
(cid:4)
| (cid:24)                          | (cid:24)           |     |
| --------------------------------- | ------------------ | --- |
| F U F L                           | (N d ,K d ),Δ Pd ∞ | <1  |
| foralluncertaintiesΔ with(cid:5)Δ | (cid:5) ∞<1.       |     |
| Pd Pd                             |                    |     |
ThetransferfunctionmatrixMoftheidealmatchingmodelischosenasdiagonal
inordertosuppresstheinteractionbetweenthetwochannelsandistakenas
|     | (cid:2) (cid:3) |     |
| --- | --------------- | --- |
w 0
M(s)= m1
|     | 0 w m2 |     |
| --- | ------ | --- |

418 18 RobustControlofaTwin-RotorAerodynamicSystem
Fig.18.17 Modelfrequencyresponses
where
1
w =
m1 1.5s2+1.2s+1
1
w =
m2 2.0s2+1.6s+1
Inthechoiceofthismodelitwasassumedthattheazimuthdynamicsisfasterthan
thepitchdynamics.
ThemodelmagnituderesponsesareshowninFig.18.17.
Theμ-synthesisisdoneforseveralperformanceweightingfunctionsthatensure
a good balance between system performance and robustness. On the basis of the
experimentalresults,wechoosetheperformanceweightingfunction
| (cid:30) |     |     | (cid:31) |
| -------- | --- | --- | -------- |
−2 80s+1
| 8.7×10 |          | −0.01  |           |
| ------ | -------- | ------ | --------- |
| (s)=   | 80s+10−3 |        |           |
| W p    |          | 7.0×10 | −1 500s+1 |
0.03
500s+10−3
andthecontrolweightingfunction
| (cid:30) |           |     | (cid:31) |
| -------- | --------- | --- | -------- |
| 4.0×10   | −50.05s+1 |     | 0        |
10−4s+1
W (s)=
| u   | 0   | 2.304×10 | −4 0.1s+1 |
| --- | --- | -------- | --------- |
10−4s+1
The control weighting functions are chosen so that the azimuth control action to
beintherange[−0.8,0.8]andthepitchcontrolactionintherange[−0.5,1].The
weightingfunctionsaresetintheM-filewts_tras_mu.m.

18.7 μ-Synthesis 419
Fig.18.18 Inverseperformanceweightingfunctions
Thefrequencyresponsesoftheinverseperformanceweightingfunctionaregiven
inFig.18.18.
The frequency responses of the inverse control weighting function are given in
Fig. 18.19. The control weighting functions are chosen as high pass filters with
appropriatebandwidthinordertoimposeconstraintsonthespectrumofthecontrol
actions.
The experiments with the control laws designed shows that the behavior of the
real closed-loop system is very sensitive to the weighting functions used. That is
whytheprecisetuningoftheweightingfunctionsrequiresalargevolumeofexper-
iments.
Thenoisetransferfunctionmatrixistakenas
(cid:2) (cid:3)
w (s) 0
W (s)= n
n 0 w (s)
n
where the transfer function w =10 −2 s is a high pass filter whose output is
n s+1
significantabove10rad/s.
The magnitude frequency response obtained from the transfer function w is
n
showninFig.18.20.Thisweightingfunctioncorrespondstomeasurementerrorin
thehighfrequencyrangeabout1×10 −2 rad.
Theμ-synthesisisperformedbyusingtheM-filedms_tras.m,implementing
thefunctiondksyn.
TheD–K iterationrunisshowninTable18.4.

420 18 RobustControlofaTwin-RotorAerodynamicSystem
Fig.18.19 Inversecontrolactionweightingfunctions
Fig.18.20 Noiseweightingfunction

| 18.7 μ-Synthesis |             |     |           |     |     |                 |     | 421 |
| ---------------- | ----------- | --- | --------- | --- | --- | --------------- | --- | --- |
| Table18.4        | Resultsfrom |     |           |     |     |                 |     |     |
|                  |             |     | Iteration |     |     | Controllerorder |     | μ   |
μ-synthesisD–Kiteration
|           |                                     |     | 1   |     |     | 16  |     | 235.419 |
| --------- | ----------------------------------- | --- | --- | --- | --- | --- | --- | ------- |
|           |                                     |     | 2   |     |     | 16  |     | 4.535   |
|           |                                     |     | 3   |     |     | 20  |     | 1.226   |
|           |                                     |     | 4   |     |     | 22  |     | 0.980   |
|           |                                     |     | 5   |     |     | 24  |     | 0.968   |
| Fig.18.21 | Frequencyresponsesoftheμ-controller |     |     |     |     |     |     |         |
Five iterations are performed that decrease the maximum value of μ to 0.971.
Thefinalcontrollerobtainedisof24thorder.
The singular value frequency response plot of the μ-controller singular values
areshowninFig.18.21.
The robust stability and robust performance analysis of the closed-loop system
| μ-controller, |     |         |       |          | dmu_tras.m, |     |          |               |
| ------------- | --- | ------- | ----- | -------- | ----------- | --- | -------- | ------------- |
| with          |     | done by | using | the file |             |     | produces | the following |
results.
report =
| Uncertain | System       | is          | robustly | stable |        | to modeled | uncertainty.   |     |
| --------- | ------------ | ----------- | -------- | ------ | ------ | ---------- | -------------- | --- |
| -- It     | can tolerate |             | up to    | 521%   | of the | modeled    | uncertainty.   |     |
| -- No     | modeled      | uncertainty |          | exists |        | to cause   | an instability |     |
| at        | 0.001        | rad/s.      |          |        |        |            |                |     |

| 422       |                                       | 18 RobustControlofaTwin-RotorAerodynamicSystem |     |     |     |
| --------- | ------------------------------------- | ---------------------------------------------- | --- | --- | --- |
| Fig.18.22 | Robuststabilityoftheclosed-loopsystem |                                                |     |     |     |
report =
| Uncertain | System achieves | a robust | performance | margin |     |
| --------- | --------------- | -------- | ----------- | ------ | --- |
of 1.041.
| -- A model  | uncertainty | exists   | of size 103%   | resulting | in a |
| ----------- | ----------- | -------- | -------------- | --------- | ---- |
| performance | margin      | of 0.968 | at 21.4 rad/s. |           |      |
Thefrequencyresponsesofthestructuredsingularvaluethatcorrespondstoro-
buststabilityanalysisareshowninFig.18.22.
Thefrequencyresponseofμ,correspondingtotherobustperformanceanalysis
oftheclosed-loopsampled-datasystem,isshowninFig.18.23.
The frequency responses of the uncertain closed-loop system are obtained by
the M-file dfrs_tras.m. The frequency responses of the singular values of the
closed-loop transfer function matrix for random values of the plant uncertain pa-
rameters are shown in Fig. 18.24. It is seen that as a result of achieving robust
performance,theclosed-loopsystemfrequencyresponsesareclosetotheseofthe
model(shownwithdashedlines).
Thefrequencyresponseplotofthesingularvaluesofdisturbancetransferfunc-
tion matrix (output sensitivity function S ) is shown in Fig. 18.25. (The inverse
o
performancefunctionsareshownwithdashedlines.)Thedisturbanceattenuationis
morethan100times(40dB).
The frequency response plot of the singular values of the transfer function ma-
trix from noises to outputs for the controller Kd are shown in Fig. 18.26. The
mu

18.7 μ-Synthesis 423
Fig.18.23 Robustperformanceoftheclosed-loopsystem
Fig.18.24 Frequencyresponsesoftheclosed-loopsystem(–)andmodel(--,-.)

424 18 RobustControlofaTwin-RotorAerodynamicSystem
Fig.18.25 Singularvalueplotofthesensitivityfunction(–)andtheinverseperformanceweight-
ingfunction(--,-.)
Fig.18.26 Singularvalueplotofthenoisetransferfunction

18.7 μ-Synthesis 425
Fig.18.27 Frequencyresponsesoftheinputsensitivityfunction(–)andinversecontrolweighting
function(--,-.)
strongestinfluencehavethenoiseswithfrequencybetween5rad/sand10rad/s,but
theireffectontheclosed-loopsystemoutputisnegligible.
InFig.18.27weshowthefrequencyresponsesoftheinputsensitivity.Themaxi-
muminfluenceofthedisturbancesontheplantinputisintherangearound10rad/s.
Thefrequencyresponseofthenoise-to-controlloop(Fig.18.28)showsthatone
may expect high level of the noises at the actuator inputs. In Fig. 18.28 we show
the frequency response plot of the singular values of the transfer function matrix
fromnoisetocontrolactions.Themaximumofthelargersingularvalueisequalto
20dB,whichshowsthatthemagnitudeofthenoisesattheplantinputis10times
largerthanthemagnitudeofthenoisesatthesensoroutputs.Theselargenoisesare
duetotherelativelyhighgainsinthecontroller(upto104).
The singular values of the open-loop system with μ-controller are shown in
Fig.18.29.
Considernowthetransientresponsesoftheclosed-loopsystem.Theseresponses
are obtained for 30 different values of the uncertain parameters implementing the
M-filedsl_tras.m.
The transient responses of the sampled-data closed-loop system, obtained for
differentrandomvaluesoftheuncertainparameters,areshowninFig.18.30.These
processeshaveacceptableperformance.
The control actions for different values of the uncertain parameters are shown
inFig.18.31.Themotorinputsignalsarelessthan1forallpossiblevaluesofthe
uncertainparameters.

426 18 RobustControlofaTwin-RotorAerodynamicSystem
Fig. 18.28 Frequency response of the noise-to-control loop (–) and inverse control weighting
function(--,-.)
Fig.18.29 Singularvalueplotoftheopen-loopsystem

18.8 NonlinearSystemSimulation 427
Fig.18.30 Transientresponsesoftheuncertainlinearizedclosed-loopsystem
Fig.18.31 Controlactionsoftheuncertainlinearizedclosed-loopsystem
18.8 NonlinearSystem Simulation
The nonlinear sampled-data closed-loop control system is simulated using the
Simulink® model TRAS_2dof_model.mdl. This model allows to simulate the

428 18 RobustControlofaTwin-RotorAerodynamicSystem
closed-loopsystembehaviorfordifferentreferencesanddisturbancesettingnoises
equaltozero.Themodelutilizesthenonlineardifferentialequations(18.1)–(18.6)
describingtheTwin-RotorAerodynamicSystem.
TheSimulink® modelTRAS_2dof_model.mdlisshowninFig.18.32.The
azimuthcontrolactionsareboundedintherange [−0.8,0.8] andthepitchcontrol
actions—intherange[−0.5,1].
The simulation of the nonlinear system for several references and disturbances
produces results that are close to the results obtained for the nominal linearized
model.
In Fig. 18.33 we show the transient responses to the reference of the nonlinear
systemwithμ-controller.
In Fig. 18.34 we show the control actions of the nonlinear system with μ-
controller.
18.9 ExperimentalResults
Theexperimentswiththecontrollerdesignedaredonebyusingthelaboratoryset-
up,showninFig.18.1alongwithaPCwithMATLAB®,ver.R2007b.Thegenera-
tionoftheCdrivingprogramisdonebyusingtheSimulinkCoder®.Forthisaima
Simulink®modeloftheclosed-loopsystemisusedwithbuilt-indriverforinterface
withtheplant.
The Simulink® model TRAS_2dof_exper.mdl of the twin-rotor aerody-
namicsystemthatisusedtogeneratethecontrolactionsisshowninFig.18.35.As
in the simulation of the nonlinear system the azimuth control actions are bounded
intheinterval[−0.8,0.8]andthepitchcontrolactionsintheinterval[−0.5,1].
Theexperimentallyobtainedtransientresponsesoftheclosed-loopsystem,con-
trolled in real time with the μ-controller designed, are shown in Fig. 18.36. The
comparisonwiththetransientresponsesofthelinearizedclosed-loopsystemgiven
in Fig. 18.31 shows a good coincidence between the theoretical and experimental
results.
The experimentally obtained control actions are shown in Fig. 18.37. Due to
the high level of the noises at the actuator inputs, the control actions are severely
contaminatedbyerrors.
To extract the true actuator inputs, the control signals are filtrated by using
appropriate first order Butterworth filter. The corresponding results are shown in
Fig.18.38andareclosetothetheoreticalresultsshowninFig.18.11.
18.10 Conclusions
TheexperiencegainedinthedesignandexperimentalimplementationoftheTwin-
Rotor Aerodynamic System controller allows one to derive the following conclu-
sions.

18.10 Conclusions 429
ledomnoitalumismetsysraenilnoN
23.81.giF

430 18 RobustControlofaTwin-RotorAerodynamicSystem
Fig.18.33 Transientresponsesofthenonlinearsystem
Fig.18.34 Controlactionsinthenonlinearsystem

18.10 Conclusions 431
lortnocemitlaerrofdesuledomnoitalumiS
53.81.giF

432 18 RobustControlofaTwin-RotorAerodynamicSystem
Fig.18.36 Experimentaltransientresponses
Fig.18.37 Experimentalcontrolactions(noisydata)

18.10 Conclusions 433
Fig.18.38 Experimentalcontrolactions(afterfiltration)
• The modern technologies for real-time control allow implementation of high-
ordercontrollers(inthegivencasen=24),whichhelptoachievebetterperfor-
manceandrobustnessoftheclosed-loopsystem.
• Rapidtuningofthecontrollerispossibleaswellasprototypingofalargenumber
ofcontrollers.
• Thestrongcontaminationoftheinputsignalsbynoisesleadstothenecessityto
suppressthehigh-frequencycomponentsofthecontrolactions.
• Due to the high level of noises in the control inputs the actuators may saturate,
whichmayleadtogenerationofauto-oscillationsintheclosed-loopsystem.
18.10.1 NotesandReferences
ThederivationoftheTwin-RotorAerodynamicSystemnonlinearmodelpresented
inthischapterfollows[165].
TheTwin-RotorAerodynamicSystempresentsasimplifiedmodelofahelicopter
in which the main rotor thrust and tail rotor thrust are controlled by changing the
correspondingpropellerspeed.(In therealhelicopterthisis donebychangingthe
collectiveandcyclicpitchanglesofthepropellerblades.)Thebehaviorofthissys-
temillustrateswellthedifficultiesarisingincontrolofstronglycoupledtwo-channel
nonlinear systems. Good disturbance attenuation and channel decoupling is possi-
ble to achieve by using H ∞-design or μ-synthesis based on the linearized plant

434 18 RobustControlofaTwin-RotorAerodynamicSystem
model.Anonlinear H ∞ disturbancerejectioncontrollerfortheTwin-RotorAero-
dynamicSystem,showingagoodperformanceforarangeofoperatingconditions,
isproposedin[104].
The control of unmanned rotorcraft vehicles is an area attracting intensive re-
search in the recent years. The reader interested in this subject may consult the
books[19,105,118,166].

Chapter 19
Robust Control of Self-balancing Two-Wheeled
Robot
Thischapterpresentsthedesignandexperimentationofa2-degree-of-freedomro-
bust controller for a self-balancing two-wheeled LEGO® Mindstorms NXT robot.
A 12th order discrete-time controller is designed by using the techniques of
μ-synthesis. The closed-loop control system achieves robust stability and robust
performanceinthepresenceoftwouncertainfrictioncoefficients.Theexperimen-
talresultsshowthattherobotpreservesstabilityintheverticalplanefordeviations
◦
greaterthan16 .
19.1 Introduction
Inrecentyears,therehasbeenagrowinginterestinresearchandeducationinim-
plementation of miniature robots, build on the basis of LEGO® Mindstorms NXT
developer kit (see for instance [10, 13, 144]). The control of such robots is done
by32-bitATMELARM7(AT91SAM7S256)microcontrollerwith48MHzspeed.
ThismicrocontrollerworksundertheoperationalsystemnxtOSEKandhas64KB
RAM, which makes it suitable for implementation of sufficiently complex control
laws.
The LEGO® Mindstorms NXT kit is used by Yorihisa Yamamoto to build the
self-balancing two-wheeled robot NXTway-GS [188], which implements a linear
quadratic regulator for robot digital control (stabilization of vertical body position
and achieving a reference position in the horizontal plane). The software product
EmbeddedCoderRobotNXTdevelopedbyTakashiChikamasa[22]isusedtoim-
plementadditionaltasksrelatedtotherobotcontrol(systeminitialization,avoiding
obstaclesandbatteryvoltagechecking).
ThegeneralviewoftheNXTway-GSrobotinself-balancingmodeisshownin
Fig.19.1.
The robot balancing is achieved by rotating the wheels in the appropriate di-
rection.ThecomputationofcontrolactionstobothDCdrivemotorsisrealizedin
single precision on the basis of signals from the micro-electromechanical (MEM)
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 435
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7_19,©Springer-VerlagLondon2013

436 19 RobustControlofSelf-balancingTwo-WheeledRobot
Fig.19.1 NXTway-GSrobot
inself-balancingmode
gyroscopicsensorwhichmeasurestheangularrate(and,afterintegration,thetiltan-
gle)oftherobotbodyintheverticalplaneandsignalsfromrotaryencoderswhich
measure the wheels rotation angles. The control of the DC motors is executed by
Pulse Width Modulated (PWM) signals. To avoid obstacles the robot is equipped
withanultrasonicsensor.
InthischapterwepresentthedesignofarobustcontrollerforNXTway-GSrobot
withtheaimtoimplementinmaximumdegreetheavailablesoftwareforreal-time
controlpresentedin[188].Sincetherobustcontrollersareofhigherorderthebasic
problem is to check the possibility to implement such controllers on the available
microcontrollerworkingwithsamplingfrequencyf =250Hzinthestabilization
s
loop. The results obtained show that the microcontroller under consideration im-
plements without difficulties a robust discrete controller of 12th order that allows
toimprovetheclosed-loopsystemperformance.Resultsfromthesimulationofthe
closed-loopsystemaswellasexperimentalresultsobtainedduringtherealimple-
mentationofthecontrollerdesignedaregiven.
19.2 UncertainModeloftheTwo-Wheeled Robot
Thenonlineardifferentialequationsdescribingtherobotmotionarederivedindetail
in[188]byusingtheLagrangemethod.Theseequationsarelinearizedanalytically
aroundthebalancepoint(equilibriumposition)resultinginastatespacedescription
offourthorderfortheverticalplanemotionandasecondorderdescriptionforthe

19.2 UncertainModeloftheTwo-WheeledRobot 437
rotationaroundverticalaxis.Inthefirstcase,theaverageangle θ ofleftandright
wheelrotationsandthebodytiltangleψ (measuredfromtheverticalposition),as
wellastheirderivatives(thecorrespondingangularrates),areusedascomponents
ofthestatevector.Inthesecondcase,statevariablesarethebodyyawangleφ and
itsderivative.Introducingthestateandcontrolactionvectorsas
⎡ ⎤
|     | θ   |     | (cid:2) | (cid:3) | (cid:2) (cid:3) |     |
| --- | --- | --- | ------- | ------- | --------------- | --- |
⎢ ⎥
|     | =⎢ ψ ⎥ |     | φ   |     | u    |        |
| --- | ------ | --- | --- | --- | ---- | ------ |
| x   | ⎦,     | x   | =   | ,   | u= l | (19.1) |
| 1   | ⎣ ˙    | 2   | ˙   |     |      |        |
|     | θ      |     | φ   |     | u r  |        |
˙
ψ
whereu ,u
l r arethecontrolactionstotheleftandrightwheelmotors,respectively,
theequationsofthelinearizedsystemareobtainedintheform
|     |     | x˙ =A | x +B | u   |     | (19.2) |
| --- | --- | ----- | ---- | --- | --- | ------ |
|     |     | 1     | 1 1  | 1   |     |        |
|     |     | x˙ =A | x +B | u   |     | (19.3) |
|     |     | 2     | 2 2  | 2   |     |        |
where the expressions for the elements of matrices A 1 , B 1 , A 2 , B 2 , as well as the
values of corresponding parameters, are given in [188]. We present only the ex-
pressionsformatricesA 1 andB 1 ,whichareusedlateroninthedesignofarobust
controller:
|     |     | ⎡   |       |         | ⎤   |        |
| --- | --- | --- | ----- | ------- | --- | ------ |
|     |     | 0   | 0     | 1 0     |     |        |
|     |     | ⎢   |       |         | ⎥   |        |
|     | =⎢  | 0   | 0     | 0 1     | ⎥   |        |
|     | A   | ⎣   |       |         | ⎦   | (19.4) |
|     | 1   | 0 a | a     | a       |     |        |
|     |     |     | 32    | 33 34   |     |        |
|     |     | 0 a | 42⎤ a | 43 a 44 |     |        |
⎡
|     |     | 0   | 0   |     |     |        |
| --- | --- | --- | --- | --- | --- | ------ |
|     |     | ⎢   | ⎥   |     |     |        |
|     | =⎢  | 0   | 0 ⎥ |     |     |        |
|     | B   |     |     |     |     | (19.5) |
|     | 1   | ⎣   | ⎦   |     |     |        |
|     |     | b 3 | b 3 |     |     |        |
|     |     | b   | b   |     |     |        |
|     |     | 4   | 4   |     |     |        |
where
|     | a =−gMLe |     | /det |     |     |     |
| --- | -------- | --- | ---- | --- | --- | --- |
|     | 32       | 12  | E    |     |     |     |
=gMLe
|     | a 42           | 11  | /det E   |       |     |        |
| --- | -------------- | --- | -------- | ----- | --- | ------ |
|     | a =−2(σe       |     | +βe      | )/det |     |        |
|     | 33             | 22  | 12       | E     |     |        |
|     | a =2(σe        | +βe | )/det    |       |     |        |
|     | 43             | 12  | 11       | E     |     |        |
|     | a =2β(e        | +e  | )/det    |       |     |        |
|     | 34             | 22  | 12       | E     |     |        |
|     | =−2β(e         |     | +e       |       |     |        |
|     | a 44           | 11  | 12 )/det | E     |     |        |
|     | =α(e           | +e  |          |       |     |        |
|     | b              |     | )/det    | E     |     |        |
|     | 3              | 22  | 12       |       |     |        |
|     | b =−α(e        | +e  | )/det    |       |     | (19.6) |
|     | 4              | 11  | 12       | E     |     |        |
|     | e =(2m+M)R2+2J |     |          | +2n2J |     |        |
|     | 11             |     |          | w     | m   |        |
e =MLR−2n2J
|     | 12     |     | m     |     |     |     |
| --- | ------ | --- | ----- | --- | --- | --- |
|     | =ML2+J |     | +2n2J |     |     |     |
|     | e 22   |     | ψ     | m   |     |     |

438 19 RobustControlofSelf-balancingTwo-WheeledRobot
Table19.1 Nominalparametersoftherobotmodel
| Parameter Description                          | Value | Units |
| ---------------------------------------------- | ----- | ----- |
| g gravityacceleration                          | 9.81  | m/s2  |
| m wheelmass                                    | 0.03  | kg    |
| R wheelradius                                  | 0.04  | m     |
| Jw wheelinertiamoment                          | mR2/2 | kgm2  |
| M bodymass                                     | 0.6   | kg    |
| W bodywidth                                    | 0.14  | m     |
| D bodydepth                                    | 0.04  | m     |
| H bodyheight                                   | 0.144 | m     |
| L distanceofthecenterofthemassfromthewheelaxle | H/2   | m     |
|                                                | ML2/3 | kgm2  |
Jψ bodypitchinertiamoment
| Jφ bodyyawinertiamoment | M(W2+D2)/12 | kgm2 |
| ----------------------- | ----------- | ---- |
1.0×10−5
| Jm DCmotorinertiamoment                           |        | kgm2    |
| ------------------------------------------------- | ------ | ------- |
| Rm DCmotorresistance                              | 6.69   | (cid:2) |
| Kb DCmotorbacke.m.f.constant                      | 0.468  | m       |
| Kt DCmotortorqueconstant                          | 0.317  | Nm/A    |
| n gearratio                                       | 1      |         |
| fm frictioncoefficientbetweenbodyandDCmotor       | 0.0022 |         |
| fw frictioncoefficientbetweenbodyandmotionsurface | 0.468  |         |
0.0001
=e −e2
det E 11 e 22
12
α=nK /R
t m
β=nK K /R +f
t b m m
=β+f
σ w
and the nominal values of the robot model parameters, in (19.6), are given in Ta-
ble19.1.
Itshouldbenotedthattherobotmodelparametersarenotdeterminedwithsuf-
ficientaccuracywhichmaycausedifficultiesincontrollerdesigns,andthusrobust
controllersarerequired.
According to (19.6), the basic parameter of robot model is the body mass M,
whichdeterminesalmostallmodelparameters.Sincethismassdependsonthepay-
loaditisreasonabletoassumeitasanuncertainparameteroftherobotmodel.Inthis
case,however,thematrixΔintheM–Δmodeloftheuncertainplantisa52×52
matrix,inwhichtheuncertaintyofM occurs52times.Thismakesthesynthesisof
robustcontrollerundersuchanassumptionalmostimpossibleinpractice.
Inthegivencaseasuncertainparametersweconsiderthefrictioncoefficientf
m
betweentherobotbodyandDCmotorandthefrictioncoefficient f betweenthe
w
robot wheels and motion surface. The introduction of these sample uncertainties

19.2 UncertainModeloftheTwo-WheeledRobot 439
Fig.19.2 Uncertainmodel
ofthetwo-wheeledrobot
allows to design easily a robust controller that ensures robust stability and robust
performanceoftheclosed-loopsystemwithrespecttothegivenuncertainty.Inpar-
ticular,weassumethatthecoefficient f isknownwith20%uncertaintyandthe
m
coefficientf with100%uncertainty.Theanalysisperformedlateronshowsthat
w
thecoefficientf hasmoresignificantinfluenceonthesystemdynamics.
m
Thetworealuncertainparametersf andf aredefinedintheprogrambyusing
m w
thefollowingcommandlines:
fm = ureal(’fm’,0.0022,’Mode’,’Range’,’Percentage’,20);
fw = ureal(’fw’,0.0001,’Mode’,’Range’,’Percentage’,100);
As a result, for the subsystem (19.2) one obtains an uncertain plant G with
unc
twoinputsandfouroutputs(Fig.19.2).
TheuncertainsystemmodeliscreatedbytheM-filemod_robot.m.
Thefrequencyresponse(inmagnitude)ofthenominalanduncertainplants(for
randomparametervaluesintherangesassumed)areshowninFig.19.3.Obviously,
Fig.19.3 Magnituderesponsesofthenominalanduncertainplant

440 19 RobustControlofSelf-balancingTwo-WheeledRobot
thevariationofthefrequencyresponseduetothevariationsinfrictioncoefficients
isrelativelysmall.
19.3 DesignofRobust Controller
The robot stabilization in upright position is a difficult task since the robot itself
presentsaninvertedpendulumwhosecontrolrequiresasufficientlyaccuratemodel.
Thedesignofadiscrete-timecontrollerforthesubsystem(19.2)wasdoneinitially
forthenominalplantmodelbyusingtheH ∞-design.However,duetotheinaccurate
plantmodelthecontrollerobtainedwas unabletostabilizetherobot,althoughthe
simulation results were positive. That is why the final design is done by using the
μ-synthesis, which allows to stabilize efficiently the robot in spite of the model
inaccuracy.Forbetterresultsitisappropriatetoimplementa2-degree-of-freedom
controller. The design is done for 250 Hz sampling frequency, which corresponds
tothefrequencyofthesignalattheoutputofgyrosensor.However,thefollowing
problemappearsduringthedesign.Theexperimentswithdifferentstandarddesign
configurationsshowthattheycannotensuregoodtrackingofthereferenceangleθ,
and hence the desired position in the motion plane. That is why apart from the
constraintsonthesensitivityfunctionweaddalsoaconstraintontheintegralofthe
errorinwheelsrotationangle.Thisallowstoensuresufficientaccuracyintracking
theangleθ.Theintegralcomponentisaddedalsointhesystemfeedback.
Thesubsystem(19.3)iscontrolledbyaPIDregulatorasdescribedin[188].
Theclosed-loopstructurewiththesensitivityfunctionrequirementontheoutput
variablesaswellastherequirementonthecontrolactionsisshowninFig.19.4.The
transfer function matrix W reflects the requirements on the system performance,
p
thematrixW reflectstherequirementsoncontrolactionsandthetransferfunctions
u
W and W reflects the influence of noises on the encoder and gyro measure-
n11 n22
ments,respectively.TheblockIntgintegratesthedifferencebetweenthereference
valueandtheoutputvalueoftheangleθ anditsoutputisusedinthesystemfeed-
backaswellasaninputtoweightingfunctionW .
p
Theinternalstructureoftheeight-input,16-outputopen-loopsystemof12thor-
der,whichissavedasthevariablesys_ic,isshowninFig.19.5.Thereferenceand
noisearesavedasthevariablesrefandnoise,respectively.Thecontrolactionis
savedasthevariablecontrol.Theinputtothecontrollerconsistsofthereference
˙ ˙
valuesofvariablesθ,ψ,θ,ψ aswellasoffourplantoutputsandintegratoroutput.
Theopen-loopsysteminterconnectionissetbytheM-fileolp_robot_2dof.m
implementingthefunctionsysic.
The schematic diagram showing the specific input/output arrangement of the
variablesys_ic,isshowninFig.19.6.
The closed-loop system block-diagram corresponding to the μ-synthesis prob-
lem is shown in Fig. 19.7. The matrix P is the transfer function matrix of the ex-
tendedopen-loopsystemshowninFig.19.5.

19.3 DesignofRobustController 441
Fig.19.4 Block-diagramoftheclosed-loopsystemwithperformancerequirements
Fig.19.5 Open-loopsysteminterconnection

442 19 RobustControlofSelf-balancingTwo-WheeledRobot
Fig.19.6 Schematicdiagramoftheopen-loopsysteminterconnection
Fig.19.7 Blockdiagramof
theclosed-loopsystem
Inthegivencasethefollowingweightingfunctionsarefoundas appropriatein
thecontrollerdesign.
Performanceweightingfunctions:
| W =diag(W | ,W ,W   | ,W ,W   | )   |
| --------- | ------- | ------- | --- |
| p         | p11 p22 | p33 p44 | p55 |
0.4s+1
W =0.95
| p11 5s+0.06 |     |     |     |
| ----------- | --- | --- | --- |
W =0.93
p22
W =0.15 (19.7)
p33
1.1s+1
W =0.22
| p44 1.0s+1 |     |     |     |
| ---------- | --- | --- | --- |
0.4s+1
W =1.8
| p11 5s+0.06 |     |     |     |
| ----------- | --- | --- | --- |

| 19.3 DesignofRobustController |     |     | 443 |
| ----------------------------- | --- | --- | --- |
Fig.19.8 Singularvalueplotofμ-controller
Controlactionweightingfunctions:
| W =diag(W | ,W      | )   |     |
| --------- | ------- | --- | --- |
| u         | u11 u22 |     |     |
1.2s+1
| W =0.02 |     |     | (19.8) |
| ------- | --- | --- | ------ |
u11 0.0024s+1
1.2s+1
W =0.02
u22 0.0024s+1
Noiseshapingfilters:
=diag(W
| W n | n11 ,W n22 | )   |     |
| --- | ---------- | --- | --- |
1.0s+2
=0.1
| W u11 |     |     | (19.9) |
| ----- | --- | --- | ------ |
0.01s+1
1.0s+2
=1.0
W u22
0.01s+1
The design of 2-degree-of-freedom controller for the subsystem (19.2) is done
dms_robot_2dof.m dksyn
| by the M-file | that implements | the function | from |
| ------------- | --------------- | ------------ | ---- |
RobustControlToolbox®3.Asaresultafterthreeiterationsoneobtainsa12thorder
controller,whichensuresaminimumvalueofthestructuredsingularvalueμequal
to 0.930. This shows that the closed-loop system achieves robust performance in
respecttothevariationofbothuncertaincoefficients.
The singular value plot (the magnitude response) of the controller obtained is
showninFig.19.8.Themaximumcontrollergainis41dB,whichensuresaccept-

444 19 RobustControlofSelf-balancingTwo-WheeledRobot
Fig.19.9 Magnituderesponseoftheuncertainclosed-loopsystem
ablecontrolactions.Theexperimentsshowthatlargercontrollergainsleadtoactu-
atorssaturationandinstabilityoftherealsystem.
19.4 Closed-Loop System Properties
After determining the controller, it is possible to compute several frequency re-
sponses and time responses of the closed-loop system that give profound infor-
mation about its properties. The frequency responses are obtained by the M-file
dfrs_robot_2dof.m.
InFig.19.9weshowafamilyoffrequencyresponsecharacteristicsoftheclosed-
loopwithinputandoutputthedesiredandactualangleθ,respectively,fordifferent
random values of the uncertain parameters in the prescribed range. It is seen that
the responses have acceptable peaks, the frequency band width (at level −3 dB)
beingabout2.13rad/s.Forthisbandwidthitispossibletoachievegoodtrackingof
typicalforthesystemunderconsiderationreferencesignals.
The magnitude responses of the output sensitivity function of the closed-loop
system along with the inverse performance function are shown in Fig. 19.10. It is
seen that the disturbance attenuationin the low frequencyrange is better than this
requiredbytheperformanceweightingfunction.
InFig.19.11weshowthemagnituderesponseoftheloopfromreferenceangle
θ totheintegralofthetrackingerrorofthisangle.Clearly,theprescribedfrequency

19.4 Closed-LoopSystemProperties 445
Fig.19.10 Outputsensitivityfunctionoftheclosed-loopsystem
Fig.19.11 Magnituderesponseoftheintegralcomponent

446 19 RobustControlofSelf-balancingTwo-WheeledRobot
Fig.19.12 Sensitivityofcontrolactiontoreferencesandnoises
domainconstraintsontheintegralerrorarefulfilled,theerrorattenuationinthelow
frequency range (where the reference spectrum lies) being 30 dB (i.e., more than
30times).Itispossibletoachieveevenbettersuppressionofthiserrorbutinsuch
a case the requirement for robust performance cannot be fulfilled (the value of μ
increases).
InFig.19.12weshowthemagnituderesponseoftheloopfromreferencesand
noises to the control actions (motor controls). It is seen that this response is lying
below the frequency response of the inverse control weighting filter, i.e., the pre-
scribedconstraintsonthecontrolsarefulfilled.Theseconstraintsarechosensothat
toavoidsaturationoftheactuatorswhichgeneratethePWMsignalstothemotors.
The robust stability and robust performance analysis of the closed-loop sys-
tem with discrete-time μ-controller is done by the file dmu_robot_2dof.m.
The robust stability analysis of the uncertain closed-loop system shows that the
upper bound on the structured singular value does not exceed the value of 0.063
(seeFig.19.13).Thismeansthatthesystemmayremainstableformuchlargerthan
theprescribeduncertaintyinthecorrespondingparameters.
Thisisnotthecaseinrespecttotherobustperformance.Itisseenfromthefre-
quencyresponsecharacteristicofthestructuredsingularvalue,showninFig.19.14,
that its maximum value is almost equal to 0.9304. This shows that there exists an
uncertainty which is only 1.075 times larger than the existing one, for which the
closed-loopsystemlosesrobustperformance.
In Fig. 19.15 we show the worst case magnitude response of the closed-loop
systemobtainedbythefilewcp_robot_2dof.mimplementingthefunctionwc-

19.4 Closed-LoopSystemProperties 447
Fig.19.13 Robuststabilityoftheclosed-loopsystem
Fig.19.14 Robustperformanceoftheclosed-loopsystem

448 19 RobustControlofSelf-balancingTwo-WheeledRobot
Fig.19.15 Worst-casemagnituderesponseoftheclosed-loopsystem
gain from Robust Control Toolbox®3. Due to the robust performance achieved,
theworstcaseresponseisslightlydifferentfromthenominalone.
The transient responses of the uncertain closed-loop system with discrete-time
μ-controllerisdonebythefilemcs_robot_2dof.m.
In Fig. 19.16 we show the reference angle θ, which is input to the controller
aswellasthetransientresponseoftheoutputangleθ.Multiplyingthesevariables
by the wheel radius R=0.04 m it is possible to determine the accuracy of robot
positioninginhorizontalplanemotion.
The body tilt angle, corresponding to the reference plane trajectory given in
Fig. 19.16, is shown in Fig. 19.17. Obviously,this angle is in the rangeof ±2 de-
grees.
The control action to the right motor, corresponding to the reference trajectory
giveninFig.19.16,isshowninFig.19.18.
The simulationof the nonlinear closed-loop system in the time domain is done
bytheprogramnxtway_gs_vr.mdlfrom[188],inwhichthecontroller,asim-
plementedbythefilenxtway_gs_controller.mdl,ismodifiedsuchthatto
use the μ-regulator designed (see for details the next section). The simulation of
the closed-loop system for zero reference and initial deviation of robot body from
the vertical plane shows that the robot successfully and quicklyreturns to the bal-
ance point. Since the simulation program nxtway_gs_vr.mdl implements the
linearizedplantmodel,itisnotpossibletoestablishthemaximumvalueofthever-
tical deviation for which the robot preserves stability. This is done experimentally
asdescribedinthenextsection.

19.4 Closed-LoopSystemProperties 449
Fig.19.16 Transientresponseoftheclosed-loopsystem
Fig.19.17 Transientresponseoftheclosed-loopsystem:bodytiltangle

450 19 RobustControlofSelf-balancingTwo-WheeledRobot
Fig.19.18 Rightmotorcontrolaction
19.5 ExperimentalResults
Thedesignedrobustregulatorofthetwo-wheeledrobotmotionisexperimentedin
practiceusingtheavailablesoftwareforautomaticgenerationofCcontrolcodeand
itsloadinginthedigitalrobotcontroller,aspresentedin[188].
For this aim we use the modified block-diagram of the controller model in
Simulink®,showninFig.19.19andsavedinthefilerobust_controller.The
12thorderμ-regulatorisrepresentedbythestatespaceblock“DiscreteController”
and the integration of the tracking error is done by the block “Discrete Integra-
tor”. This controller replaces the original linear quadratic state controller used in
the Simulink® file nxtway_gs_vr.mdl adopted from [188]. The generation of
thecontrolcodeisdonebyusingtheSimulinkCoder®.Duringtheexperimentsone
measuresthecontrolsignalstobothmotors,thepitchangleψ,thebatteryvoltage
and so on. The data transfer from robot to the personal computer is done by us-
ing the bluetooth-protocol.The file containing the results is loaded to MATLAB®
˙
whichallowstovisualizetheexperimentaldata.Sincetheangularrateψ measured
by the gyroscope and its integralare contaminatedby noises there is some bias in
thecomputedvalueofψ,whichisremovedbytheMATLAB®functiondtrend.
In Fig. 19.20 we show the results from one of the experiments performed. The
robotissubjecttotwodifferentdisturbanceforcescausingdeviationsfromthever-
tical position at approximately t =54 s and t =90 s. For the bigger deviation of
16.5 ◦ at t =54 s the regulator succeeds to stabilize the system and to return the

19.5 ExperimentalResults 451
noitatnemelpmirellortnoC
91.91.giF

452 19 RobustControlofSelf-balancingTwo-WheeledRobot
Fig.19.20 Transientresponsestodisturbanceforces
robottothebalancepoint.Therearesomeoscillationsinthesteady-statemodeof
order±2 ◦ thatareduetothedead-zoneinmotorgears.
The control signal to the right wheel for the same experiment is shown in
Fig. 19.21. In stabilization mode the control magnitude is between 40 % and
60 % from the maximum one which guarantees that the actuator saturation will
beavoided.Sincethecontrolatt=54sreaches100%itisjustifiedtoassumethat
◦
the deviation of 16.5 is the maximum allowable one for which the robot is kept
stable.
19.6 Conclusions
The experience gained in the design and experimental evaluation of the Two-
WheeledRobotSystemcontrollerallowstoderivethefollowingconclusions.
• Theinclusionofallpossibleuncertaintiesintheplantmodelmayleadtoavery
complicatedmodelthatmakesrobustcontrollerdesignimpossibleinpractice.In
manycasesitissufficienttotakeasmallnumberofuncertainparametersinorder
tofindarobustcontrollerthatensuresacceptableperformanceinpractice.
• TheLEGO® MindstormsNXTmicrocontrolleriscapabletorealizecomplicated
high-order control laws that may ensure stability of the closed-loop system for
sufficientlylargedeviationsfromtheequilibriumstate.

19.7 NotesandReferences 453
Fig.19.21 Controlactiontotherightwheelmotor
• Thepresenceofnonlinearitiesinthesystem,likedead-zoneorbacklash,mayde-
terioratesignificantlytheclosed-loopperformancesincethedesignoftherobust
controllerisbasedontheassumptionofalinearizedplantmodel.
• Thepresenceofbiasandnoisesinthegyroscopesignalmayrequireinclusionof
appropriate filters to determine sufficiently accurately estimates of the tilt angle
anditsderivative.
19.7 Notesand References
Differenttypesofwheeledrobotandtheirpropertiesaredescribedin[18].Thetwo-
wheeledNXTway-GSrobot,presentedinthischapter,isaninverted-pendulum-type
robot which should be stabilized around the vertical position by a control system.
Usually,suchrobotsareequippedwithtwoservodrivesforactuation,agyroscope
formeasuringangleandangularvelocityofpendulumbody,encodersformeasuring
thepositionofthewheelsandamicrocontrollerimplementingadiscretereal-time
stabilizationalgorithm.Sincethegyroscopemeasurementsaresubjecttobias,ran-
domwalkandnoise,thebodytiltangleisfrequentlyestimatedbyusingaKalman
filter. In some implementations it is appropriate to add an accelerometer or to use
InertialMeasurementUnitwithMEMsensorsinordertoeliminatethedrift.
The most popular commercial product, built on the idea of self balancing two-
wheeledrobot,istheSegway®PersonalTransporter(PT),producedbySegwayInc.,

454 19 RobustControlofSelf-balancingTwo-WheeledRobot
USA [152]. Some of the Segway® PTs have maximum speed of 20 km/h and can
travelasfaras38kmonasinglebatterycharge.
Different dynamic models and methods for real-time control of two-wheeled
robots may be found in [30, 85, 128], including self-tuning PID controllers [142],
robust[170]andfuzzycontrollers[186].Whenthesizeoftherobotsgetsbiggerand
mass gets smaller it is necessary to take into account the flexibility of robot body
[143]. Many issues connected to the development of real-time systems for mobile
robotcontrolareconsideredindepthintheexcellentbookofBräunl[16].

References
1. Abramovitch,D.Y.:Magneticandopticaldiskcontrol:parallelsandcontrasts.In:Proceed-
ings of the 2001 American Control Conference, Arlington, VA, June 2001, pp. 421–428
(2001)
2. Abramovitch,D.,Franklin,G.:Abriefhistoryofdiskdrivecontrol.IEEEControlSyst.Mag.
22,28–42(2002)
3. Abramovitch,D.,Franklin,G.:Diskdrivecontrol:theearlyyears.In:Proceedingsofthe
15thIFACCongress.SessionT-Th-M12,Barcelona,Spain,July2002,pp.1–12(2002).CD-
ROM
4. Abramovitch,D.,Wang,F.,Hurst,T.,Franklin,G.:Diskdrivepivotnonlinearitymodelling
PartI:Frequencydomain.In:Proceedingsofthe1994AmericanControlConference,Balti-
more,MD,June1994,pp.2600–2603(1994)
5. Abramovitch,D.,Hurst,T.,Henze,D.:AnoverviewofthePESParetomethodfordecom-
posing baseline noise sources in hard disk position error signals. IEEE Trans. Magn. 34,
17–23(1998)
6. Adamjan,V.M.,Arov,D.Z.,Krein,M.G.:AnalyticpropertiesofSchmidtpairsforaHankel
operatorandthegeneralizedSchur–Takagiproblem.Math.USSRSb.15,31–73(1971)
7. Al-Saggaf, U.M., Franklin, G.F.: An error bound for a discrete reduced order model of a
linearmultivariablesystem.IEEETrans.Autom.ControlAC-32,815–819(1987)
8. Anderson, B.D.O., Moore, J.B.: Linear Optimal Control. Prentice Hall, Englewood Cliffs
(1972)
9. Apkarian,P.,Gahinet,P.:Aconvexcharacterizationofgain-scheduledH∞controllers.IEEE
Trans.Autom.Control40,853–864(1995)
10. Azlan,N.,Zainudin,F.,Yusuf,H.,Toha,S.,Yusoff,S.,Osman,N.:Fuzzylogiccontrolled
miniatureLEGOrobotforundergraduatetrainingsystem.In:Proceedingsofthe2ndIEEE
Conference on Industrial Electronics and Applications, ICIEA 2007, Harbin, PRC, May
2007,pp.2184–2188(2007)
11. Balas,G.J.,Doyle,J.C.,Glover,K.,Packard,A.,Smith,R.:μ-AnalysisandSynthesisTool-
box:User’sGuide.MUSYN/TheMathworks,Natick(1995)
12. Balas,G.,Chiang,R.,Packard,A.,Safonov,M.:RobustControlToolbox®User’sGuide.The
Mathworks,Natick(2012).http://www.mathworks.com/help/pdf_doc/robust/robust_ug.pdf
13. Behrens,A.,Atorf,L.,Schwann,R.,Neumann,B.,Schnitzler,R.,Ballé,J.,Herold,T.,Telle,
A.,Noll,T.G., Hameyer,K.,Aach, T.: MATLAB meets LEGO Mindstorms—a freshman
introductioncourseintopracticalengineering.IEEETrans.Ed.53,306–317(2010)
14. Bernstein, D.S., Haddad, W.M.: LQG control with an H∞ performance bound: a Riccati
equationapproach.IEEETrans.Autom.ControlAC-34,293–305(1989)
15. Boyd,S.,ElGhaoui,L.,Feron,E.,Balakrishnan,V.:LinearMatrixInequalityinSystems
andControlTheory.SocietyforIndustrialandAppliedMathematics,Philadelphia(1994)
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 455
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7,©Springer-VerlagLondon2013

456 References
16. Bräunl, T.: Embedded Robotics: Mobile Robot Design and Applications with Embedded
Systems,3rdedn.Springer,Berlin(2008).ISBN978-3-540-70533-8
17. Callier,F.M.,Desoer,C.A.:LinearSystemTheory.Springer,NewYork(1991)
18. Campion,G.,Chung,W.:Wheeledrobots.In:Siciliano,B.,Khatib,O.(eds.)SpringerHand-
bookofRobotics,pp.391–410.Springer,Berlin(2008).Chap.17
19. Castillo, P., Lozano, R., Dzul, A.E.: Modelling and Control of Mini-Flying Machines.
Springer,London(2005).ISBN1852339578
20. Chen,B.M.,Lee,T.H.,Peng,K.,Venkataramanan,V.:HardDiskDriveServoSystems,2nd
edn.Springer,Berlin(2006)
21. Chew,K.K.,Tomizuka,M.:Digitalcontrolofrepetitiveerrorsindiskdrivesystems.IEEE
ControlSyst.Mag.10,16–20(1990)
22. Chikamasa, T.: Embedded Coder Robot NXT demo. http://www.mathworks.com/
matlabcentral/fileexchange/13399
23. Choi,B.W.,Gu,D.W.,Postlethwaite,I.:Low-orderH∞ sub-optimalcontrollers.IEEProc.
PartD,ControlTheoryAppl.141,243–248(1994)
24. deGaston,R.R.E.,Safonov,M.G.:Exactcalculationofthemultiloopstabilitymargin.IEEE
Trans.Autom.ControlAC-33,156–171(1988)
25. DeLuca,A.,Siciliano,B.:Trajectorycontrolofanon-linearone-linkflexiblearm.Int.J.
Control50,1699–1715(1989)
26. Desai,U.B.,Pal,D.:Atransformationapproachtostochasticmodelreduction.IEEETrans.
Autom.ControlAC-29,1097–1100(1984)
27. Desoer, C.A., Chan, W.S.: The feedback interconnection of lumped linear time-invariant
systems.J.FranklinInst.300,335–351(1975)
28. Desoer,C.A.,Vidyasagar,M.:FeedbackSystems:Input-OutputProperties.AcademicPress,
NewYork(1975)
29. Ding,J.,Tomizuka,M.,Numasato,H.:Designandrobustnessanalysisofdualstageservo
system.In:Proceedingsofthe2000AmericanControlConference,Chicago,Illinois,June
2000,pp.2605–2609(2000)
30. Do,K.D.,Seet,G.:Motioncontrolofatwo-wheeledmobilevehiclewithaninvertedpendu-
lum.J.Intell.Robot.Syst.60,577–605(2010)
31. Doyle,J.C.:Analysisoffeedbacksystemswithstructureduncertainties.IEEProc.PartD,
ControlTheoryAppl.129,242–250(1982)
32. Doyle,J.C.:Structureduncertaintyincontrolsystemdesign.In:Proceedingsofthe24IEEE
ConferenceonDecisionandControl,December1985,pp.260–265(1985)
33. Doyle,J.C.:Areviewofμ:forcasestudiesinrobustcontrol.In:Proceedingsof10thIFAC
WorldCongress,Munich,Germany,July1987,pp.395–402(1987)
34. Doyle,J.C.,Francis,B.A.,Tannenbaum,A.R.:FeedbackControlTheory.Macmillan,New
York(1992)
35. Du,C.,Zhang,J.,Guo,G.:VibrationanalysisandcontroldesigncomparisonofHDDsus-
ingfluidbearingandballbearingspindles.In:Proceedingsofthe2002AmericanControl
Conference,Anchorage,AK,May2002,pp.1378–1383(2002)
36. El Ghaoui, L., Niculescu, S.L. (eds.): Advances in Linear Matrix Inequality Methods in
Control:AdvancesinDesignandControl.SocietyforIndustrialandAppliedMathematics,
Philadelphia(2000)
37. Eltohamy,K.G.:Nonlinearoptimalcontrolofatripleinvertedpendulumwithsinglecontrol
input.Int.J.Control69,239–256(1998)
38. Enns,D.:Modelreductionforcontrolsystemsdesign.PhDthesis,DepartmentofAeronau-
ticsandAstronautics,StanfordUniversity,Stanford,CA(1984)
39. Enns, D.: Model reduction with balanced realizations: an error bound and a frequency
weightedgeneralization.In:Proceedingsofthe23rdIEEEConferenceonDecisionandCon-
trol,LasVegas,NV,pp.127–132(1984)
40. Evans,R.B.,Griesbach,J.S.,Messner,W.C.:Piezoelectricmicroactuatorfordualstagecon-
trol.IEEETrans.Magn.35,977–982(1999)

References 457
41. Fan,M.K.H.,Tits,A.L.:Characterizationandefficientcomputationofthestructuredsingular
value.IEEETrans.Autom.ControlAC-31,734–743(1986)
42. Fan,M.K.H.,Tits,A.L.,Doyle,J.C.:Robustnessinthepresenceofmixedparametricuncer-
taintyandunmodeleddynamics.IEEETrans.Autom.ControlAC-36,25–38(1991)
43. Fernando,K.V.,Nicholson,H.:Singularperturbationalmodelreductionofbalancedsystems.
IEEETrans.Autom.ControlAC-27,466–468(1982)
44. Fernando,K.V.,Nicholson,H.:Singularperturbationalapproximationfordiscrete-timesys-
tems.IEEETrans.Autom.ControlAC-28,240–242(1983)
45. Francis,B.A.:ACourseinH∞ ControlTheory.LectureNotesinControlandInformation
Sciences,vol.88.Springer,Berlin(1987)
46. Franklin,G.F.,Powell,J.D.,Workman,M.L.:DigitalControlofDynamicSystems,3rdedn.
Addison-Wesley,MenloPark(1998)
47. Furuta,K.,Kajiwara,K.,Kosuge,K.:Digitalcontrolofadoubleinvertedpendulumonan
inclinedrail.Int.J.Control32,907–924(1980)
48. Furuta,K.,Ochia,T.,Ono,N.:Attitudecontrolofatripleinvertedpendulum.Int.J.Control
39,1351–1365(1984)
49. Gahinet,P.,Apkarian,P.:AlinearmatrixinequalityapproachtoH∞control.Int.J.Robust
NonlinearControl4,421–448(1994)
50. Gahinet,P.,Nemirovski,A.,Laub,A.J.,Chilali,M.:LMIControlToolbox.TheMathWorks,
Natick(1995)
51. Garcia-Benitez,E.,Walkins,J.,Yurkovich,S.:Nonlinearcontrolwithaccelerationfeedback
foratwo-linkflexiblerobot.ControlEng.Pract.1,989–997(1993)
52. Ge,S.,Lee,T.,Zhu,G.:Improvingregulationofasingle-linkflexiblemanipulatorwithstrain
feedback.IEEETrans.Robot.Autom.14,179–185(1998)
53. Geniele,H.,Patel,R.,Khorasani,K.:End-pointcontrolofaflexible-linkmanipulator:theory
andexperiment.IEEETrans.ControlSyst.Technol.5,559–570(1997)
54. Ghanekar, M., Wang, D., Heppler, G.: Scaling laws for linear controllers of flexible link
manipulatorscharacterizedbynondimensionalgroups.IEEETrans.Robot.Autom.13,117–
127(1997)
55. Glover, K.: All optimal Hankel-norm approximations of linear multivariable systems and
theirl∞-errorbounds.Int.J.Control39,1115–1193(1984)
56. Glover, K.: Multiplicative approximation of linear multivariable systems with L∞ error
bounds. In: Proceedings of the 1986 American Control Conference, Minneapolis, MN,
pp.1705–1709(1986)
57. Glover,K.,Doyle,J.C.:State-spaceformulaefor allstabilizing controllersthat satisfyan
H∞normboundandrelationstorisksensitivity.Syst.ControlLett.11,167–172(1988)
58. Glover,K.,Jonckheere,E.A.:AcomparisonoftwoHankelnormmethodsforapproximating
spectra.In:Byrnes,C.I.,Lindquist,A.(eds.)Modelling,IdentificationandRobustControl.
North-Holland,Amsterdam(1986)
59. Goh,T.B.,Li,Z.,Chen,B.M.,Lee,T.H.,Huang,T.:Designandimplementationofahard
disk drive servo system using robust and perfect tracking approach. In: Proceedings of
the 38th IEEE Conference on Decision and Control, Phoenix, Arizona, December 1999,
pp.5247–5252(1999)
60. Green,M.:Balancedstochasticrealizations.LinearAlgebraAppl.98,211–247(1988)
61. Green,M.:Arelativeerrorboundforbalancedstochastictruncation.IEEETrans.Autom.
ControlAC-33,961–965(1988)
62. Green,M.,Limebeer,D.J.N.:LinearRobustControl.PrenticeHall,EnglewoodCliffs(1995)
63. Gu,D.W.,Tsai,M.C.,Postlethwaite,I.:State-spaceformulaefordiscrete-timeoptimization.
Int.J.Control49,1683–1723(1989)
64. Gu,D.W.,Postlethwaite,I.,Tsai,M.C.:H∞super-optimalsolutions.In:Leondes,C.T.(ed.)
Advances in Control and Dynamic Systems, vol. 51, pp. 183–246. Academic Press, San
Diego(1992)
65. Gu,D.W.,Choi,B.W.,Postlethwaite,I.:Low-orderstabilizingcontrollers.IEEETrans.Au-
tom.ControlAC-38,1713–1717(1993)

458 References
66. Gu,D.W.,Goh,S.J.,Fitzpatrick,T.,Postlethwaite,I.,Measor,N.:Applicationofanexpert
systemforrobustcontrollerdesign.In:Control’96,vol.2,pp.1004–1009(1996)
67. Gu, D.W., Petkov, P.H., Konstantinov, M.M.: Direct Formulae for the H∞ Sub-Optimal
CentralController.TechnicalReport1998-7,NiconetReport(1998).http://www.win.tue.nl/
niconet
68. Gu,D.W.,Petkov,P.H.,Konstantinov,M.M.:FormulaefordiscreteH∞loopshapingdesign
procedurecontrollers.In:Proceedingsofthe15thIFACWorldCongress,Paper276,Session
T-Mo-M15,Barcelona,Spain,July2002.CD-ROM
69. Guo,L.,Lee,H.S.,Hudson,A.,Chen,S.-H.:Acomprehensivetimedomainsimulationtool
forharddiskdriveTPIpredictionandmechanical/servoenhancement.IEEETrans.Magn.
35,879–884(1999)
70. Hammarling,S.:Numericalsolutionofthestablenon-negativedefiniteLyapunovequation.
IMAJ.Numer.Anal.2,303–323(1982)
71. Hara,S.,Hara,T.,Yi,L.,Tomizuka,M.:Twodegree-of-freedomcontrollersforharddisk
driveswithnovelreferencesignalgeneration.In:Proceedingsofthe1999AmericanControl
Conference,SanDiego,CA,June1999,pp.4116–4121(1999)
72. Helton, J.W.: Worst case analysis in the frequency domain: the H∞ approach to control.
IEEETrans.Autom.ControlAC-30,1154–1170(1985)
73. Helton,J.W.,Merino,O.:ClassicalControlUsingH∞ Methods.SocietyforIndustrialand
AppliedMathematics,Philadelphia(1998)
74. Hernandez,D.,Park,S.-S.,Horowitz,R.,Packard,A.K.:Dualstagetrack-followingservo
designforharddiskdrives.In:Proceedingsofthe1999AmericanControlConference,San
Diego,CA,June1999,pp.4116–4121(1999)
75. Hoyle,D.,Hyde,R.,Limebeer,D.J.N.:AnH∞approachtotwo-degree-of-freedomdesign.
In:Proceedingsofthe30thIEEEConferenceonDecisionandControl,Brighton,UK,De-
cember1991,pp.1581–1585(1991)
76. Hsu, C.S., Yu, X., Yeh, H.H., Banda, S.S.: H∞ compensator design with minimal order
observer. In: Proceedings of the 1993 American Control Conference, San Francisco, CA,
June1993
77. Huang,Y.,Mathur,P.,Messner,W.C.:Robustnessanalysisonahighbandwidthdiskdrive
servosystemwithaninstrumentedsuspension.In:Proceedingsofthe1999AmericanCon-
trolConference,SanDiego,CA,June1999,pp.3620–3624(1999)
78. InternationalSocietyNiconet.SLICOT:NumericalSubroutineLibraryforControlandSys-
temsTheory(2001).http://www.win.tue.nl/niconet
79. Ishikawa,J.,Yanagita,Y.,Hattori,T.,Hashimoto,M.:Headpositioningcontrolforlowsam-
plingratesystemsbasedontwodegree-of-freedomcontrol.IEEETrans.Magn.32,1787–
1792(1996)
80. Iwasaki,T.,Skelton,R.E.:AllloworderH∞ controllerswithcovarianceupperbound.In:
Proceedingsofthe1993AmericanControlConference,SanFrancisco,CA,June1993
81. Kajiwara,H.,Apkarian,P.,Gahinet,P.:LPVtechniquesforcontrolofaninvertedpendulum.
IEEEControlSyst.Mag.19,44–54(1999)
82. Karkoub,M.,Balas,G.,Tamma,K.,Donath,M.:Robustcontrolofflexiblemanipulatorsvia
μ-synthesis.ControlEng.Pract.8,725–734(2000)
83. Kempf, C., Messner, W., Tomizuka, M., Horovitz, R.: Comparison of four discrete-time
repetitivecontrolalgorithms.IEEEControlSyst.Mag.13,48–54(1993)
84. Kim, S.W., Anderson, B.D.O., Madievski, A.G.: Error bound for transfer function order
reduction using frequency weighted balanced truncation. Syst. Control Lett. 24, 183–192
(1995)
85. Kim,Y.,Kim,S.H.,Kwak,Y.K.:Dynamicanalysisofanonholonomictwo-wheeledinverted
pendulumrobot.J.Intell.Robot.Syst.44,25–46(2006)
86. Kobayashi,M.,Yamaguchi,T.,Horowitz,R.:Track-seekingcontrollerdesignfordual-stage
actuatorinmagneticdiskdrives.In:Proceedingsofthe2000AmericanControlConference,
Chicago,Illinois,June2000,pp.2610–2614(2000)

References 459
87. Kozierok,C.M.:The PCGuide:The ReferenceSectionon HardDiskDrives.June2012.
http://www.pcguide.com
88. Kundur,P.:PowerSystemStabilityandControl.McGraw-Hill,NewYork(1994).ISBN-13:
978-0070359581
89. Kung,S.:Anewlow-orderapproximationalgorithmviasingularvaluedecomposition.In:
Proceedingsofthe18thIEEEConferenceonDecisionandControl,Ft.Lauderdale,Florida,
December1979
90. Kung,S.,Lin,D.W.:OptimalHankelnormmodelreduction:multivariablesystems.IEEE
Trans.Autom.ControlAC-26,832–852(1981)
91. Larcombe, P.J.: On the generation and solution of the symbolic, open-loop characteristic
equationforadoubleinvertedpendulum.Int.J.Syst.Sci.24,2379–2390(1993)
92. Laub, A.J.: On computing balancing transformations. In: Proceedings of the Joint 1980
AmericanControlConference,SanFrancisco,CA,August1980,p.8(1980)
93. Laub,A.J.,Heath,M.T.,Paige,C.C.,Ward,R.C.:Computationofsystembalancingtrans-
formationsandotherapplicationsofsimultaneousdiagonalizationalgorithms.IEEETrans.
Autom.ControlAC-32,115–121(1987)
94. Lee,H.S.:Controlleroptimizationforminimumpositionerrorsignalsofharddiskdrives.
In: Proceedings of the 2000 American Control Conference, Chicago, Illinois, June 2000,
pp.3081–3085(2000)
95. Lee,S.-H.,Kang,H.J.,Chung,C.C.:Robustfastseekcontrolofaservotrackwriterusinga
statespacedisturbanceobserver.IEEETrans.ControlSyst.Technol.20,346–355(2012)
96. Li,Y.,Thang,B.,Shi,Z.,Lu,Y.:Experimentalstudyfortrajectorytrackingofatwo-link
flexiblemanipulators.Int.J.Syst.Sci.31,3–9(2000)
97. Limebeer,D.J.N.:Thespecificationandpurposeofacontrollerdesignstudy.In:Proceed-
ingsofthe30thIEEEConferenceonDecisionandControl,Brighton,UK,December1991,
pp.1579–1580(1991)
98. Limebeer, D.J.N., Kasenally, E.M., Perkins, J.D.: On the design of robust two degree of
freedomcontrollers.Automatica29,157–168(1993)
99. Lin, J.L.: Control system design for robust stability and robust performance. PhD thesis,
DepartmentofEngineering,UniversityofLeicester,Leicester,UK,May1992
100. Lin,C.-A.,Chiu,T.-Y.:Modelreductionviafrequencyweightedbalancedrealization.Con-
trolTheoryAdv.Technol.8,341–351(1992)
101. Lin,J.L.,Postlethwaite,I.,Gu,D.W.:μ–Kiteration:anewalgorithmforμ-synthesis.Auto-
matica29,219–244(1993)
102. Lindquist,A.,Picci,G.:Onthestochasticrealizationproblem.SIAMJ.ControlOptim.17,
365–389(1979)
103. Liu,Y.,Anderson,B.D.O.:Singularperturbationofbalancedsystems.Int.J.Control50(4),
1379–1405(1989)
104. López-Martinéz,M.,Vivas,C.,Ortega,M.G.:AmultivariablenonlinearH∞controllerfora
laboratoryhelicopter.In:Proceedingsofthe44thIEEEConferenceonDecisionandControl,
andtheEuropeanControlConference2005,Seville,Spain,December2005,pp.4065–4070
(2005)
105. Lozano, R. (ed.): Unmanned Aerial Vehicles Embedded Control. Wiley-ISTE, Chichester
(2010).ISBN978-1-84821-127-8
106. Lundström,P.,Skogestad,S.,Doyle,J.C.:Two-degree-of-freedomcontrollerdesignforan
ill-conditioneddistillationprocessusingμ-synthesis.IEEETrans.ControlSyst.Technol.7,
12–21(1999)
107. Lunz,J.:RobustMultivariableFeedbackControl.PrenticeHall,London(1989)
108. MacDuffee,C.C.:TheTheoryofMatrices.Chelsea,NewYork(1950)
109. Maciejowski,J.M.:MultivariableFeedbackDesign.Addison-Wesley, Wokingham (1989).
ISBN0-201-18243-2
110. Magee,D.P.:Optimalfilteringtoimproveperformanceinharddiskdrives:simulationre-
sults.In:Proceedingsofthe1999AmericanControlConference,SanDiego,CA,June1999,
pp.71–75(1999)

460 References
111. McFarlane,D.C.,Glover,K.:RobustControllerDesignUsingNormalizedCoprimeFactor
PlantDescriptions.LectureNotesinControlandInformationSciences,vol.138.Springer,
Berlin(1990)
112. McFarlane, D., Glover, K.: A loop shaping design procedure using H∞ synthesis. IEEE
Trans.Autom.ControlAC-37,749–769(1992)
113. Medrano-Cerda,G.A.:Robuststabilizationofatripleinvertedpendulum-cart.Int.J.Control
68,849–865(1997)
114. Medrano-Cerda,G.A.:Robustcomputercontrolofaninvertedpendulum.IEEEControlSyst.
Mag.19,58–67(1999)
115. Meier,Z.,Farwig,H.,Unbehauen,H.:Discretecomputercontrolofatriple-invertedpendu-
lum.Optim.ControlAppl.Methods11,157–171(1990)
116. Meirovitch,L.:ElementsofVibrationAnalysis.McGraw-Hill,NewYork(1986)
117. Messner,W.,Ehrlich,R.:Atutorialoncontrolsfordiskdrives.In:Proceedingsofthe2001
AmericanControlConference,Arlington,VA,June2001,pp.408–420(2001)
118. Mettler, B.: Identification Modeling and Characteristics of Miniature Rotorcraft. Kluwer
Academic,Boston(2003).ISBN1-4020-7228-7-096-1
119. Meyer,D.G.:Fractionalbalancedreduction:Modelreductionviafractionalrepresentation.
IEEETrans.Autom.ControlAC-35(3),1341–1345(1990)
120. Moore,B.C.:Principlecomponentanalysisinlinearsystems:controllability,observability,
andmodelreduction.IEEETrans.Autom.ControlAC-26,17–31(1981)
121. Morari,M.,Zafiriou,E.:RobustProcessControl.PrenticeHall,EnglewoodCliffs(1989)
122. Mori,S.,Nishihara,H.,Furuta,K.:Controlofanunstablemechanicalsystem.Controlof
pendulum.Int.J.Control23,673–692(1976)
123. Murad,G.:Robustmultivariablecontrolofindustrialproductionprocesses:adiscrete-time
multi-objectiveapproach.PhDthesis,DepartmentofEngineering,UniversityofLeicester,
Leicester,UK(1995)
124. Murad, G., Postlethwaite, I., Gu, D.-W., Whidborne, J.F.: Robust control of a glass tube
shapingprocess.In:ProceedingsoftheSecondEuropeanControlConference,Gröningen,
TheNetherlands,June–July1993,vol.4,pp.2350–2355(1993)
125. Murad,G.,Postlethwaite,I.,Gu,D.-W.,Samar,R.:OnthestructureofanH∞two-degree-
of-freedom internal model-based controller and its application to a glass tube production
process.In:ProceedingsoftheThirdEuropeanControlConference,Rome,September1995,
pp.595–600(1995)
126. Murad,G.,Gu,D.-W.,Postlethwaite,I.:Robustinternalmodelcontrolofabinarydistilla-
tioncolumn.In:IEEEInternationalConferenceonIndustrialTechnology,Shanghai,China,
December1996,pp.194–198(1996)
127. Murad,G.,Gu,D.-W.,Postlethwaite,I.:ADirectModelReductionApproachforDiscrete-
Time Non-Minimal State-Space Systems. Internal Report 94-23, University of Leicester,
Leicester,UK,September1994
128. Nawawi,S.W.,Ahmad,M.N.,Osman,J.H.S.:Real-timecontrolsystemforatwo-wheeled
invertedpendulummobilerobot.In:Fürstner,I.(ed.)AdvancedKnowledgeApplicationin
Practice,pp.299–312.Sciyo,Rijeka(2010).Chap.16
129. Nehari,Z.:Onboundedbilinearforms.Ann.Math.65,153–162(1957)
130. Nesterov, Y., Nemirovski, A.: Interior-Point Polynomial Algorithms in Convex Program-
ming. Studies in Applied Mathematics. Society for Industrial and Applied Mathematics,
Philadelphia(1993)
131. Ng, W.Y.: Interactive Multi-Objective Programming as a Framework for Computer-Aided
ControlSystemDesign.LectureNotesinControlandInformationSciences.Springer,Berlin
(1989)
132. Packard, A., Doyle, J.C.: The complex structured singular value. Automatica 29, 71–109
(1993)
133. Packard,A.,Pandey,P.:Continuitypropertiesofthereal/complexstructuredsingularvalue.
IEEETrans.Autom.ControlAC-38,415–428(1993)

References 461
134. Packard,A.,Fan,M.K.H.,Doyle,J.C.:Apowermethodforthestructuredsingularvalue.In:
Proceedingsofthe27thIEEEConferenceonDecisionandControl,Austin,Texas,December
1988,pp.2132–2137(1988)
135. Pao,L.Y.,Franklin,G.F.:Time-optimalcontrolofflexiblestructures.In:Proceedingsofthe
29thIEEEConferenceonDecisionandControl,Honolulu,HI,December1990,pp.2580–
2581(1990)
136. Pappas,T.,Laub,A.J.,Sandell,N.R.:Onthenumericalsolutionofthediscrete-timealgebraic
Riccatiequation.IEEETrans.Autom.ControlAC-25,631–641(1980)
137. Park,J.,Asada,H.:Dynamicanalysisofnoncollocatedflexiblearmsanddesignoftorque
transmissionmechanisms.J.Dyn.Syst.Meas.Control116,201–207(1994)
138. Pernebo, L., Silverman, L.M.: Model reduction via balanced state space representations.
IEEETrans.Autom.ControlAC-27,382–387(1982)
139. Postlethwaite, I., Lin, J.L., Gu, D.W.: Robust control of a high purity distillation column
usingμ–Kiteration.In:Proceedingsofthe30thIEEEConferenceonDecisionandControl,
Brighton,UK,December1991
140. Redheffer,R.M.:Remarksonthebasisofnetworktheory.J.Math.Phys.28,237–258(1950)
141. Redheffer,R.M.:Onacertainlinearfractionaltransformation.J.Math.Phys.39,269–286
(1960)
142. Ren,T.-J.,Chen,T.-C.,Chen,C.-J.:Motioncontrolforatwo-wheeledvehicleusingaself-
tuningPIDcontroller.ControlEng.Pract.16,365–375(2008)
143. Ruan,X.-g.,Ren,H.-g.,Li,X.-y.,Wang,Q.-y.:Dynamicmodelandanalysisoftheflexible
two-wheeled mobile robot. In: Xiong, C., Liu, H., Huang, Y., Xiong, Y. (eds.) Intelligent
RoboticsandApplications.LectureNotesinArtificialIntelligence,vol.5314,pp.933–942.
Springer,Berlin(2008)
144. RWTH-Mindstorms NXT Toolbox for MATLAB. Aachen, Germany (2008). http://www.
mindstorms.rwth-aachen.de
145. Safonov,M.G.:Stabilitymarginsofdiagonallyperturbedmultivariablefeedbacksystems.
IEEProc.PartD,ControlTheoryAppl.129,251–256(1982)
146. Safonov, M.G., Chiang, R.Y.: A Schur method for balanced-truncation model reduction.
IEEETrans.Autom.ControlAC-34,729–733(1989)
147. Safonov, M.G., Chiang, R.Y., Limebeer, D.J.N.: Hankel model reduction without
balancing—adescriptorapproach.In:Proceedingsofthe26thIEEEConferenceonDeci-
sionandControl,LosAngeles,CA,December1987
148. Safonov, M.G., Limebeer, D.J.N., Chiang, R.Y.: Simplifying the H∞ theory via loop-
shifting,matrix-pencilanddescriptorconcepts.Int.J.Control50,2467–2488(1989)
149. Samar,R.,Postlethwaite,I.,Gu,D.-W.:Modelreductionwithbalancedrealizations.Int.J.
Control62,33–64(1995)
150. Sánchez-Peña, R.S., Sznaier, M.: Robust Systems: Theory and Applications. Wiley, New
York(1998)
151. Sefton,J.,Glover,K.:Pole-zerocancellationsinthegeneralH∞problemwithreferenceto
atwoblockdesign.Syst.ControlLett.14,295–306(1990)
152. SegwayPersonalTransporters.Bedford,NH(2012).http://www.segway.com
153. Sezginer,R.S.,Overton,M.L.:ThelargestsingularvalueofeXAoe−X isconvexonconvex
setsofcommutingmatrices.IEEETrans.Autom.ControlAC-35,229–230(1990)
154. Skogestad,S.:Dynamicsandcontrolofdistillationcolumns:atutorialintroduction.Chem.
Eng.Res.Des.75,539–562(1997)
155. Skogestad,S.,Postlethwaite,I.:MultivariableFeedbackControl,2ndedn.Wiley,Chichester
(2005)
156. Skogestad,S.,Morari,M.,Doyle,J.C.:Robustcontrolofill-conditionedplants:highpurity
distillation.IEEETrans.Autom.Control33,1092–1105(1988)
157. Sreeram,V.,Anderson,B.D.O.,Madievski,A.G.:Newresultsonfrequencyweightedbal-
ancedreductiontechnique.In:Proceedingsofthe1995AmericanControlConference,Seat-
tle,WA,June1995,pp.4004–4009(1995)

462 References
158. Stoorvogel,A.A.:TheH∞ControlProblem:AStateSpaceApproach.PrenticeHall,Engle-
woodCliffs(1992)
159. Sutton,R.,Halikias,G.,Plummer,A.,Wilson,D.:ModellingandH∞ controlofasingle-
linkflexiblemanipulator.Proc.Inst.Mech.Eng.,PartI,J.Syst.ControlEng.213,85–104
(1999)
160. Tang,K.S.,Man,K.F.,Gu,D.-W.:StructuredgeneticalgorithmforrobustH∞controlsys-
temsdesign.IEEETrans.Ind.Electron.43(5),575–582(1996)
161. Tits,A.L.,Fan,M.K.H.:Onthesmall-μtheorem.Automatica31,1199–1201(1995)
162. Tombs,M.S.,Postlethwaite,I.:Truncatedbalancedrealizationofastablenon-minimalstate
spacesystem.Int.J.Control46(4),1319–1330(1987)
163. Tomizuka,M.:Dealingwithperiodicdisturbancesincontrolsofmechanicalsystems.Annu.
Rev.Control32,193–199(2008)
164. Tsacouridis,V.A.,Medrano-Cerda,G.A.:Discrete-timeH∞controlofatripleinvertedpen-
dulumwithsinglecontrolinput.IEEProc.,ControlTheoryAppl.146,567–577(1999)
165. Two Rotor Aerodynamical System. User’s Manual. Krakow, Poland (2006). http://www.
inteco.com.pl
166. Valavanis,K.P.(ed.):AdvancesinUnmannedAerialVehicles:StateoftheArtandtheRoad
toAutonomy.Springer,Berlin(2007).ISBN978-1-4020-6113-4
167. vanderLinden,G.-W.,Lambrechts,P.F.:H∞controlofanexperimentalinvertedpendulum
withdryfriction.IEEEControlSyst.Mag.19,44–50(1993)
168. Varga,A.:Balancingfreesquare-rootalgorithmforcomputingsingularperturbationapprox-
imations.In:Proceedingsofthe30thIEEEConferenceonDecisionandControl,Brighton,
UK,December1991,pp.1062–1065(1991)
169. Varga,A.:Onstochasticbalancingrelatedmodelreduction.In:Proceedingsofthe39thIEEE
Conference on Decision and Control, Sydney, Australia, December 2000, pp. 2385–2390
(2000)
170. Vermeiren,L.,Dequidt,A.,Guerra,T.M.,Rago-Tirmant,H.,Parent,M.:Modeling,control
andexperimentalverificationonatwo-wheeledvehiclewithfreeinclination:anurbantrans-
portationsystem.ControlEng.Pract.19,744–756(2011)
171. Vidyasagar,M.,Kimura,H.:Robustcontrollersforuncertainlinearmultivariablesystems.
Automatica22,85–94(1986)
172. Vidyasagar,M.,Schneider,H.,Francis,B.:Algebraicandtopologicalaspectsoffeedback
stabilization.IEEETrans.Autom.ControlAC-27,880–894(1982)
173. Walker,D.J.:Relationshipbetweenthreediscrete-timeH∞algebraicRiccatiequationsolu-
tions.Int.J.Control52,801–809(1990)
174. Wang,F.,Hurst,T.,Abramovitch,D.,Franklin,G.:Diskdrivepivotnonlinearitymodelling
PartII:Timedomain.In:Proceedingsofthe1994AmericanControlConference,Baltimore,
MD,June1994,pp.2604–2607(1994)
175. Wang,G.,Sreeram,V.,Liu,W.Q.:Anewfrequency-weightedbalancedtruncationmethod
andanerrorbound.IEEETrans.Autom.Control44,1734–1737(1999)
176. Whidborne,J.F.,Liu,G.P.:CriticalControlSystems.ResearchStudies,Taunton(1993)
177. Whidborne, J.F., Murad, G., Gu, D.-W., Postlethwaite, I.: Robust control of an unknown
plant—theIFAC93benchmark.Int.J.Control61,589–640(1994)
178. Whidborne, J.F., Postlethwaite, I., Gu, D.-W.: Robust controller design using H∞ loop-
shaping and the method of inequalities. IEEE Trans. Control Syst. Technol. 2, 455–461
(1994)
179. Whidborne, J.F., Gu, D.-W., Postlethwaite, I.: Algorithms for solving the method of
inequalities—acomparativestudy.In:Proceedingsofthe1995AmericanControlConfer-
ence,June1995
180. Whidborne, J.F., Postlethwaite, I., Gu, D.-W.: Multiobjective control system design—
amixedoptimizationapproach.In:Agarwal,R.P.(ed.)RecentTrendsinOptimizationThe-
oryandApplications.WorldScientificSeriesinApplicableAnalysis,vol.5,pp.467–482.
WorldScientific,Singapore(1995)

References 463
181. Whidborne,J.F.,Postlethwaite,I.,Gu,D.-W.:Robustcontrolofapapermachine.Control
Eng.Pract.3,1475–1478(1995)
182. White,W.N.,Fales,R.C.:Controlofadoubleinvertedpendulumwithhydraulicactuation:
acasestudy.In:Proceedingsofthe1999 AmericanControlConference,SanDiego,CA,
June1999,pp.495–499(1999)
183. White,M.T.,Tomizuka,M.,Smith,C.:Rejectionofdiskdrivevibrationandshockdistur-
banceswithadisturbanceobserver.In:Proceedingsofthe1999AmericanControlConfer-
ence,SanDiego,CA,June1999,pp.4127–4131(1999)
184. Willems, J.C.: Least stationary optimal control and the algebraic Riccati equation. IEEE
Trans.Autom.ControlAC-16(6),621–634(1971)
185. Willems, J.C.: Dissipative dynamical systems I: General theory. II: Linear systems with
quadraticsupplyrates.Arch.Ration.Mech.Anal.45,321–334(1972)
186. Wong,C.-C.,Wang,H.-Y.,Lim,S.-A.,Cheng,C.T.:FuzzycontrollerdesignedbyGAfor
two-wheeledmobilerobots.Int.J.FuzzySyst.9,22–30(2007)
187. Yamakita,M.,Hoshino,T.,Furuta,K.:Controlpracticeusingpendulum.In:Proceedingsof
the1999AmericanControlConference,SanDiego,CA,June1999,pp.490–494(1999)
188. Yamamoto, Y.: NXTway-GS (Self-Balancing Two-Wheeled Robot) controller design).
http://www.mathworks.com/matlabcentral/fileexchange/19147-nxtway-gs-self-balancing-
two-wheeled-robot-controller-design
189. Youla,D.C.,Jabr,H.A.,Lu,C.N.:Single-loopfeedbackstabilizationoflinearmultivariable
dynamicalplants.Automatica10,159–173(1974)
190. Youla,D.C.,Jabr,H.A.,Bongiorno,J.J.:ModernWeiner–Hopfdesignofoptimalcontrollers,
PartII:Themultivariablecase.IEEETrans.Autom.ControlAC-21,319–338(1976)
191. Zakian,V.,Al-Naib,U.:Designofdynamicalandcontrolsystemsbythemethodofinequal-
ities.Proc.IEEControlSci.120,1421–1427(1973)
192. Zames,G.:Feedbackandoptimalsensitivity:modelreferencetransformations,multiplica-
tive seminorms and approximate inverses. IEEE Trans. Autom. Control AC-26, 301–320
(1981)
193. Zames, G., Francis, B.A.: Feedback, minimax sensitivity, and optimal robustness. IEEE
Trans.Autom.ControlAC-28,585–600(1983)
194. Zeiger, H.P., McEwen, A.J.: Approximate linear realization of given dimension via Ho’s
algorithm.IEEETrans.Autom.ControlAC-19,153(1974)
195. Zhou, K., Doyle, J.C.: Essentials of Robust Control. Prentice Hall, Upper Saddle River
(1998)
196. Zhou,K.,Doyle,J.C.,Glover,K.:RobustandOptimalControl.PrenticeHall,UpperSaddle
River(1995)

Index
Symbols C
M–Δconfiguration,27 Centralcontroller,38
H∞gain-scheduledcontrollers,236 CentralH∞suboptimalcontroller,44
H∞loop-shapingdesignprocedure,53 Choleskyfactors,37
H∞mixedsensitivitydesign,179 Clampinghub,368
H∞suboptimalproblem,34 Closed-loopsystem,4
∞-normofasystem,11 Complementarysensitivityfunction,26
Condensor,329
μ–Kiterationmethod,70
Continuous-timesystem,5
μ-synthesis,204
Control-system,4
μ-synthesismethod,69
ControllabilityGramian,75
2-degree-of-freedomcontrolscheme,33
Coprimefactorization,7
Coprimetransferfunctions,8
A
Absolute-errorapproximationmethods,74 D
Additiveperturbation,13 D–Kiteration,69
Admissiblepoint,62 Descriptorsystems,221
Admissibleset,62 Diagonalscalingproblem,30
Affineparameter-dependentsystems,223 DiscreteLyapunovequations,80
AlgebraicRiccatiequation,35 Discrete-timeH∞case,45
Assumed-modesmethod,368 Discrete-timeRiccatiequation,46
Asymptoticstability,6 Discrete-timesystem,5
Asymptoticallystablesystem,94 Disksectors,250
Disktracks,250
Distillateproduct,328
B
Distillationcolumn,328
BalancedRealizationAlgorithm,75
Disturbance,26
Balancedresidualization,76
Disturbanceattenuation,26
BalancedStochasticTruncationmethod,84 dksyn,205
Balancedsystem,75 dtrend,450
Balancedtruncationmethod,75 DualizationLemma,103
Bezoutidentity,8
bode,127 E
bodemag,127 Elasticdeflection,368
Bottomproduct,329 EmbeddedCoderRobotNXT,435
Bounded-Input–Bounded-Outputstability,6 Embeddedservo,251
Bounded-reallemma,97 Errorsignal,26
D.-W.Guetal.,RobustControlDesignwithMATLAB®, 465
AdvancedTextbooksinControlandSignalProcessing,
DOI10.1007/978-1-4471-4682-7,©Springer-VerlagLondon2013

466 Index
F Inverseinputmultiplicativeperturbation,14
Fastpart,16 Inverseoutputmultiplicativeperturbation,15
feedback,125
Feedbacksystem,4 L
Feedforwardcompensator,54 Leftcoprimefactorperturbations,15
Feedforwardpath,33,53 LEGO®MindstormsNXT,435
Fictitiousoutputvector,17 lftdata,131,148
Finsler’sLemma,102 LinearFractionalTransformation
Flexible-linkmanipulator,368 lower,20
FractionalBalancedTruncationmethod,82 upper,19
FractionalSingularPerturbation LinearMatrixInequality(LMI),93
Approximationmethod,82 LMIfeasibleproblem,93
frd,107 Loop-ShapingDesign,175
Frequency-Weightedapproximationmethods, Loopshapingdesignprocedure,53
86 loopsens,116
Frequency-WeightedBalancedTruncation,88 loopsyn,175
Frequency-WeightedModuliTruncation Low-ordercontroller,73
Method,89
Lowerboundonμ,30
Frequency-WeightedSingularPerturbation
LPVsystems,221
Approximation,89
LQGmethods,3
Fulluncertaintyblocks,21
LTImodels,107
Furutapendulum,325
ltiss,223
ltisys,222
G
LV-configurationofthedistillationcolumn,
Gainscheduling,234
331
Generalizedplant,32
Lyapunovequations,75
gridureal,129
M
H
Mass–damper–springsystem,121,222
Hankelapproximationproblem,52
Measurementnoise,26
Hankelnorm,51,77
Methodofinequalities,61
Hankelsingularvalue,75
MIMOsystem,4
Hankel-normapproximation,77
Minimalsystem,5
HardDiskDrive,249
Mixedoptimizationloop-shapingdesign
HardDiskDriveservocontrolsystem,251
method,60
hinfgs,236
Mixedsensitivityproblem,31
hinfsyn,190
mixsyn,179
I Modelwithadditiveuncertainty,135
iconnect,132 Modelwithmultiplicativeuncertainty,138
Ill-conditionedproblem,35 Multivariablesystem,4
Ill-posedfeedbacksystem,48 mussv,148
impulse,127
Inducednorm,10 N
Input,4 Naturalfrequencies,370
Inputcomplementarysensitivitymatrix,116 Noiserejection,26
Inputlooptransfermatrix,116 Nominalmodel,13
Inputmultiplicativeperturbation,14 Nominalparametervalue,17
Inputsensitivitymatrix,116 Nominalperformance,67
Interconnectedsystem,32 Nominalstability,67
Interior-pointmethodsinconvexoptimization, Noncollocatedcontrollerstructure,378
94 Nonrepeatablerunout,251
Internalstability,6 Normofasignal,9
Inverseadditiveperturbation,14 Normalizedsystem,38

Index 467
NXTway-GS,435 S
nyquist,127 S-procedure,102
Scalaruncertaintyblocks,21
O Scaledmodel,331
ObservabilityGramian,75 Scalingmatrix
Open-loopsystem,4 input,331
Orderreduction,74 output,331
Orthonormalmatrix,78 SchurComplementFormula,98
Output,4 sconnect,241
Outputcomplementarysensitivitymatrix,116 Seekingmode,251
Outputlooptransfermatrix,116
Segway®PersonalTransporter,453
Outputmultiplicativeperturbation,14 Sensitivityfunction,26
Outputsensitivitymatrix,116 sigma,113
sinfo,223
Singularperturbationapproximation,76
P
Singularvaluedecomposition,40
Parameterbox,224
SISOsystem,4
Parameter-dependentsystems,221
slft,237
Parametricuncertainty,18
Sliders,250
pdlstab,229
Slowpart,16
pdsimul,232
Small-GainTheorem,23
Performancemargin,156
Spaceeigenfunction,369
Performancespecifications,26
Spectralradiusofamatrix,28
Platters,249
splot,223
Polytopicsystem,227
ss,107
Positionbursts,251
Stability,5
PositionErrorSignal,251
Stabilitymargin,28
Postcompensator,53
Stabilizingcontroller,23
Powersignal,10
step,127
Precompensator,53
Structuredsingularvalue,27
ProjectionLemma,101
Structureduncertainty,18
psys,225
Suboptimaldiscrete-timeloop-shaping
pvec,224
controller,56
sysic,133
Q
SYSTEMmatrix,222
Quadraticallystablesystem,229
Systemnorms,10
quadstab,229
T
R tf,107,125
Read/writeheads,249 Time-invariantsystem,5
Reboiler,329 Trackfollowingmode,251
Referenceinput,26 Trade-offbetweennominalperformanceand
Relative-errorapproximationmethods,84 robustnessoftheclosed-loopsystem,
Repeatablerunout,251 325
Resonantmodes,252 Transferfunctionmatrix,5
Rightcoprimefactorperturbations,15 Tripleinvertedpendulum,292
Robustcontrolsystem,23 Twin-RotorAerodynamicSystem(TRAS),
Robustperformance,67 401
Robuststability,67 Two-WheeledSelf-BalancingRobot,435
Robuststabilizationconditions,25
Robustlystablesystem,23 U
robustperf,157 ucomplex,130
robuststab,146 ucomplexm,130
Runout,251 ufrd,130

468 Index
ultidyn,134 W
umat,130 wcgain,165
Unmodeleddynamics,13,17,140 Weightingfunctions,26
Unstructureduncertainty,13 Worst-casegain,165
Upperboundonμ,30
ureal,123 X
usample,127 X-Riccatiequation,47
uss,124
usubs,127 Y
YoulaParameterizationTheorem,8
V
Vertexcontrollers,235 Z
Vertexsystem,227 Z-Riccatiequation,47
VoiceCoilMotor,250 zpk,107