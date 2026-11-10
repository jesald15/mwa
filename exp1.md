# EXPERIMENT 1: DESIGN AND SIMULATION OF A DIPOLE ANTENNA USING HFSS

## PART A: GEOMETRY

1. Go to **Project → Insert HFSS Design** and ensure that the **3D Modeler** is active.

2. Draw the first arm (**pole1**) using a cylinder with the following dimensions:
   - Height: 93.75 mm
   - Radius: 6 mm
   - Centre: (0, 0, 6) mm
   - Material: Copper

3. Create the second arm:
   - Right-click the cylinder and select **Edit → Duplicate → Around Axis**.
   - Set the axis to **Y** and the angle to **180°**.
   - Rename the duplicated cylinder as **pole2**.
   - Assign Copper as the material.

4. Set the visibility axis to **YZ** and draw a rectangle for the feed.
   - Position: (0, −3, −6) mm
   - Y Size: 6 mm
   - Z Size: 12 mm

5. Assign a **Modal Lumped Port** to the rectangle.
   - Name: `lumped_port`
   - Impedance: 73 Ω
   - Draw a new integration line through the centre.
   - Click **Next** and then **Finish**.

6. Draw a box around the antenna and configure it as the radiation boundary.
   - Rename the box as `radiation_boundary`.
   - Material: Vacuum
   - Transparency: 1
   - X Size: 200 mm
   - Y Size: 200 mm
   - Z Size: 400 mm
   - Position: (−100, −100, −200) mm

7. Assign the radiation boundary:
   - Right-click the box and select **Assign Boundary → Radiation**.
   - Click **OK**.
   - Verify that **Rad1** appears under Boundaries.

## PART B: SIMULATION SETUP

1. Navigate to **HFSS → Analysis Setup → Add Solution Setup → Advanced**.

2. Configure the solution setup:
   - Solution Frequency: 800 MHz
   - Maximum Number of Passes: 20
   - Click **OK**.

3. Right-click the solution setup and select **Add Frequency Sweep**.

4. Configure the frequency sweep:
   - Sweep Type: Fast
   - Distribution: Linear Count
   - Start Frequency: 600 MHz
   - Stop Frequency: 1000 MHz
   - Number of Points: 100

   **Note:** Earlier notes specify 400 MHz as the start frequency. Confirm the correct value with your lab instructions.

5. Click **OK** and verify that the frequency sweep appears under **Setup1**.

6. Run the simulation:
   - Navigate to **HFSS → Validation Check**.
   - If validation passes, click **Analyze All**.

## PART C: RESULTS

### 1. Far-Field Setup

1. Navigate to **HFSS → Radiation → Insert Far Field Setup → Infinite Sphere**.
2. Configure the angular ranges:
   - Phi: 0° to 360°
   - Theta: 0° to 360°

### 2. S-Parameter Plot

1. Navigate to **Results → Create Terminal Solution Data Report → Rectangular Plot**.
2. Set the following options:
   - Category: Terminal S Parameter
   - Function: dB
3. Click **New Report**.
4. Add a marker at the S-parameter dip.
5. Note the resonant frequency.

### 3. Resonant Frequency Adjustment

1. Check whether the resonant frequency is close to 800 MHz.
2. If the dip is not near 800 MHz:
   - Change the antenna size to 85.
   - Run **Analyze All** again.
   - Repeat the S-parameter plot and marker check.
3. Continue until the resonant frequency is close to 800 MHz.

### 4. Radiation Pattern

1. Navigate to **Results → Create Far Field Report → Radiation Pattern**.
2. Configure the following options:
   - Category: Gain
   - Quantity: GainTotal
   - Function: dB
3. Click **New Report** to generate the radiation pattern.

### 5. Field Visualization on the Antenna

1. Navigate to **HFSS → Fields → Plot Fields → Radiation Field**.
2. Enable the **Visible** option.
3. Click **Apply** and then **Close**.
