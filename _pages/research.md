---
layout: archive
browser_title: "Research"
title: "Research Projects"
permalink: /research/
author_profile: true
---
<h2 style="text-align:left;font-family:'Arial';font-size:28px"> On-chip spectrometer </h2>

<div style="text-align: justify;font-family:'PT serif';font-size:13px">

One of the most exciting photonics pursuits is miniaturizing the spectrometers to a chip-scale. The ability to analyze the wavelength content of light is commercially accomplished using a benchtop dispersion grating, or an interferometer, both of which are very bulky instruments due to their fundamental physics. For many years, Our lab has been doing research on fiber-coupled, micron-scale multi-mode interference (MMI) waveguides and their integration to Optofluidic chips (ref). These MMI waveguides have unique wavelength fingerprints, i.e. mode propagation patterns, which, when imaged, can also give spectral information. My initial research shows that the top scattering of these MMIs mode patterns can be imaged and wavelength extracted using advanced machine learning techniques, which perform better than simple linear algorithms.

 <div style="display: flex; align-items: flex-end;">
    <div style="margin-right: 10px;">
        <figure style="margin: 0;">
            <img src='/images/Project/on_chip_spectro/5x.png' style="max-width: 200px;">
            <figcaption style="word-wrap: break-word;"><i><b>Fig 1 : </b
            >Micrscope image of an MMI waveguide-based spectrometer. Many of these MMI waveguides can be placed on the same chip, light-coupled from separate sources, calibrated & utilized from a single camera image. This opens up possibilites for parallel data processing inherent in this approach.</i></figcaption>
        </figure>
    </div>
    <div style="margin-left: 10px;">
        <figure style="margin: 0;">
            <img src='/images/Project/on_chip_spectro/ezgif.com-animated-gif-maker.gif' width='200'>
            <figcaption style="word-wrap: break-word;"><i><b>Fig 2 : </b>Interference pattern between the propagating modes inside an MMI waveguide. As each mode varies with the change in input light's wavelength, the overall interference pattern also changes deterministically. When imaged from top, this combines the the topology of the rough waveguide surface, generating a unique fingerprint pattern for each wavelength. This opens the possibilities for a very simple on-chip, CMOS-compatible spectrometer</i></figcaption>
        </figure>
    </div>
        <div style="margin-left: 10px;">
        <figure style="margin: 0;">
            <img src='/images/Project/on_chip_spectro/prediction.png' width='300'>
            <figcaption style="word-wrap: break-word;"><i><b>Fig 3 : </b
            >Example of a multi-point spectrum reconstruction by our MMI-spectrometer, compared against the true specturm of the light from a commercial optical spectrum analyzer (OSA)</i></figcaption>
        </figure>
    </div>
</div>

<p> One of the big tasks of this projects was extensive instrumentation. To test the capabilities of this MMI spectrometer, a lot of MMI pattern images (from a camera) plus their true spectra (from a commercial spectrum analyzer) are needed to train the neural network. I automated this data acquisition process by automating all the instruments, namely (a) wavelength tuning of the laser, (b) camera acquisition at each wavelength, (c) spectrum trace at each wavelength, (d) power monitoring of the source. These instruments communicated with each other over TCP/IP communications through the entire acquisition process over several hours without my intervention ( I used to monitor from a remote location). I integrated several high-power, class IIIB (visible) and class IV (NIR) laser and their attenuation over big dynamic range of light levels, to test the capabilities of the MMI spectrometer. </p>

