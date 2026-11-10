# EXPERIMENT: DESIGN OF A RECTANGULAR MICROSTRIP PATCH ANTENNA USING ANSYS HFSS

## 1. CREATING A NEW PROJECT

1. Open **ANSYS HFSS**.
2. Navigate to **Project → Insert HFSS Design**.

## 2. CREATING THE GROUND PLANE

1. Select **Create Rectangle** and rename `Rectangle1` as **Ground** in the Model Window.
2. Set the rectangle properties:
   - Size (X × Y): 60 × 60 mm
   - Centre: (−30, −30, 0) mm
3. Change the colour and click **Apply → OK**.

## 3. CREATING THE SUBSTRATE

1. Select **Create Box** and draw a box above the Ground plane with the same X and Y dimensions.
2. Rename `Box1` as **Substrate** in the Model Window.
3. Set the following properties:
   - Material: FR4_Epoxy
   - Size: 60 × 60 × 1.6 mm
   - Z-height: 1.6 mm
4. Change the colour and click **Apply → OK**.

## 4. CREATING THE PATCH

1. Select **Create Rectangle** and rename `Rectangle1` as **Patch**.
2. Set the rectangle properties:
   - Length (L): 29.4 mm
   - Width (W): 38 mm
   - Centre: (−29.4/2, −38/2, 1.6) mm
3. Change the colour and click **Apply → OK**.

## 5. CREATING THE FEEDLINE

1. Select **Create Rectangle** and draw a rectangle along the X-axis.
2. Rename `Rectangle1` as **Feed**.
3. Set the following properties:
   - Size (X × Y): 30 × 3 mm
   - Centre: (0, 3/2, 1.6) mm
4. Change the colour and click **Apply → OK**.

## 6. CREATING THE CUT

1. Draw a rectangle over the feed region and rename it as **Cut**.
2. Set the following properties:
   - Size: (−9.5, 5) mm
   - Position: (29.4/2, −5/2, 1.6) mm
3. Select **Patch** and **Cut** together.
4. Click **Subtract** to create the cut.

## 7. CONNECTING THE FEEDLINE AND PATCH

1. Select **Patch** and **Feed** together.
2. Click **Unite** to combine both structures into a single conducting element.

## 8. ASSIGNING THE EXCITATION PORT

1. Under the **Visibility** tab, change the working plane to **YZ**.
2. Select **Create Rectangle** and draw a rectangle on the substrate.
3. Rename it as **Port** and set its Y-dimension to 3 mm.
4. Select the Port and navigate to **Right-click → Assign Excitation → Lumped Port**.
5. Change the Integration Line to **New Line** and draw a line through the centre of the rectangle.
6. Verify that the Integration Line status changes to **Defined**.
7. Click **Next → Finish**.
8. Verify the port under the Project Manager Window.

## 9. CREATING THE RADIATION BOUNDARY

1. Select **Create Box** and draw a box surrounding the entire antenna structure.
2. Rename the box as **radiation**.
3. Set the following properties:
   - Medium: Air
   - Size (X × Y × Z): 80 × 80 × 40 mm
   - Centre/Position: (−40, −40, −20) mm
   - Transparency: 1
4. Apply the settings and click **OK**.

## 10. ASSIGNING BOUNDARY CONDITIONS

1. Select **Patch** and **Ground** together.
2. Right-click and navigate to **Assign Boundary → Perfect E**.
3. In the Model Window, right-click **Rad1** and select **Assign Boundary → Radiation**.

# RESULTS

## 11. SETTING UP THE SIMULATION

1. Navigate to **HFSS → Analysis Setup → Add Solution Setup → Advanced**.
2. Configure the solution parameters:
   - Solution Frequency: 2.4 GHz
   - Maximum Number of Passes: 20

3. Configure the frequency sweep:

| Parameter | Value |
|---|---|
| Sweep Type | Fast |
| Distribution | Linear Step |
| Start Frequency | 1 GHz |
| Stop Frequency | 3 GHz |
| Step Size | 0.02 GHz |

4. Click **OK** to save the settings.

## 12. VALIDATION AND SIMULATION

1. Navigate to **HFSS → Validation Check** to verify the design.
2. If validation is successful, select **HFSS → Analyze All**.
3. Wait for the simulation to complete.

## 13. PLOTTING THE S-PARAMETERS

1. In the Project Manager Window, right-click **Results**.
2. Select **Create Terminal Solution Data Report → Rectangular Plot**.
3. Set the following parameters:
   - Category: Terminal S Parameter
   - Function: dB
4. Click **New Report** to generate the S-parameter plot.
5. Right-click the plot and select **Marker → Add Marker**.
6. Place the marker at the dip in the curve to identify the resonant frequency.

## 14. CREATING THE FAR-FIELD SETUP

1. Navigate to **HFSS → Radiation → Insert Far Field Setup → Infinite Sphere**.
2. Set the angular ranges:

| Parameter | Start | Stop |
|---|---|---|
| Phi (φ) | 0° | 360° |
| Theta (θ) | 0° | 180° |

3. Apply the settings.

## 15. PLOTTING THE RADIATION PATTERN

1. Navigate to **Results → Create Far Field Report → 3D Polar Plot**.
2. Select the following options:
   - Quantity: rE
   - Function: dB
3. Click **New Report** to generate the radiation pattern.

## 16. VISUALIZING THE RADIATION PATTERN ON THE STRUCTURE

1. Navigate to **HFSS → Fields → Plot Fields → Radiation Field**.
2. In the window, enable the **Visible** option.
3. Click **Apply → Close**.
4. Observe the radiation pattern displayed on the antenna structure.
