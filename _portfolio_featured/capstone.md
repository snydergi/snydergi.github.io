---
title: "Deployable Vehicle Solar Array"
author_profile: true
key: 4
toc: true
excerpt: "CAD, Prototyping, Testing"
header:
  teaser: /assets/images/projectImages/capstone/capstone.gif
classes: wide
---
## Sponsor
The project was sponsored by and done for Intelligent Systems (https://www.isehome.com/).

For project inquiries, contact Stephe Blansette (stephe@isehome.com)

## Featured Video
<iframe width="560" height="315" src="https://www.youtube.com/embed/HwJkGOtCSRk" title="SolarOrigami_RHIT_CapstoneDemo" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Project Overview
For Mechanical Engineering at Rose-Hulman Institute of Technology, a Capstone Project,
typically for an external client, is created as an opportunity to apply the past four years of
engineering education on a real-world problem. My team was tasked to create an apparatus to
support and deploy a vehicle-roof-mounted solar array in the shape of an origami square twist to
help Intelligent Systems, the project client, work toward expanding their solar product range.

<div style="text-align: center;">
  <img src="/assets/images/projectImages/capstone/squaretwist.png" alt="Square Twist" style="width: 50%; height: auto;">
</div>
<p style="text-align: center; font-style: italic; margin-top: 8px;">Origami Square Twist Pattern</p>

### Collaborators

This project was done in collaboration with the following students:

* Oscar Almeida (<almeido@rose-hulman.edu>)
* Max Jones (<jonescm@rose-hulman.edu>)
* Hannah Richardsen (<richarhc@rose-hulman.edu>)
* Rishon Shah (<shahrj@rose-hulman.edu>)

## Development

Throughout the year, many iterations of both the deployment mechanism, as well as the
supporting structure for the solar array were developed alongside the client to meet specifications
including weight, footprint, and actuation time. To approach the scale prototype deliverable, project
work was split in three converging modules: canopy, frame, and actuation.

### Canopy

The canopy is the portion of the project meant originally to be a stand-in for the actual solar
panels, which were ready for fabrication and already a preset size, but developed into a room for
experimentation to alter the method the panels were affixed to the frame. To maintain the origami
square twist with a three-dimensional structure, panel spacing was the key consideration. Using a
corrugated polypropylene sheet, the same material many yard signs are made from, an under-layer
for the panels was devised that would provide more rigidity than the previous canvas backing, as
well as provide slight assistance in actuation due to the elastic properties of the material when
folded. To successfully fold this canopy, sheet metal relief cutting techniques were applied to allow
for proper flexing and folding.

<div style="text-align: center;">
  <img src="/assets/images/projectImages/capstone/canopy.png" alt="Canopy" style="width: 50%; height: auto;">
</div>
<p style="text-align: center; font-style: italic; margin-top: 8px;">Polypropylene Canopy</p>

### Frame

The frame of the apparatus is used to provide a rigid base for the attachment of the final
product to the vehicle. The quarter-scale prototype utilizes an extruded t-slot aluminum frame. This
was used to allow for ease of changing frame layout and attachment points of the various
components. While the current frame on the prototype remains within the target weight
specification, at full-scale, for cost purposes the t-slot will be changed to an alternative such as
square aluminum tubing. With the mounting and connection points determined, any alternative to
the t-slot aluminum that maintains the base strength and allows for fastening, through machining or
welding, of components is a viable substitute for the current frame.

<div style="text-align: center;">
  <img src="/assets/images/projectImages/capstone/frame.png" alt="Frame" style="width: 50%; height: auto;">
</div>
<p style="text-align: center; font-style: italic; margin-top: 8px;">Frame Topview in CAD</p>

### Actuation

Overall, the system of the solar origami apparatus is centered around the use of a lead screw.
A lead screw is mounted within two rotary bearings that are attached to the frame. Threaded on the
lead screw between the two bearing blocks is a nut that connects to a plate. This plate connects to
the edge of the canopy to the drive system, as well as two telescoping supports that serve to remove load
from the lead screw. Turning the lead screw pushes the plate thus pushing the
canopy open and closed. By utilizing a screw to actuate the system, a motor or crank can be
attached to rotate the lead screw and operate the system which allows our design to be used
manually and or automatically to increase use flexibility.

<div>
  <div style="display: inline-block; width: 48%; margin-right: 2%;">
    <img src="/assets/images/projectImages/capstone/actuator.png" alt="Actuator Top View" style="width: 100%; height: auto;">
    <p style="text-align: center; font-style: italic; margin-top: 8px;">
      Actuator Top View in CAD
    </p>
  </div>
  <div style="display: inline-block; width: 48%;">
    <img src="/assets/images/projectImages/capstone/actuatorAndFrame.jpg" alt="Frame and Telescoping Supports" style="width: 100%; height: auto;">
    <p style="text-align: center; font-style: italic; margin-top: 8px;">
      Frame and Sliding Support Top View in CAD
    </p>
  </div>
</div>

## Project Outcomes

A table of final technical specifications, their rationale, evaluation protocol, and performance results
is below:

| Technical Specification                                                | Rationale                 | Evaluation Protocol                                                   | Performance Results       |
| :--------------------------------------------------------------------- | :-----------------------: | :-------------------------------------------------------------------: | :-----------------------: |
| Use square origami twist pattern                                       | Client Req.               | True/False                                                            | True                      | 
| Operate with one input (manual and automatic)                          | Client Req.               | True/False                                                            | True                      |
| Self-support weight in deployed state                                  | Client Req.               | True/False                                                            | True                      |
| 1/4 panels usable in stowed state                                      | Client Req.               | True/False                                                            | True                      |
| Withstand snow, hail, sleet, and rain without damage                   | Client Req., Benchmarking | Operate after water treatment testing, both when wet and after drying | True                      |
| Canopy and frame do not exceed 41.25 lbs. in total for 1/4 scale model | Road Safety Concerns      | Weight canopy and frame for 1/4 scale model                           | Total Weight = 17.73 lbs  |
| Deviates from roof angle no more than &plusmn;5 degrees (deployed)     | Client Req.               | Observe and measure deflection on mock car surface                    | Deflection = -2.49&deg;   |
| Single person operation                                                | Accessibility             | True/False                                                            | True                      |
| Actuates in under 60 seconds                                           | Reduce downtime           | Record time to deploy and retract                                     | Time to Open = 28.99 s    |