<div style="display: flex; align-items: flex-end;">
    <div style="margin-right: 10px;">
        <figure style="margin: 0;width: 250px;">
            <img src='/images/Project/on_chip_spectro/IMG_8774-ezgif.com-effects.gif' style="width: 100%; display: block;">
            <figcaption style="word-wrap: break-word;"><i><b>Fig 4 : </b>One of the lab automation projects for visible-range spectrometer data acqusition. Light from a supercontinuum source is being tunably filtered by an acousto-optic filter in 10 nm steps, gets coupled into two fibers- one couples into spectrometer (not shown here) and another into the spectrum analyzer. Once the laser confirms that the wavelength has been tuned (shifted), the camera (not shown here) takes an MMI image, the OSA takes a spectral trace, and the powermeter saves the input light's power, all at the same time. </i></figcaption>
        </figure>
    </div>
    <div style="margin-left: 10px;">
        <figure style="margin: 0;width: 250px;">
            <img src='/images/Project/on_chip_spectro/IMG_8776.JPEG' style="width: 100%; display: block;">
            <figcaption style="word-wrap: break-word;"><i><b>Fig 5 : </b
            >To get a NIR-range tunable laser, I also accomplished similar lab automations with a CW Ti:Sapphire cavity laser (pumped externally with a 20 Watt, 532 nm solid-state laser as seen here), but in a very different way! The laser company (Del-mar Photonics) provided us different passive elements, e.g. a birefringent Lyot filter, and different Fabry-Perot etalons, which can be placed at different angles to tune the peak resonant wavelength. We built an external Arduino circuit to shift the orientation of these elements in the cavity. This Arduino circuit had a LabView interface for easy graphical use during an experiment, and could communicate with other instruments (camera, OSA, powermeter etc.) being controlled by sperate programs.</i></figcaption>
        </figure>
    </div>
</div>

<h4 style="text-align:left;font-family:'Arial';font-size:28px"> Sub-project: SM fiber-wavguide gluing </h4>
<p> 
One of our goals with the MMI spectrometer is to increase it’s portability for field applications. Specifically, we want to train an MMI spectrometer in the lab using lasers and send it to unknown light sources, e.g. a large telescope in a remote observatory. To achieve this, we need a very stable, long-term coupling between a single-mode fiber (typically ~5 um in diameter) and our delivery rectangular waveguide (~4 um) to the MMI. In industry, this is typically achieved by etching V-grooves on the Si chip. The low-cost alternative I started investigating is a 3D printed stage with micron-scale groove to hold the fiber in place. I designed a rectangular-groove stage to hold the chip and accommodate a bare fiber and dispense a drop of UV-curable, optically transparent glue at the junction. Given the high viscosity of the glue, the shape of the groove and the curing process, UV dosage etc. are being further researched by one of our new lab members.  </p>

<div style="display: flex; align-items: flex-end;">
    <div style="margin-right: 10px;">
        <figure style="margin: 0;width: 800px;">
            <img src='/images/Project/SM fiber-waveguide gluing/Picture0.png' style="width: 100%; display: block;">
            <figcaption style="word-wrap: break-word;"><i><b>Fig : </b>(a) An early version CAD design of the 3-printed chip stage to glue the fiber to the waveguide. The fiber groove has to be raised on a pedestal to match the waveguide position within the printer tolerance  (b) a 3-D printed V-groove mount, printed using the Formlabs SLA 3D printer at UCSC BELS (c) Controlled dispensing of a glue-drop at the fiber-waveguide coupling junction. The waveguide’s top field propagation profile and facet mode are also monitored throughout the process. </i></figcaption>
        </figure>
    </div>
   
</div>

<h4 style="text-align:left;font-family:'Arial';font-size:28px"> Sub-project: Integrating MMI spectrometer to a large telescope </h4>

<p>One of our application goals with the MMI spectrometer is to integrate it into large-scale telescopes, in particular, the 3-meter Shane telescope at the Lick Observatory on top of Mount Hamilton in San Jose, California. We have been working with three project goals- (a) a spectrometer system that can seamlessly integrate within Shane’s adaptive optics assembly, where space is very tight, (b) coupling light with low-loss from the telescope focal plane into the MMI chip using different fiber designs (single-mode fiber, photonic lantern, lensed Multi-mode fiber) (c) Imaging the patterns out of an MMI waveguide generated by light from different bright, ~0 magnitude stars (e.g. Vega, Capella, Aldebaran) using cheap, commercially available cameras. We have successfully transported a fiber-glued MMI chip from our UCSC lab to the observatory and tested its coupling. The scarcity of light makes this project very challenging, but it has been exciting to collaborate with astronomers and the Lick engineers on high-precision optimization of the Optical assembly.</p>

