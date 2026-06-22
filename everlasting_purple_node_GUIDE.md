## Tools
- Glass blowing torch and fusion kit
- High-vacuum pump with argon backfill station
- Spot welder for platinum wire clips
- Thermal epoxy and applicator
- Ceramic adhesive applicator
- M2.5 and M3 hex drivers
- Soldering station with high-temperature solder
- Precision tweezers

## Assumptions
- Experience with high-voltage RF resonance systems
- Access to a controlled atmosphere glass fusion environment
- Knowledge of vacuum tube evacuation and degassing procedures
- Clean room or dust-free environment for globe assembly

## 1. Fabrication
### 1.1 Prepare quartz stem rod and mount getters
**Secure the non-evaporable getters to the quartz stem rod using platinum wire clips.**
1. Clean the 60mm Fused Quartz Internal Lead Shield with isopropyl alcohol to remove skin oils.
2. Position two Hydrogen/Oxygen Getters symmetrically near the top of the Quartz Stem Rod.
3. Wrap a 0.2mm Platinum wire clip around the first getter and the quartz rod twice.
4. Twist the wire ends tightly with needle-nose pliers to ensure zero mechanical play.
5. Repeat the clipping process for the second getter 180 degrees offset from the first.
6. Trim excess wire and tuck the sharp ends flush against the getter surface.
  > Tip: Avoid touching the getter material with bare hands, as finger oils can cause outgassing when the node reaches high plasma operating temperatures.

### 1.2 Bond zirconia lattice to central quartz support
**Adhere the zirconia lattice structure to the central quartz internal lead shield.**
1. Clean the Internal Lead Shield surface with isopropyl alcohol to remove skin oils
2. Apply a thin bead of high-temperature ceramic adhesive to the 60mm quartz rod
3. Center the 4x Volume Zirconia Lattice vertically over the adhesive bead
4. Rotate the lattice slightly to ensure even coverage of the bonding agent
5. Cure the assembly in a kiln at 150°C for 2 hours to set
  > Tip: Ensure the lattice is perfectly concentric with the quartz rod to prevent uneven thermal stress during high-frequency operation.

### 1.3 Machine chassis mounting holes for ferrite and supercaps
**Drill and tap mounting holes in the Extruded Finned Chassis for power components.**
1. Mark mounting locations for the E65 Ferrite Core Transformer on the chassis base
2. Drill two 2.5mm holes for the transformer and tap with an M3 thread
3. Drill four 2.05mm pilot holes at the corners for the Integrated LCP Base attachment
4. Tap the LCP base pilot holes using an M2.5 tap for the self-tapping screws
5. Clean the chassis of aluminum shavings and deburr all drilled hole edges
  > Tip: Use a drop of cutting oil when tapping the aluminum chassis to prevent the tap from binding or snapping.

### 1.4 Apply capacitive mesh sleeve to interior globe surface
**Line the globe interior with capacitive mesh and secure with high-temp tape.**
1. Clean the interior surface of the Dycenian Frosted Globe with anhydrous alcohol
2. Roll the Capacitive Return Mesh into a cylinder slightly smaller than the globe opening
3. Insert the mesh into the globe and allow it to spring outward against the glass
4. Apply small tabs of high-temp kapton tape to the top and bottom mesh edges
5. Verify the RF_RETURN lead wire is accessible for future connection to the transformer
  > Tip: Ensure the mesh is perfectly flush against the glass to avoid corona discharge and uneven purple light distribution.

### 1.5 Integrate GTM ferrules into glass globe base
**Fuse GTM Ferrules into the Dycenian Frosted Globe base for vacuum-tight electrical feedthroughs.**
1. Heat the neck of the Dycenian Frosted Globe using a precision hydrogen-oxygen torch
2. Position the GTM Ferrules into the softened glass at the specified entry points
3. Slowly rotate the globe to ensure a uniform glass-to-metal hermetic seal
4. Anneal the fusion zone in a kiln at 520°C to relieve internal stresses
5. Perform a vacuum leak test on the IN pin interfaces once the glass is cool
  > Tip: Ensure the ferrules are expansion-matched to the borosilicate glass to prevent cracking during thermal cycling of the 2.5kV field.

## 2. Wiring
### 2.1 Solder Qi module to supercapacitor module
**Solder the Qi Wireless Module to the 50F Supercapacitor Module.**
1. Tin the VCC and GND pads on the Qi Wireless Module
2. Cut two 50mm lengths of 22AWG silicone-insulated wire and strip the ends
3. Solder the wire from Qi Wireless Module VCC to Supercapacitor POS
4. Solder the wire from Qi Wireless Module GND to Supercapacitor NEG
5. Check for a 5V DC potential across the supercapacitor terminals when powered
  > Tip: Ensure the supercapacitor is fully discharged before soldering to prevent accidental arcing or damage to the Qi module.

