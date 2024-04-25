# Background Removal

## OVERVIEW

In this project, we want to develop an AI service in terms of image background removal.
There is a segmentation model (Tracer-B7)^1 which is open source. 
In this github project, a background removal tool is introduced.

## GOALS

1. Implemention of an API service in order to remove the background of our images.
2. Optimizing this service for different production environments (GPU&CPU).

## SPECIFICATIONS

## Architecture

We want to design anarchitecture for this service. Through this procedure we pay attention to the following points:

- Separatation of api service from the background removal process.
- In the architecture, we consider how to scale the service interms of achieving high throughput (Processing Images Per Minute).

(^1) https://github.com/Ir1d/image-background-remove-tool


## API

We design and develop an API route for getting input images, details are in the following items.

- Input Structure of API route:
    - picture_id: int
    - picture: str(base64)
- Input Picture is base64.
- We want to test our API function.
- We prefer Fast API as the framework for development with Pydantic structure.

## Background Removal Deep Learning Model

We provide a python class which is implemented in order to infer from the Tracer-B7model.
This link contains the model file which you can use in terms of running this model. 
In  tracer_b7.py. In the TracerB7 class, there is an **infer** method which gets an image as an input and returns a segmentation mask.

In the process picture procedure we need to use this segmentation model.