<div style="display: flex; align-items: flex-end;">
    <div style="margin-right: 10px;width: 600px;">
        <figure style="margin: 0">
            <img src='/images/Project/Integrating MMI spectrometer to a large telescope/Picture0.png' style="width: 100%; display: block;">
            <figcaption style="word-wrap: break-word;"><i><b>Fig 1 : </b>(a) The 3-meter Shane telescope at Lick. The Adaptive Optics assembly is right underneath the telescope. A colleague and I are climbing on a forklift to reach the ShaneAO and install our optical subsystems. (b) I designed and deployed a chip + fiber mounting and microscope imaging system within the space constraints on the board. The fiber collects light from the focal plane of the telescope and feeds it to our chip, which we can image (c) Top- A lensed multi-mode fiber edge-coupled to one of our single-mode delivery waveguides, Bottom-facet image of the MMI section using laser light at the telescope. The final goal here is to efficiently couple sub-nanowatt light from the stars into the MMI and image it.  </i></figcaption>
        </figure>
    </div>
       
</div>

<h2 style="text-align:left;font-family:'Arial';font-size:28px; padding-top: 40px;"> Multiplexed biosensing in optofluidic chip using free-space excitation </h2>
<p style="text-align: justify; font-family:'PT serif';font-size:13px">
My PhD lab have been working on the development of CMOS-compatible optofludic on-chip ARROW bionsensor devices that can detect and count individual tiny, nano-scale pathogens (e.g. RNA, protein biomarkers) with the help of fiber-based planar laser excitation of fluorescently labeled biomarkers (more details about my works on planar optofluidic schemes in a later section). My research goal was to design a waveguide-free optofluidic biosensors with free-space multiplexed laser excitation (i.e. different fluorescently tagged particles can be identified and distinguished from the same fluid sample based on their fluorescence signal signatures). I implemented this by evaporating reflective aluminum thin film on the planar device’s top surface, into which FIB-milled light entrance slits were created on the optofluidic channel. The next and the most crucial step was to design a two-laser, top-down precision excitation setup. The individual laser beam-shapes and focal depths had to be taken into consideration since we want to focus all the power on the ~10um x 4um patterened slits without wasting incident light on the reflecting areas. I developed a composite, portable optical system comprising a custom, open-barrel microscope and two elongated laser beams almost matching the dimesions of the slit patterns over the channel. I also developed a MATLAB GUI-based signal post-processing app for the data analysis of these experiments.

<div style="display: flex; align-items: flex-end;">
    <div style="margin-right: 10px;width: 800px;">
        <figure style="margin: 0">
            <img src='/images/Project/Multiplexed biosensing in optofluidic chip using free-space excitation/top_down0.png' style="width: 100%; display: block;">
            <figcaption style="word-wrap: break-word;"><i><b>Fig 1 : </b>(a) SEM image of an aluminum-coated optofluidic sensor. The z-shape is the fliudic channel, connected on left/ right with solid-core connection waveguides. The tiny patterned slits on the optofluidic channel can be seen at the center, where the laser beams will be focused (b) Movable top-down excitation setup built with cage systems. The yellow cage box is in-house designed and 3D-printed, to hold a 600 nm long pass filter at 45degrees. Green laser comes from the side of this box, while the red laser diode (not turned on) is at the top of the system. Right above the sample, a side-arm camera helps to position the system on the chip. (c) Two high-power laser spots beam-shaped and is incident on the patterned slits on the optofluidic channel. The beam separation is carefully designed to ensure no cross-talk (leakage) into unintended slits. This enables simulataneous/ separate laser excitations and makes multiplexed sample detection from the same channel possible (d) A time trace of the fluorescence signals. Photons are collected by an avalanche photodiode (APD) with a TImeharp SIngle-photon counting board and binned by a MATLAB program. Each spike denotes a particle (event). In this particular scheme, lasers can be used in different combinatorial sequence in the same run to excite differently tagged particles. (e) I also developed a MATLAB GUI based program, which can separate out each event (here you can see the zoom-in of a spike) and calculate different properties of the multi-peak signal for further analysis. </i></figcaption>
        </figure>
    </div>
    