### 2.2 Connect supercapacitor to 48V boost converter input
**Connect the 50F Supercapacitor Module to the 48V 300W Boost Converter input terminals.**
1. Strip 8mm of insulation from 16AWG high-current silicone power leads
2. Solder the positive lead from Supercapacitor POS to Boost Converter VIN+
3. Solder the negative lead from Supercapacitor NEG to Boost Converter VIN-
4. Slide 4mm heat shrink over terminals and shrink at 250°C for insulation
5. Perform a multimeter continuity check between modules to ensure low-resistance bonding
  > Tip: Verify the supercapacitor is fully discharged before soldering to prevent high-current arcing that can damage the boost converter's input MOSFETs.

### 2.3 Wire GaN Power IC to boost converter and bias resistor
**Wire the GaN Power IC to the 48V boost converter and gate bias resistor.**
1. Solder a 14AWG silicone wire from Boost Converter VOUT极 to GaN Power IC VIN
2. Connect a 24AWG jumper between GaN Power IC GATE_IN and Bias Resistor P1
3. Solder a wire from Bias Resistor P2 to the GaN Power IC GND pin
4. Run a common ground wire from GaN Power IC GND to the Boost Converter VIN-
5. Check for 48V DC isolation between high-side and logic-side traces using a multimeter
  > Tip: Ensure the GaN IC is already mounted to the heat sink with thermal epoxy before soldering to prevent overheating the silicon junction.

### 2.4 Configure resonant tank with capacitor and transformer primary
**Wire the high-frequency resonant tank circuit between the transformer and GaN IC.**
1. Solder Resonant Tank Capacitor P1 directly to E65 Ferrite Core Transformer PRI_A
2. Solder Resonant Tank Capacitor P2 directly to E65 Ferrite Core Transformer PRI_B
3. Connect GaN Power IC VOUT to E65 Ferrite Core Transformer PRI_A
4. Run 48V DC from the Boost Converter to the Transformer PRI_TAP center tap
5. Verify electrical continuity across the L-C resonant loop with a multimeter
  > Tip: Use short, heavy-gauge Litz wire for these connections to minimize skin effect losses at the 250kHz switching frequency.

### 2.5 Wire internal tube electrodes to GTM ferrule terminals
**Connect internal discharge and noble gas tube electrodes to the GTM Ferrule pins.**
1. Trim the pure nickel leads from the UV-C Discharge Tube and Noble Gas Tubes to 15mm
2. Gather the three anode wires and crimp them together into the GTM Ferrules IN pin
3. Solder the cathode leads from all three tubes to the common ground point of the GTM base
4. Slide high-temp quartz sleeving over each wire to prevent 2.5kV arcing
5. Verify the crimped connections are rigid and can withstand the 250kHz resonant field vibration
  > Tip: Keep internal leads as short as possible to minimize parasitic inductance, which can shift the 250kHz resonant peak.

## 3. Bring-up
### 3.1 Verify 5V Qi charging and supercapacitor storage
**Test the wireless charging input and energy storage of the supercapacitor system.**
1. Place the Qi Wireless Module on a 5W charging pad and measure 5V_DC at VCC
2. Confirm the 50F Supercapacitor Module POS terminal voltage rises steadily toward 5V
3. Allow the supercapacitor to charge for 10 minutes then remove the charging pad
4. Measure the voltage retention at the POS terminal after 5 minutes of standby
5. Verify that the GND path is stable and shows zero potential difference from the NEG terminal
  > Tip: Note that charging a 50F bank from zero takes significant time; use a high-current multimeter range to monitor the initial bulk charge safely.

### 3.2 Calibrate boost converter output to stable 48V
**Adjust the boost converter potentiometer to lock the output at 48V DC.**
1. Connect a multimeter set to DC Voltage across the VOUT+ and VOUT- pins
2. Power the 48V 300W Boost Converter via the 50F Supercapacitor Module
3. Turn the multi-turn trimmer potentiometer clockwise using a ceramic screwdriver
4. Monitor the display until the output reaches a stable 48.0V DC
5. Disconnect power and verify the setting remains consistent upon reboot
  > Tip: Use a ceramic adjustment tool to prevent accidental shorts or induction interference during the calibration of the 300W rail.

### 3.3 Test 250kHz switching frequency on GaN IC
**Verify 250kHz oscillation frequency at the GaN Power IC gate terminal.**
1. Connect oscilloscope probe to GaN Power IC GATE_IN and ground clip to GND
2. Apply 5V DC power via the Qi Wireless Module to charge the supercapacitors
3. Measure the waveform period and verify a 4.0 microsecond cycle time
4. Observe the peak-to-peak voltage at the Bias Resistor P1 to confirm 5V AC amplitude
5. Adjust the resonant tank if the frequency deviates more than 5kHz from 250kHz
  > Tip: Use a high-impedance 10x probe to avoid loading the resonant circuit, which can shift the measured frequency.

