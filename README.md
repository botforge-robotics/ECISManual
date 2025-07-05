<h1 align="center">Manual</h1>

<p align="center">
  <img src="images/homeimage.jpg" alt="Home Image" width="80%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" />
</p>

## Table of Contents

1. [GUI](#gui)

   - [Machine Interface](#machine-interface)
   - [Companion App Interface](#companion-app-interface)
   - [Example 3-Input Overflow Configuration](#example-3-input-overflow-configuration)

2. [Setup & Working](#setup--working)

3. [Maintenance](#maintenance)
   - [Change Air Filter](#change-air-filter)
   - [Change Pump Pipe](#change-pump-pipe)
   - [Calibration Pump](#calibration)
   - [Refill Fluids](#refill-fluids)

## 1. GUI

### A. Machine Interface

#### Manual Mode

<p align="center">
  <img src="images/manualMode.jpg" alt="Manual Mode" width="80%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" />
</p>
<p align="center">
  <img src="images/keyboard.jpg" alt="Manual Mode" width="80%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" />
</p>

In manual mode, there are two types of control:

1. **Motors**

   - Flow Rate (µl/min): Enter the desired flow rate (maximum 500 µl/min for best accuracy).
   - Volume (µl): Enter the target volume to dispense or intake.
   - Action Buttons: Use **Dispense** or **Intake** to start the motor.
   - Controls: **Pause**, **Resume**, or **Stop** the operation at any time.
   - Long-press **Dispense** or **Intake** to run the motor at 1000 µl/min while the button is held.
   - Valves of respected motor will automatically open and close on motor operation.
   - Motors Available:
     - Nutrition (1)
     - Sample (2)
     - Antibiotic (3)

2. **Valve Controls**
   - **Open** – allow flow.
   - **Close** – stop flow.
   - **Unlock** – temporarily release the clamp so you can insert or remove a tube, then **Close** to lock.
   - Valves:
     - Nutrition (1)
     - Sample (2)
     - Antibiotic (3)
     - Air-relief (4)
     - Overflow (5)

#### Auto Mode

<p align="center">
  <img src="images/AutoMode.jpg" alt="Auto Mode" width="80%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" />
</p>

In auto mode, the system operates automatically based on pre-set configurations.

### B. Companion App Interface

The Android companion app allows you to create, edit, and upload automation configurations over Bluetooth.

#### 1. Launch the App

<p align="center">
  <img src="images/ui0.png" alt="App Icon" width="60%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" />
</p>

Tap the **ECIS Companion** icon to open the application.

#### 2. Connect via Bluetooth

<p align="center">
  <img src="images/ui1.png" alt="Device List" width="60%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" />
</p>

1. Press the refresh button ⟳ in the top-right corner to scan for nearby devices.
2. Select **ECIS Control Panel** to establish a Bluetooth connection.

#### 3. Retrieve / Save Configurations

<p align="center">
  <img src="images/ui2.png" alt="Load Config" width="60%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" />
</p>

- **Load Config** – downloads all configurations from the machine.
- **Reset to Default** – writes the factory-default configuration set back to the machine.
- **Save Config** – becomes active after you make changes; press it to upload the current configuration.

#### 4. Understand the Configuration Screen

<p align="center">
  <img src="images/ui3.png" alt="Config Steps" width="60%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" />
</p>

The selected configuration is displayed as a vertical list of steps that will run sequentially during automation.

- **Clone** (copy icon) – duplicate the current configuration.
- **Delete** (trash icon) – remove the current configuration.
- Drag a step tile up or down to reorder it.

#### 5. Switch or Create a Configuration

<p align="center">
  <img src="images/ui4.png" alt="Config Dropdown" width="60%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" />
</p>

Tap the dropdown to choose another configuration or select **+ New Config** to create one from scratch.

#### 6. Add a Step

<p align="center">
  <img src="images/ui5.png" alt="Add Step" width="60%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" />
</p>

Press the green **+ Add Step** button and pick a step type from the dialog.

#### a.Motor Control Step

<p align="center">
  <img src="images/ui6.png" alt="Motor Step" width="60%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" />
</p>

- Rename the step if desired.
- Choose **Nutrition**, **Sample**, or **Antibiotic** motor.
- Set **Flow Rate** and **Volume**; the action is always _Dispense_.

#### b.Valve State Step

<p align="center">
  <img src="images/ui8.png" alt="Valve Step" width="60%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" />
</p>

Open or close the **Air-relief** and **Overflow** valves. Rename the step for clarity.

#### c.Sample Input Step

<p align="center">
  <img src="images/ui9.png" alt="Sample Input" width="60%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" />
</p>

This interactive step pauses automation until the user confirms:

1. Intake the sample (volume field).
2. If bubbles are present, you may dispense and repeat until successful.
3. Tap **Next** to resume automation.

#### d.Wait Step

<p align="center">
  <img src="images/ui91.png" alt="Wait Step" width="60%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" />
</p>

Enter the duration (seconds). Automation is paused for this period.

#### e.Buzzer Step

<p align="center">
  <img src="images/ui92.png" alt="Buzzer Step" width="60%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" />
</p>

Set how long (seconds) the buzzer should sound; automation resumes afterwards.

### C. Example 3-Input Overflow Configuration

Below is a walkthrough of the default "3-Input-Air Relief" automation. Each image corresponds to a block in the configuration list and the step it performs on the machine.

| #   | Image                                                                                                                           | Purpose                                                                                                                                                                               |
| --- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | <img src="images/e1.png" alt="Step 1" width="100%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" /> | **Close Valves** – Ensure both _Air-relief_ and _Overflow_ valves are closed before starting.<br>**Sample Input** – Operator intakes 180 µl of sample. Automation waits until you tap |
| 2   | <img src="images/e2.png" alt="Step 2" width="100%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" /> | **Open Overflow Valve and Dispence Nutrition** 100ul vol. 100ul/min flow rate – Opens the overflow path so fluid direct pass through PDMS and exit                                    |
| 3   | <img src="images/e3.png" alt="Step 3" width="100%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" /> | **Close all Valves and wait for given duration**                                                                                                                                      |
| 4   | <img src="images/e4.png" alt="Step 4" width="100%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" /> | **Sample Air-relief** – Open air relief valve and pass 40ul sample to release air into air-relief pipe before entering electrodes.                                                    |
| 5   | <img src="images/e5.png" alt="Step 5" width="100%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" /> | **Open Overflow Valve and Dispence Sample** 100ul vol. 100ul/min flow rate – Opens the overflow path so fluid direct pass through PDMS and exit                                       |
| 6   | <img src="images/e6.png" alt="Step 6" width="100%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" /> | **Close all Valves and wait for given duration**                                                                                                                                      |
| 7   | <img src="images/e7.png" alt="Step 7" width="100%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" /> | **Anti-biotic Air-relief** – Open air relief valve and pass 40ul Anti-biotic to release air into air-relief pipe before entering electrodes.                                          |
| 8   | <img src="images/e8.png" alt="Step 8" width="100%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" /> | **Open Overflow Valve and Dispence Anti-biotic** 100ul vol. 100ul/min flow rate – Opens the overflow path so fluid direct pass through PDMS and exit                                  |
| 9   | <img src="images/e9.png" alt="Step 9" width="100%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" /> | **Close All Valves & Buzzer** – Closes both valves and sounds the buzzer for 3 s, indicating the procedure is complete.                                                               |

Feel free to duplicate this configuration and tweak flow-rates, volumes, or timings to suit your protocol.

## 2. Setup & Working

### PDMS Setup

<div style="display: flex; flex-wrap: wrap; gap: 15px; justify-content: center; margin: 25px 0; max-width: 800px; margin-left: auto; margin-right: auto;">
<img src="images/InsertPdms.png" alt="PDMS Setup" width="48%" align="left">
<img src="images/pdmsSetup.png" alt="PDMS Setup" width="48%" align="right">
</div>
<br clear="all">

To prepare the PDMS module:

1. Place the PDMS slide on the holder and lock it in place.
2. Connect the Nutrition, Sample, and Antibiotic inlet tubes (recommended length: 35 cm each).

   > Keep the Sample tube upright in the tube holder beside the Sample valve. This small pressure head prevents back-flow. if the tube drops below the PDMS level fluid can backflow on another pump dispensing.

3. For the Air-relief and Overflow lines, click **Unlock** on their respective valves, insert 35 cm tubes, and then click **Close** to secure them.

4. After plumbing is complete, switch to **Auto Mode**, choose the required configuration, and press **Start**.

## 3. Maintenance

### A. Change Air Filter

<p align="center">
  <img src="images/chnageFilter.png" alt="Change Air Filter" width="80%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" />
</p>

Remove these screws and replace the filter here.

### B. Change Pump Pipe

| Step                                                                    | Image                                                                                                                                           |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| 1. Remove these screws and open the panel.                              | <img src="images/changePipe1.jpg" alt="Change Pipe 1" width="100%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" /> |
| 2. Remove this bolt by holding the back nut and remove this orange cap. | <img src="images/changePipe2.jpg" alt="Change Pipe 2" width="100%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" /> |
| 3. Unlock the pump cap by pushing the lever left.                       | <img src="images/changePipe3.jpg" alt="Change Pipe 3" width="100%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" /> |
| 4. Remove this screw.                                                   | <img src="images/changePipe4.jpg" alt="Change Pipe 4" width="100%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" /> |
| 5. Remove this metal pipe holder.                                       | <img src="images/changePipe5.jpg" alt="Change Pipe 5" width="100%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" /> |
| 6. Remove the pump pipe at this connector.                              | <img src="images/changePipe6.jpg" alt="Change Pipe 6" width="100%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" /> |
| 7. Cut a new pipe to the same length (97mm).                            | <img src="images/changePipe7.jpg" alt="Change Pipe 7" width="100%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" /> |
| 8. Replace the pipe and do the same in reverse to assemble.             | <img src="images/changePipe8.jpg" alt="Change Pipe 8" width="100%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" /> |

### C. Calibration Pump

#### Change Valves

1. Click on <span style="vertical-align: middle;"><img src="images/calibrationOpen.jpg" alt="Calibration Open" width="40%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5); vertical-align: middle;" /></span>
2. Change the specified valves accordingly.
   <p align="center">
     <img src="images/Callibration.jpg" alt="Calibration Open" width="80%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" />
   </p>

#### Procedure

1. Dispense a known amount of fluid (e.g., 100 µl) at a flow rate of 100 µl/min into a measuring container such as a pipette tip. Verify whether the dispensed volume is under- or over-delivered. the Sample pump must first intake, then dispense the reference volume for calibration. (Stay below 500 µl/min.)
2. Adjust the flow rate and volume calibration set points. If the dispensed volume is under the target, increase the set points; if it is higher, decrease the set points. The flow rate and volume set points will be the same number. The Nutrition and Antibiotic pumps share the same values because they use identical tubing.

### D. Refill Fluids

<p align="center">
  <img src="images/changeFluid.jpg" alt="Change Fluid" width="80%" style="border-radius: 15px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);" />
</p>

To refill fluid containers:

1. Hold the container cap firmly and rotate the container clockwise to unlock it.
2. Remove the container and refill with the appropriate fluid.
3. Replace the container and rotate counterclockwise to lock it back in place.
4. Ensure the container is properly seated and secured before resuming operation.