</div>

<h4 style="text-align:left;font-family:'Arial';font-size:28px"> Sub-project: Knife-edge measurement of free-space beam profiles </h4>

<p>Because the performance of the top-down biosensor depends heavily on the incident laser power (intensity), it was important for this project to measure the beam quality. I implemented a knife edge measurement system by blocking and controlling amount of the laser power incident on a photodetector using a thin razor blade, which can scan the beam by moving in nano-scale steps on a 2D piezo-stage along one cross-sectional diameter of the beam as well the focal depth. The 1/e^2 beam diameter (w) could be calculated from the measured knife position_vs_power by modeling the data fit with P= P0 + Pmax/2 * (1 - erf (√2(y-y0)/w)), where P0=backround power, Pmax=maximum power, y0= position for half power. Ultimately, this enabled us to measure many useful Gaussian beam parameters, e.g. beam width, beam quality, divergence, rayleigh length, M^2 parameter. .</p>

<div style="display: flex; align-items: flex-end;">
    <div style="margin-right: 10px;width: 750px;">
        <figure style="margin: 0">
            <img src='/images/Project/Knife-edge measurement of free-space beam profiles/knife_edge0.png' style="width: 100%; display: block;">
            <figcaption style="word-wrap: break-word;"><i><b>Fig : </b>Knife edge measurement setup (a) Schematics of the knife-edge procedure of the focused beam (b) LabVIEW interface plotting the power measurement for each in-plane step of the knife. After an in-plane scan is finished, the program estimates the 1/e^2 diameter of the beam (c) This can be repeated at different z (light propagation) positions to find the beam size at each position, which can calculate the beam divergence, depth of field etc. for different wavelengths of light.  </i></figcaption>
        </figure>
    </div>
</div>

<h2 style="text-align:left;font-family:'Arial';font-size:28px; padding-top: 40px;"> Project: Biosensing in optofluidic chip using free-space, patterned excitation</h2>
<p style="text-align: justify; font-family:'PT serif';font-size:13px">
We wanted to further improve upon the concept of fiber-free excitation scheme on the ARROW-based optofluidic sensor, as the above concept requires metal film deposition, milling and precise positioning of laser beam. We wanted to image an excitation pattern anywhere on the detection channel. To this end, we imaged the “pattern-generating” waveguides (MMIs, y-splitters) available to us and focused the output pattern on an uncoated ARROW device. This eliminated the need for Al deposition and patterning and is power-efficient, as the full incident power is contained in the tiny spots. I implemented the optical scheme using a double-stack optical assembly. An excitation pattern was generated on the upper floor and was routed to be normally incident on the vacuum held biosensor chip in the lower floor. 

<div style="display: flex; align-items: flex-end;">
    <div style="margin-right: 10px;width: 800px;">
        <figure style="margin: 0">
            <img src='/images/Project/Biosensing in optofluidic chip using free-space, patterned excitation/Picture0.png' style="width: 100%; display: block;">
            <figcaption style="word-wrap: break-word;"><i><b>Fig : </b> (a) Mode images of a fiber-coupled 1x4 Y-splitter waveguide. (b) This pattern is collimated and sent to be normally incident on an uncoated optofluidic channel sitting on a different chip, with the help of a custom-built camera-assisted microscope. The choice of appropriate optics can reduce the magnification factor of the beam to keep the pattern tightly confined on the channel. (c) Multi-stack optical setup for the experiment. At the top floor, the excitation pattern is created by fiber coupling the waveguide. This is then sent to the lower floor optics, where the biosensor and the collection optics sits. The top-floor optics can move in-plane with the cage-system micrscope (which has independent fine focusing) so that the patterned beam stays on-axis with the optical elements.   </i></figcaption>
        </figure>
    </div>
