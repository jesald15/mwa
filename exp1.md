# Experiment 1

## Part A: Geometry
Go to Project
Insert HFSS Design and make sure the 3D Modeler is active.
Draw the first arm (pole1) with a cylinder: height 93.75 mm, radius 6 mm, centre (0, 0, 6)
mm. Assign Copper.
Create the second arm: right-click the cylinder
Edit
Duplicate
Around Axis. Set the
axis to Y and the angle to 180°. Rename it pole2 and assign Copper.
Set the visibility axis to YZ and draw a rectangle for the feed. Set its position to (0, −3, −6)
mm, with Y = 6 mm and Z = 12 mm.
Assign a Modal Lumped Port to the rectangle. Name it lumped_port, set the impedance
to 73 Ω, draw a new integration line through the centre, then click Next and Finish.
Draw a box around the antenna and rename it radiation_boundary. Assign Vacuum and
set transparency to 1.
Set the box to X = 200 mm, Y = 200 mm, Z = 400 mm, positioned at (−100, −100, −200)
mm.
Right-click the box
Assign Boundary
Radiation, click OK, and check that Rad1 appears
under Boundaries.

## Part B: Simulation Setup
Go to HFSS
Analysis Setup
Add Solution Setup
Advanced. Set the solution frequency
to 800 MHz and the maximum passes to 20, then click OK.
Right-click the setup and choose Add Frequency Sweep:
Sweep type: Fast
Distribution: Linear Count
Start: 600 MHz (the earlier notes said 400 MHz, so check which value your lab expects)
Stop: 1000 MHz
Points: 100
Confirm that the sweep appears under Setup1.
Run HFSS
Validation Check. If it passes, click Analyze All.

## Part C: ResultsAdd the far-field setup: HFSS
Radiation
Insert Far Field Setup
Infinite Sphere. Set phi
and theta both from 0° to 360°.
Create the S-parameter plot: Results
Create Terminal Solution Data Report
Rectangular Plot. Set the category to Terminal S Parameter and the function to dB, then
click New Report.
Add a marker at the dip and note the resonant frequency.
If the dip is not near 800 MHz, change the size to 85, run Analyze All, and repeat the plot
and marker check until it is close.
Create the radiation pattern: Results
Create Far Field Report
Radiation Pattern. Set
the category to Gain, the quantity to GainTotal, and the function to dB, then click New
Report.
Show the field on the antenna: HFSS
then click Apply and Close.
Fields
Plot Fields
Radiation Field. Tick Visible,
