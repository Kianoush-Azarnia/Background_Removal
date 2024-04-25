# Background Removal

## OVERVIEW

Inthisproject,wewanttodevelopanAIserviceintermsofimagebackgroundremoval.Thereis
asegmentationmodel(Tracer-B7)^1 whichisopensource. Inthisgithub project,abackground
removaltoolisintroduced.

## GOALS

1. ImplementanddevelopanAPIserviceinordertoremovethebackgroundofourimages.
2. Optimizethisservicefordifferent productionenvironments(GPU&CPU).

## SPECIFICATIONS

## Architecture

Design anarchitecture foryourservice.Throughthisprocedurepleasepay attentiontothe
followingpoints:

- Separateapiservicefromyourbackgroundremovalprocess.
- In your architecture, considerhow to scale your service interms of achieving high
    throughput(ProcessingImagesPerMinute).
- Inthisarchitectureyouarefreetouseanytechnologyandarchitecture.
- Afterdesigning,youhavetodocumentitvisuallyandexplainyourarchitecture **briefly**.

(^1) https://github.com/Ir1d/image-background-remove-tool


## API

DesignanddevelopanAPIrouteforgettinginputimages,detailsareinthefollowingitems.

- InputStructureofAPIroute:
    - picture_id: int
    - picture: str(base64)
- InputPictureisbase64,andyouhavetohandleitthroughyourprogram.
- Ifyouhaveenoughtime,writeatestforyourAPIfunction.
- WepreferFastAPIasyourframeworkfordevelopmentwithPydanticstructure.

## BackgroundRemovalDeepLearningModel

WeprovideapythonclasswhichisimplementedinordertoinferfromtheTracer-B7model.This
linkcontainsthemodelfilewhichyoucanuseintermsofrunningthismodel.Inmini-projectfiles
therearevariouspythonfiles,butyouhavetoonlyworkwithtracer_b7.py.IntheTracerB7class,
thereisan **infer** methodwhichgetsanimageasaninputandreturnsasegmentationmask.

Inyourprocesspictureprocedureyouhavetousethissegmentationmodel.