</div>

<h2 style="text-align:left;font-family:'Arial';font-size:28px"> Planar ARROW optofluidic biosensor optical characterization </h2>


<p style="text-align: justify; font-family:'PT serif';font-size:13px">I have characterized different designs of single-layer and buried ridge SiO2 waveguides on ARROW platforms as an excitation mechanism for planar optofluidic sensors. The experiments included  mode imaging of the waveguides (to make sure the mode hits the center of the orthogonally intersecting channel), as well to measure the quality of multi-spot interference patterns at the design wavelengths, and finally their overall performance in a sensing experiment using fluorescence calibration beads. </p>


<div style="display: flex; align-items: flex-end;">
    <div style="margin-right: 10px;width: 800px;">
        <figure style="margin: 0">
            <img src='/images/Project/Planar ARROW optofluidic biosensor optical characterization/Picture0.png' style="width: 100%; display: block;">
            <figcaption style="word-wrap: break-word;"><i><b>Fig : </b>Planar optofluidic ARROW biosensors (a) conceptual design of our labs MMI waveguide based ARROW device. The blue channel is where the liquid (and pathogens) flow. The MMI and the single mode excitation waveguides orthogonally intersect the channel and can deliver the laser power. The collection waveguides on two ends of the channel collects the fluorescence signals and guides it to a photodetector. (b) A laser-coupled optofluidic chip in operation. The objective at the bottom of the picture can do simultaneous optical mode imaging during a fluorescence experiment. (c) Mode profiles of a single mode waveguide (facet back-lit with a red LED) with 488nm, 556nm, 633nm lasers. The three lasers were coupled to the same single mode fiber. </i></figcaption>
        </figure>
    </div>
</div>


<h2 style="text-align:left;font-family:'Arial';font-size:28px; padding-top: 40px;"> Simulation of Planar waveguides and input grating couplers</h2>
<p style="text-align: justify; font-family:'PT serif';font-size:13px">
I have participated in training sessions offered by Photon Design to learn how to model and simulate various types of planar waveguides using their FDM and FMM solvers. I utilized FIMMWAVE for mode calculations and building model lists and FIMMPROP to calculate mode overlaps and simulate field propagation along the waveguides. Using these tools, we were able to calculate the coupling efficiency and loss between the single-mode and MMI waveguides in a planar optofluidic biosensor. Later, I applied these simulation techniques to optimize the MMI waveguide design parameters. This optimization aimed to enhance the contrast between field patterns at different wavelengths, enabling its use as a spectrometer.


<div style="display: flex; align-items: flex-end;">
    <div style="margin-right: 10px;width: 550px;">
        <figure style="margin: 0">
            <img src='/images/Project/Simulation of Planar waveguides and input grating couplers/Picture0.png' style="width: 100%; display: block;">
            <figcaption style="word-wrap: break-word;"><i><b>Fig : </b>Simulation of planar waveguides in FIMMWave (a) an SiO2 buried ridge waveguide sitting on the ARROW (antiresonant reflecting optical waveguide) layers (b) Intensity profile of the TE00 mode using the finite difference method (FDM) solver engine (c) calculation of different mode properties by the solver, which can be scanned with a parameter sweep. </i></figcaption>
        </figure>
    </div>
    <div style="margin-left: 10px;width: 350px;">
       <figure style="margin: 0">
            <img src='/images/Project/Simulation of Planar waveguides and input grating couplers/Picture1.gif' style="width: 100%; display: block;">
            <figcaption style="word-wrap: break-word;"><i><b>Fig : </b
            >Extraction of the z-axis field propagation pattern inside an MMI waveguide using eigenmode expansion in FIMMProp. The gif shows the shift of the intensity pattern in changing the wavelength from 633 to 643 nm, with bright, confined spots at ~3800 um mark. </i></figcaption>
        </figure>
    </div>
</div>

