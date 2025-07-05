# Manual

![Home Image](images/homeimage.jpg)

<style>
  img {
    border-radius: 15px;
    box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);
    display: block;
    margin: 0 auto;
  }
  h1 {
    text-align: center;
  }
  h2 {
    border-bottom: 2px solid #ff6600;
    padding-bottom: 4px;
    margin-top: 40px;
  }
  h3 {
    color: #ff6600;
    margin-top: 24px;
  }
  h4 {
    color: #ff9040;
    margin-top: 16px;
  }
</style>

## Table of Contents

1. [GUI](#gui)
   a. [Machine Interface](#machine-interface)
   b. [Companion App Interface](#companion-app-interface)
   c. [Example&nbsp;3-Input&nbsp;Overflow&nbsp;Configuration](#example-3-input-overflow-configuration)

2. [Setup & Working](#setup--working)

3. [Maintenance](#maintenance)
   a. [Change Air Filter](#change-air-filter)
   b. [Change Pump Pipe](#change-pump-pipe)
   c. [Calibration Pump](#calibration)
   d. [Refill Fluids](#refill-fluids)

## 1. GUI

### A. Machine Interface

#### Manual Mode

![Manual Mode](images/manualMode.jpg)
![Manual Mode](images/keyboard.jpg)

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

![Auto Mode](images/AutoMode.jpg)

In auto mode, the system operates automatically based on pre-set configurations.

### B. Companion App Interface

The Android companion app allows you to create, edit, and upload automation configurations over Bluetooth.

#### 1. Launch the App

![App Icon](images/ui0.png)

Tap the **ECIS Companion** icon to open the application.

#### 2. Connect via Bluetooth

![Device List](images/ui1.png)

1. Press the refresh button ⟳ in the top-right corner to scan for nearby devices.
2. Select **ECIS Control Panel** to establish a Bluetooth connection.

#### 3. Retrieve / Save Configurations

![Load Config](images/ui2.png)

• **Load Config** – downloads all configurations from the machine.
• **Reset to Default** – writes the factory-default configuration set back to the machine.
• **Save Config** – becomes active after you make changes; press it to upload the current configuration.

#### 4. Understand the Configuration Screen

![Config Steps](images/ui3.png)

The selected configuration is displayed as a vertical list of steps that will run sequentially during automation.

• **Clone** (copy icon) – duplicate the current configuration.
• **Delete** (trash icon) – remove the current configuration.
• Drag a step tile up or down to reorder it.

#### 5. Switch or Create a Configuration

![Config Dropdown](images/ui4.png)

Tap the dropdown to choose another configuration or select **+ New Config** to create one from scratch.

#### 6. Add a Step

![Add Step](images/ui5.png)

Press the green **+ Add Step** button and pick a step type from the dialog.

#### a.Motor Control Step

![Motor Step](images/ui6.png)

• Rename the step if desired.
• Choose **Nutrition**, **Sample**, or **Antibiotic** motor.
• Set **Flow Rate** and **Volume**; the action is always _Dispense_.

#### b.Valve State Step

![Valve Step](images/ui8.png)

Open or close the **Air-relief** and **Overflow** valves. Rename the step for clarity.

#### c.Sample Input Step

![Sample Input](images/ui9.png)

This interactive step pauses automation until the user confirms:

1. Intake the sample (volume field).
2. If bubbles are present, you may dispense and repeat until successful.
3. Tap **Next** to resume automation.

#### d.Wait Step

![Wait Step](images/ui91.png)

Enter the duration (seconds). Automation is paused for this period.

#### e.Buzzer Step

![Buzzer Step](images/ui92.png)

Set how long (seconds) the buzzer should sound; automation resumes afterwards.

### C. Example 3-Input Overflow Configuration

Below is a walkthrough of the default "3-Input-Air Relief" automation. Each image corresponds to a block in the configuration list and the step it performs on the machine.

| #   | Image                    | Purpose                                                                                                                                                                                |
| --- | ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | ![Step 1](images/e1.png) | **Close Valves** – Ensure both _Air-relief_ and _Overflow_ valves are closed before starting.</br>**Sample Input** – Operator intakes 180 µl of sample. Automation waits until you tap |
| 2   | ![Step 2](images/e2.png) | **Open Overflow Valve and Dispence Nutrition** 100ul vol. 100ul/min flow rate – Opens the overflow path so fluid direct pass through PDMS and exit                                     |
| 3   | ![Step 3](images/e3.png) | **Close all Valves and wait for given duration**                                                                                                                                       |
| 4   | ![Step 4](images/e4.png) | **Sample Air-relief** – Open air relief valve and pass 40ul sample to release air into air-relief pipe before entering electrodes.                                                     |
| 5   | ![Step 5](images/e5.png) | **Open Overflow Valve and Dispence Sample** 100ul vol. 100ul/min flow rate – Opens the overflow path so fluid direct pass through PDMS and exit                                        |
| 6   | ![Step 6](images/e6.png) | **Close all Valves and wait for given duration**                                                                                                                                       |
| 7   | ![Step 7](images/e7.png) | **Anti-biotic Air-relief** – Open air relief valve and pass 40ul Anti-biotic to release air into air-relief pipe before entering electrodes.                                           |
| 8   | ![Step 8](images/e8.png) | **Open Overflow Valve and Dispence Anti-biotic** 100ul vol. 100ul/min flow rate – Opens the overflow path so fluid direct pass through PDMS and exit                                   |
| 9   | ![Step 9](images/e9.png) | **Close All Valves & Buzzer** – Closes both valves and sounds the buzzer for 3 s, indicating the procedure is complete.                                                                |

Feel free to duplicate this configuration and tweak flow-rates, volumes, or timings to suit your protocol.

## 2. Setup & Working

### PDMS Setup

<div style="display: flex; justify-content:
space-between;">
    <img src="images/InsertPdms.png" alt="PDMS Setup"
    style="width: 48%;">
    <img src="images/pdmsSetup.png" alt="PDMS Setup"
    style="width: 48%;">
</div>
</br>
To prepare the PDMS module:

1. Place the PDMS slide on the holder and lock it in place.
2. Connect the Nutrition, Sample, and Antibiotic inlet tubes (recommended length: 35 cm each).
   </br>

   > Keep the Sample tube upright in the tube holder beside the Sample valve. This small pressure head prevents back-flow. if the tube drops below the PDMS level fluid can backflow on another pump dispensing.

3. For the Air-relief and Overflow lines, click **Unlock** on their respective valves, insert 35 cm tubes, and then click **Close** to secure them.

4. After plumbing is complete, switch to **Auto Mode**, choose the required configuration, and press **Start**.

## 3. Maintenance

### A. Change Air Filter

![Change Air Filter](images/chnageFilter.png)

Remove these screws and replace the filter here.

### B. Change Pump Pipe

| Step                                                                    | Image                                    |
| ----------------------------------------------------------------------- | ---------------------------------------- |
| 1. Remove these screws and open the panel.                              | ![Change Pipe 1](images/changePipe1.jpg) |
| 2. Remove this bolt by holding the back nut and remove this orange cap. | ![Change Pipe 2](images/changePipe2.jpg) |
| 3. Unlock the pump cap by pushing the lever left.                       | ![Change Pipe 3](images/changePipe3.jpg) |
| 4. Remove this screw.                                                   | ![Change Pipe 4](images/changePipe4.jpg) |
| 5. Remove this metal pipe holder.                                       | ![Change Pipe 5](images/changePipe5.jpg) |
| 6. Remove the pump pipe at this connector.                              | ![Change Pipe 6](images/changePipe6.jpg) |
| 7. Cut a new pipe to the same length (97mm).                            | ![Change Pipe 7](images/changePipe7.jpg) |
| 8. Replace the pipe and do the same in reverse to assemble.             | ![Change Pipe 8](images/changePipe8.jpg) |

### C. Calibration Pump

#### Change Valves

1. Click on ![Calibration Open](images/calibrationOpen.jpg)
2. Change the specified valves accordingly.
   ![Calibration Open](images/Callibration.jpg)

#### Procedure

1. Dispense a known amount of fluid (e.g., 100 µl) at a flow rate of 100 µl/min into a measuring container such as a pipette tip. Verify whether the dispensed volume is under- or over-delivered. the Sample pump must first intake, then dispense the reference volume for calibration. (Stay below 500 µl/min.)
2. Adjust the flow rate and volume calibration set points. If the dispensed volume is under the target, increase the set points; if it is higher, decrease the set points. The flow rate and volume set points will be the same number. The Nutrition and Antibiotic pumps share the same values because they use identical tubing.

### D. Refill Fluids

![Change Fluid](images/changeFluid.jpg)

To refill fluid containers:

1. Hold the container cap firmly and rotate the container clockwise to unlock it.
2. Remove the container and refill with the appropriate fluid.
3. Replace the container and rotate counterclockwise to lock it back in place.
4. Ensure the container is properly seated and secured before resuming operation.
