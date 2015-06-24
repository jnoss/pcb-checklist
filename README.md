pcb-checklist
=============

Checklist to be used before sending a pcb to fab. Sources I've used at end, comments welcomed.

- [ ] all polarized components point same way. Also the polarity should be indicated and visible when component is installed.
- [ ] no bottlenecks or breaks in polygon (run ratsnest make sure it returns 0 airwires)
- [ ] double-check any new footprints, or schematic symbols, or new devices (see below)
- [ ] status LEDs on PCB
- [ ] Use mitered 45 degree bend instead of 90 degree bend where trace changes direction.
- [ ] power traces as large as feasible
- [ ] check voltage ratings of components to be used
- [ ] check all parts to be used in design are in stock and ordered
- [ ] digital and analog signal commons joined at only one point. (Digital and analog parts are placed separately. Digital parts on digital ground (DGND) and analog parts on analog ground (AGND). Put a ferrite bead between analog and digital ground to reduce interference.)
- [ ] re-run erc and drc, netlist check
- [ ] Print 1:1 scale PCB file, check the footprint by placing the component on it.
- [ ] Bypass capacitors placed close to IC power pins. Each pin have one local bypass cap.
- [ ] Check reset circuitry, switch or jumper is accessible
- [ ] On power/ground plane, distribute the via density about the available space as evenly as possible.
- [ ] Thermal relief pad used for these pads which could have cold solder joint issue (e.g., power/ground pins of through-hole parts).
- [ ] no silkscreen legend text over vias (if vias not solder masked) or holes
- [ ] Soldermask does or does not cover vias (consistently tented or not)

testing

- [ ] Test pads/vias have added on these important signals. These pads/vias should not be placed within 5mm of the edge.
- [ ] Test vias are exposed.

labelling, mechanical

- [ ] all legend text reads in one or two directions
- [ ] components labeled left-right, top-bottom
- [ ] Switches, jumpers or LEDs are labeled with their functions.
- [ ] labels on pins for functions - label ADC pins, PWM pins, etc.
- [ ] ensure pin 1 (different usually square) interpretation and orientation consistent among all connectors of a given type on the board
- [ ] for asymmetric connectors ensure that orientation is as desired for outside/case layout/etc. (ISP, ftdi adapters, etc)
- [ ] re-read all datasheets for layout requirements - e.g., antenna spacing from ground plane, copper land for heatsinking, etc.
- [ ] if making multiple similar boards, follow same convention for connector layout/ orientation on each (if a connector / adapter board will hang off the edge of the board, ensure that it is set the correct orientation)
- [ ] ensure that polarity of connectors is marked, or if possible physically keyed or interlocked
- [ ] high pin count ICs and connectors have corner pins numbered for ease of location
- [ ] silk screen tick marks for every 5th or 10th pin on high pin count ICs and connectors

stenciling:

- [ ] ensure any new components don't have rounded-edged pads (will break paths for stencil)

new components:

- [ ] finished hole sizes are >=10 mils larger than lead
- [ ] pads >=10 mils larger than finished hole sizes (also seen this >=15)
- [ ] For SMT pads, the length are at least 8mil longer than pins' length (4mil each side). The width should be at least equal to pads' width.
- [ ] all ICs have pin one clearly marked, visible even when chip is installed
- [ ] re-check all dimensions and pinouts from datasheet

date code:

- [ ] date code printed
- [ ] PCB revision printed on silkscreen
- [ ] assembly revision blank on silkscreen legend
- [ ] serial number blank on silkscreen legend a filled rectangle provided for writing with a marker. (depending on how long the serial #’s will be and about 0.25” high.)

additional:

- [ ] Hatched copper pour (12mil trace and 20mil pitch) rather than solid copper pour where possible.
- [ ] Avoid small copper area and sharp shape area as this may act as antennae and emit noise.
- [ ] layout PCB so that any rework or repair of a component does not require removal of other components
- [ ] Check all surface mount pads have tracks that come out of the end, not the side (i.e. no links between adjacent IC pads that will look like a short during inspection).
- [ ] differential pairs are same length
- [ ]  Series-matching/damping resistors should be close to source side. Termination resistors should be close to target pins.
- [ ] High speed singles design rule check (termination, impedance, reference plane, EMI, multi-points connection topology,etc.).

thermal

- [ ] For these high power dissipation parts (e.g., FET,LDO,DC/DC module), make enough copper coverage onall the layers. Also thermal vias (plated thru-holes) are needed under the package.
- [ ] Locate these temperature-sensitive components (e.g., electrolytic cap, oscillator) away from hot part (e.g., transformer, heat sink).
- [ ] Thermal land (exposed copper area directly underneath the body of the hot component.e.g., LDO) should not covered by solder mask.



=============

sources:
- http://www.aqdi.com/check.htm
- http://www-ppd.fnal.gov/EEDOffice-w/Projects/MicroBoone/EDR/Electronic_assemblies_checklist_062812.pdf
- http://www.quick-teck.co.uk/TechArticleDoc/19196513481352925083.pdf
- http://www.aqdi.com/check.htm
- http://electronics.stackexchange.com/questions/6773/good-checklist-for-pcb-design-to-be-used-by-the-ee-not-by-the-pcb-designer