### 3.4 Perform low-power vacuum leak test on glass assembly
**Conduct a vacuum integrity and argon purity test on the globe assembly.**
1. Evacuate the Dycenian Frosted Globe to 10^-5 Torr using a turbo-molecular pump
2. Backfill the chamber with Ultra-Pure Argon Fill to 5 mbar of pressure
3. Apply a 500V test signal to the GTM Ferrules to initiate a low-power glow
4. Monitor the plasma discharge for color consistency to verify argon purity
5. Observe pressure gauges for 10 minutes to ensure zero vacuum decay
  > Tip: A shift from purple to blue-white during discharge indicates atmospheric nitrogen contamination from a leak.

### 3.5 Measure resonant peak of ferrite transformer primary
**Verify the 250kHz resonant frequency of the ferrite transformer tank circuit.**
1. Connect an oscilloscope probe across the Resonant Tank Capacitor pins P1 and P2
2. Apply a low-voltage 48V AC sweep signal to the Transformer PRI_A and PRI_B pins
3. Monitor the voltage amplitude while adjusting the signal generator frequency
4. Identify the frequency where the voltage peak occurs on the oscilloscope trace
5. Confirm the peak aligns with the design target of 250kHz ± 5kHz
  > Tip: If the peak is off-frequency, adjust the primary winding turns or the Resonant Tank Capacitor value to tune the field.

## 4. Assembly
### 4.1 Mount GaN IC and resistor to chassis with thermal epoxy
**Thermally bond the GaN Power IC and Bias Resistor to the aluminum chassis.**
1. Clean the mounting surfaces on the Extruded Finned Chassis with anhydrous isopropyl alcohol
2. Mix two-part thermal epoxy and apply a thin layer to the GaN Power IC backplate
3. Press the GaN Power IC onto the flat internal wall of the chassis
4. Apply thermal epoxy to the Bias Resistor and position it adjacent to the IC
5. Clamp both components firmly for 24 hours to ensure a low-impedance thermal bond
  > Tip: Ensure the epoxy layer is as thin as possible; excess thickness increases thermal resistance and may cause the GaN IC to overheat at 250kHz.

### 4.2 Secure transformer and supercapacitors to finned chassis
**Mount the ferrite transformer and supercapacitor module to the aluminum chassis.**
1. Align the E65 Ferrite Core Transformer with the pre-drilled chassis mounting holes
2. Insert and tighten M3 bolts through the transformer base into the Finned Chassis
3. Peel the protective backing from the 50F Supercapacitor Module adhesive pad
4. Firmly press the supercapacitor module into the internal cavity of the Finned Chassis
5. Verify that both components are immobile and clear of the cooling fins
  > Tip: Apply a thin layer of non-conductive thermal paste between the transformer and chassis to improve heat dissipation during 250kHz operation.

### 4.3 Bond ceramic pucks and discharge tube to quartz stem
**Mount the ceramic excitation pucks and UV-C tube to the quartz support stem.**
1. Apply a thin layer of high-temp ceramic adhesive to the Silver and Gold Doped Ceramic Pucks
2. Press the ceramic pucks onto the Internal Lead Shield quartz rod at 15mm intervals
3. Secure the UV-C Discharge Tube against the quartz rod using high-temp Kapton wrap
4. Align the excitation pucks so the HV_IN pins face the bottom of the stem
5. Cure the entire stem assembly in a kiln at 120°C for 60 minutes
  > Tip: Handle the quartz stem with gloves to prevent finger oils from creating weak points during high-temperature plasma operation.

### 4.4 Final argon backfill and sealing of glass globe
**Backfill the Dycenian Frosted Globe with argon and seal with high-temp silicone.**
1. Place the assembled globe into a vacuum chamber and evacuate to 10^-3 Torr
2. Introduce Ultra-Pure Argon Fill until the internal pressure reaches 700 Torr
3. Apply a bead of High-Temp Silicone around the globe base interface
4. Press the globe onto the Finned Chassis and hold until the sealant sets
5. Allow the silicone to cure for 24 hours at room temperature
  > Tip: Ensure the glass surface is cleaned with acetone before applying silicone to guarantee a hermetic seal.

### 4.5 Attach LCP base and secure with locking screws
**Mount the Integrated LCP Base to the Extruded Finned Chassis using stainless screws.**
1. Align the four mounting holes of the Integrated LCP Base with the tapped chassis ports
2. Insert four M2.5 stainless self-tapping screws through the LCP base into the chassis
3. Tighten the screws in a cross-pattern until the base is flush with the aluminum fins
4. Thread the M2.5x4mm Base Locking Screws into the secondary E26 security points
5. Check that the assembly is rigid and the E26 threaded interface shows no play
  > Tip: Do not over-torque the M2.5 screws, as the LCP material can stress-fracture if the compression against the aluminum is too high.