<p style="text-align: justify; font-family:'PT serif';font-size:13px">
Another way to couple light from off-plane into a biosensor is the use of a surface grating coupler on the planar excitation waveguides. I worked on simulating the design of input grating couplers in SiO2 and SiN single-mode waveguides aimed for visible range applications. The performance parameters, e.g. coupling efficiency, wavelength bandwidth, incident angle bandwidth of a grating coupler depends on several design parameters, e.g. grating period, duty cycle, angle, groove depth. I used 2D and 3D FDTD solvers in OmniSIm (Photon Design) and Lumerical to analyze the coupled field profiles in the waveguide, which were also cross-validated with the waveguide modes in FIMMWave. I also integrated a Python script to generate differently apodized grating structures from OmniSim’s command terminal. We also fabricated some of these gratings on our available SiO2 waveguides.</p>


<div style="display: flex; align-items: flex-end;">
    <div style="margin-right: 10px;width: 550px;">
        <figure style="margin: 0">
            <img src='/images/Project/Simulation of Planar waveguides and input grating couplers/Picture2.png' style="width: 100%; display: block;">
            <figcaption style="word-wrap: break-word;"><i><b>Fig : </b>Design structure of an input grating coupler on a few-mode, buried ridge SiO2 waveguide with constant grating period (b) 2D FDTD simulation of normal incidence of a gaussian beam excitor (fiber simulator) in OmniSim- some fraction of the light couples into the vertically fundamental mode of the waveguide. </i></figcaption>
        </figure>
    </div>
    <div style="margin-left: 10px;width: 250px;">
       <figure style="margin: 0">
            <img src='/images/Project/Simulation of Planar waveguides and input grating couplers/Picture3.gif' style="width: 100%; display: block;">
            <figcaption style="word-wrap: break-word;"><i><b>Fig : </b
            >Lumerical 3D simulation of a 20fs pulse excitation on a linearly apodized grating structure using a normally incident excitor with tilted phase front.</i></figcaption>
        </figure>
    </div>
    
</div>    
<h2 style="text-align:left;font-family:'Arial';font-size:28px; padding-top: 40px;"> Project: Designing Photonic Crystal fiber </h2>
<p style="text-align: justify; font-family:'PT serif';font-size:13px">
Photonic crystal fibers (PCF) are a specialized type of fiber where light is propagated within a core surrounded by a two-dimensional lattice of low-index air holes. This structure enables photonic bandgap propagation, which exhibits several distinctive optical properties not found in conventional fibers, such as high anomalous dispersion, tight confinement, high nonlinearity and birefringence. My work involved the design and simulation of highly birefringent photonic crystal silica fibers for O- to L-band applications using finite element analysis in COMSOL. This project, which began as part of my undergraduate thesis, led to developing a fiber embedded with gallium phosphide nano-rods embedded within a spiral lattice distribution. Thedesign demonstrates exceptionally high birefringence and nonlinearity, making it suitable for various applications, including coherent communication, supercontinuum generation, and pulse compression. I also worked on similar PCF designs for THz applications (0.1-1.5 THz) using a different low-loss material (TOPAS).

<div style="display: flex; align-items: flex-end;">
    <div style="margin-right: 10px;width: 700px;">
        <figure style="margin: 0">
            <img src='/images/Project/Designing Photonic Crystal fiber/fig_all.png' style="width: 100%; display: block;">
            <figcaption style="word-wrap: break-word;"><i><b>Fig: </b>An example photonic crystal fiber designed and evaluated by me. (a) Cross-section of the fiber showing a composite air-holes distribution- one hexagonal lattice ring followed by an 8-arm spiral distribution of air holes in silica fiber. At the center, two ~0.5 um GaP strips induce high birefringence and nonlinearity in this fiber. Different design parameters, i.e. air holes radii, pitch, GaP strip size can affect the performance (b) Mode field distribution of the y and x polarized modes, showing very different levels of confinement. This performance analysis was done using COMSOL Wave Optics module. (c) An example plot of a parametric sweep, showing GaP strip length_vs_birefringence performance. </i></figcaption>
        </figure>
    </div>
</div>
