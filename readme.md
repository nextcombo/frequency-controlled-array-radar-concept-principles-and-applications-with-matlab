# Frequency-controlled Array Radar: Concept, Principles, and Applications [with MATLAB Code]

Frequency-controlled array radar is a new array radar technology proposed in recent years, capable of forming transmit beams with distance-dependent characteristics. It overcomes the problem of traditional phased array radars ineffectively controlling the direction of the transmitted beams. This paper systematically introduces the concept, principles, and application features of frequency-controlled array radar. It comprehensively reviews domestic and international research literature on this topic, summarizes the current state of research in terms of concepts, basic principles, and radar application features, and analyzes its future application prospects and key technical issues that need to be addressed.
Keywords Frequency-controlled array; Frequency-controlled array radar; Array design; Phased array; New-type radar
1 Introduction: Array-based phased array radars, with the advantage of freely achieving beamspace scanning, are widely used in the fields of radar target detection and imaging. Typically, each element emits the same signal, which is adjusted by phase shifters at the output end to achieve beamspace scanning. Alternatively, frequency scanning can be achieved by changing the operating frequency (i.e., frequency scanning antenna).
However, phased arrays and frequency-scanning antennas share a common drawback: within each scanning frame, the beam direction remains constant in range, i.e., independent of distance. However, in applications such as interference suppression with range correlation and clutter suppression, it often requires the array beam to point at different distances from the same angle within the same frame, necessitating that the beam direction vary with distance.
In 2006, the concept of FDA (Frequency Diverse Array) radar was first proposed in literature [2] and applied for U.S. patent [3]. The direct translation of FDA should be "Frequency Diversity Array," but it is more appropriately translated as "Frequency-Controlled Array" due to its similarity to phase-controlled array radars. This is because, similar to phase-controlled array radars, it employs phase-coherent signals with a frequency offset that is much smaller than the carrier frequency, allowing for slight frequency deviations in the radiation signal's center frequency while maintaining overlapping main frequency components. This differs from the requirement for frequency orthogonality in OFDM (Orthogonal Frequency Division Multiplexing) [4] and MIMO (Multiple Input Multiple Output) systems.
Table 1 compares the characteristics of frequency-controlled arrays with several typical array technologies, revealing that their physical properties are similar. The frequency-controlled array can be considered an extension of phase-controlled arrays, while phase-controlled arrays represent a specific case of frequency-controlled arrays. Therefore, this paper refers to this new radar system as a frequency-controlled array radar [5].
Due to the directional pattern of the frequency-controlled array antenna, which is dependent on distance, this concept has garnered significant attention in American defense research institutions [6,7]. In recent years, a plethora of research papers related to frequency-controlled array radar have emerged in international journals and conferences, advancing the technology from various perspectives and application backgrounds [8]. This paper will systematically introduce the principles, characteristics, and potential applications of frequency-controlled array radar, review the current state of research, analyze its future prospects, and discuss key technical issues.
The structure of this article is as follows: Section 2 introduces the basic principles and characteristics of frequency-controlled array radar. Section 3 elaborates on the current state of research; Sections 4 and 5 respectively explore the application prospects, development trends, and key technical issues. Section 6 summarizes the entire text.
Table 1: Comparison of Technological Features between Frequency-Controlled Arrays and Several Typical Arrays
Work mode
Transmit signal
Array gain
Transmitted array pattern - Distance-dependent
Transmitted array pattern - azimuth angle dependent
FDA  
Non-orthogonal carrier
Coherent
Yes
Yes
Yes
Phased array
Non-orthogonal carrier
Coherent
Yes
None
Yes
Frequency scanning
Same carrier
Coherent
Yes
None
Yes
2 Fundamental Principles of Frequency-Controlled Array Radar
In the formula, denotes the number of elements.
Taking a 1-dimensional linear uniform array radar with frequency control as an example, assuming the desired beam pointing angle is θ and the distance of the beam direction is d, its uniformly weighted radiation pattern can be approximately derived as [9]:
Among them, is the element spacing, is the speed of light, and the phase factor is.
The characteristics of frequency-controlled array radar can be summarized by equation (2) [6,7,10].
1  
Different from frequency scanning radar: the frequency offset of frequency scanning radar is applied at different times, and all elements have the same frequency offset at the same time. Frequency-controlled array radars apply different frequency shifts to different elements at the same time.
2  
Frequency offset is an additional quantity, not a transmission of orthogonal multi-frequency signals: Frequency-controlled arrays emit phase-coherent signals (similar to phased arrays), only by adding frequency control to make the radiation signal frequencies different. This falls within the category of phased arrays and differs from OFDM radars that transmit signals at different carrier frequencies.
3  
The array is oriented with the load frequency deviation (as shown in Figure 2).
4  
When the frequency offset is fixed, the beam direction varies with distance (distance-dependent). When the distance is fixed, the beam direction changes with frequency offset (frequency-offset correlation); At that time, the frequency-controlled array degraded into a phase-controlled array.
2.2 The main characteristics of the Frequency-Controlled Array Radar (FCAAR) are its array factor, which is distance-dependent. Assume Figure 3 compares the array directional patterns of FCAAR and phased array radars [8]: The directional pattern of the phased array is not distance-dependent, whereas the unique "S"-shaped directional pattern of the FCAAR is caused by the array factor. This factor indicates that the peak of the directional pattern is a function of the distance between the elements.
Another important characteristic of the frequency-controlled array is its periodicity in the array factor. As shown in equation (2), the peak of the array pattern occurs at:
Equation (3) indicates that if one parameter is fixed, there can be multiple solutions for the non-fixed parameters; if two parameters are fixed, the third parameter has only one solution. For example, with respect to , we obtain:
It depends on two parameters: distance and time. Assume Figure 4 shows the array scan pointing diagram at two moments.
2.3 Several implementation methods of frequency-controlled array radar to avoid the frequency decoupling effect of target response, the frequency offset needs to meet [11]:
In the formula, "target length" refers to the target's length in the radar aperture direction. At the same time, in order to ensure that the signals emitted by each element are free from decoupling effects, it is also necessary to satisfy:
In the formula, denotes the coherent processing time interval.
Currently, there are mainly the following methods to implement the frequency offset setting of frequency-controlled array radars, and each method has its own system performance characteristics [12].
1  
Method for Implementing Frequency Stepping Based on Mixer Step-up Frequency (2008, WickS and ANTONIK [3] patent): Firstly, a preset frequency signal is generated, then it is mixed with the step-up frequency signal of a ramp frequency to achieve frequency configuration. The disadvantage is that the mirror frequencies of the mixer and the intermodulation between radio frequency and local oscillator frequencies will lead to poor spectral purity in the array signal, which can easily cause blurring issues in subsequent signal processing.
2  
Independent Bootstrapped Source Implementation (Same as the patent above): Each element utilizes an independent signal source, which can generate the required element waveform through direct digital frequency synthesis or programmable phase-locked loop. However, it is necessary to consider the impact of clock jitter and phase noise [14-16].
3  
Implementation method based on the divider (as proposed in [17]): Although there are issues with mixing and harmonics due to mixers, it avoids problems of clock jitter and phase noise from the local oscillator.
4  
Design method based on time delay line (as proposed in [18]): Due to the time-varying radiation pattern of frequency-controlled arrays, this method can achieve good signal spectral purity. However, it is challenging to precisely control the delay for analog signals.
3. Research Status of Frequency-Controlled Array Radar
3.1 Analysis of the Array Characteristics of Frequency Control Arrays•
The literature [23-25] analyzed the distance-dependent characteristics of frequency-controlled array (FCA) transmission beams and their applications in distance-blurred clutter suppression. Two U.S. patents [26,27] explored the potential of FCA for enhancing radar system degrees of freedom.
•  
The literature [17] analyzed the time and phase periodicity characteristics of the FCA radiation pattern, while the literature [28] analyzed its periodic beam scanning characteristics and designed a cost-effective FCA antenna [25].
•  
The literature [29] pointed out the coupling issues between distance and azimuth angle responses in FCA transmission beams, and subsequently proposed iterative minimum mean square space-time adaptive processing algorithms and time-space adaptive processing algorithms [21] to address the distance-phase coupling issues in beamforming; on this basis, the literature [30,31] studied the problem of distance-blurred suppression based on space-time-distance joint processing.
•  
The literature [32] conducted electromagnetic simulation analysis on the multipath characteristics of FCA radar, indicating that it can resolve more targets than phased array radar. The literature [33,34] also extensively simulated the distance-dependent characteristics of FCA beams.
The array manifold blurring characteristic is an important indicator for evaluating target detection and estimation performance [35-37]. The array manifold is determined by the physical positions of the elements and the array characteristics, and the literature [38] studied the relationship between the geometric structure of aomnidirectional antenna array and the DOA (Direction of Arrival) estimation of target signals; the geometric characteristics of the array manifold are also widely used in array design with limited sidelobe ratios [39] and polarization array design [40].
Documents [41,42] analyze the geometric parameters of array manifolds to provide a sufficient condition for directional ambiguity in arrays—"manifold ambiguity" originates from the existence of fuzzy sets with linear correlation in the array manifold. Based on this, documents [43,44] derive the geometric characteristics of frequency-controlled array manifolds, analyze their detection and resolution capabilities using differential geometry methods, and calculate fuzzy sets by uniformly partitioning the array manifold curves. Compared to phased arrays, frequency-controlled arrays have smaller first-order curvature, stronger detection and resolution capabilities, and fewer fuzzy generation sets, enabling more targets to be resolved without ambiguity. However, it should be noted that the method of uniformly partitioning array manifold curves does not guarantee the acquisition of all fuzzy generation sets; furthermore, document [45] also analyzes the radar fuzzy function characteristics of frequency-controlled arrays.
The angle and distance dependency of the beamforming angles in frequency-controlled array radars create conditions for joint estimation and positioning of target parameters, but it is necessary to clarify the upper limit of parameter estimation performance. The Cramer-Rao Lower Bound (CRLB) is often used to analyze the performance of array parameter estimation, but existing literature mostly focuses on phased arrays and MIMO radar: document [46] derives the CRLB for time delay, velocity (Doppler shift), and azimuth angle estimation in phased arrays; document [47] derives the CRLB for joint estimation of target parameters in co-located and split antenna MIMO radars; document [48] analyzes the estimation capability of non-coherent MIMO radars for moving targets.
To this end, document [49] considers two signal models before and after matched filtering, and derives the CRLB expressions for estimating target azimuth angle, range, and Doppler shift in frequency-controlled array radars. Both theoretical analysis and simulation results indicate that there is coupling between azimuth and range directions in frequency-controlled arrays.
To address this coupling issue, the literature [50,51] investigates time-varying or logarithmic frequency offset distance-azimuth decoupling methods, which can degrade array target detection and resolution performance. The literature [52] proposes a subarray structure that addresses the distance-azimuth coupling of transmitted beams, but changes in element positions and frequency increments directly affect the performance of target parameter estimation. Therefore, it is essential to optimize the array design.
Array optimization primarily involves the design of array structure and weight vectors: linear array optimization often aims to reduce sidelobe levels (weighting is a common method); non-uniform linear arrays often enhance array aperture performance through element position optimization (e.g., minimum redundancy array [55-57]). Although array scheduling optimization is a research hotspot in array signal processing [58-60], effective solutions for frequency-controlled array optimization have yet to be developed.
The optimization design of the frequency control array needs to answer the following questions:
1  
Under the same aperture, which array structure has the best angle estimation accuracy?
2  
How to partition the subarray under the same array structure to achieve optimal target parameter estimation accuracy?
3  
Selection of array optimization criteria and optimal solution of the objective function
In response to these issues, the literature [61] derives the CRLB expression for estimating target azimuth and range using arbitrary sub-aperture - frequency-controlled array radar. Based on minimizing the CRLB, it proposes an antenna element frequency increment optimization design method, and adopts an optimization solution method based on penalty function and NELDER-MEAD algorithm [62]. Simulation results show that among uniform linear arrays, centered symmetric linear arrays, and minimum redundancy arrays with the same aperture, the uniform linear array has the best direction finding performance. However, in optimizing multiple sub-arrays (...), this paper only considers the optimization of the CRLB for azimuth angle estimation but does not take into account the distance estimation CRLB, and further research is needed for multi-objective function optimization (considering convex optimization techniques).
The literature [63] proposes an emitted beamforming method based on spherical functions, aiming to concentrate the energy of the transmitted signal into the desired distance or azimuth observation area. However, it does not consider the time-varying characteristics of frequency-controlled array beams, and further research has been conducted in this context by literatures [65,66].
Furthermore, literature [67] designs a system architecture for frequency-controlled array radar receivers; literature [18] designs a frequency-controlled array antenna suitable for linear continuous wave frequency modulation; literature [68] introduces a frequency-controlled array receiving beamforming method for solving the problem of range ambiguity in space-time signal processing; and literature [69] proposes a multi-domain filtering method for polarization-sensitive frequency-controlled arrays.
3.3 New Radar Technology Based on Frequency-Controlled Arrays•
Literature [20] is the first to apply frequency-controlled arrays to radar imaging, aiming to utilize frequency multiplexing to increase the azimuth synthetic aperture length and improve azimuth resolution [70].
•
Literature [71] proposes a ground motion target indication method for forward-looking radar based on frequency-controlled arrays.
•
Literatures [72,73] propose a dual-station radar system based on frequency-controlled arrays, applied in low-jamming electronic reconnaissance, and further propose MIMO radar technology based on frequency-controlled arrays [9], but requires selecting appropriate fixed reference points for array element positioning; literature [74] proposes a non-uniform array solution, which can be applied to radar 2D imaging [75].
•
Literature [76] uses frequency-controlled arrays to suppress the effects of distributed MIMO radar transmit-receive beam grating lobes; literature [77] proposes a phased-MIMO radar transmit beamforming method that combines the advantages of frequency-controlled arrays and MIMO radar.
One of the significant application potentials of frequency-controlled arrays in radar is to achieve 2D joint estimation of target distance and azimuth angle, but it needs to solve the coupling problem between range and azimuth angle in beamforming. To this end, literature [78,79] respectively proposes a method for joint estimation of target range and azimuth angle based on dual-pulse frequency-controlled array radar, and literature [80,81] further proposes a joint estimation method based on frequency-controlled array - MIMO radar.
Influenced by the surge in cognitive radar research, literature [82,83] separately proposes the concept of cognitive frequency control array radar technology based on adaptive selection and cognitive selection incremental frequency offset. On this basis, the literature [84,85] proposed new system frequency control array radar technology with environmental perception and ripple-cancelling cognitive.
The aforementioned literatures all employ frequency-controlled arrays for radar transmission ends. Document [86,87] draws on nested array technology [88], proposing the design method of nested frequency-controlled array receiver based on delay lines [89], and conducts theoretical analysis of its target detection and estimation performance.
Furthermore, the literature [90] proposes a radar radio frequency stealth method based on frequency-controlled arrays: by broadening the emission beam width to reduce the signal peak power, it is possible to decrease the probability of being intercepted by radar. The literature [91] introduces a wireless confidential communication method based on frequency-controlled arrays, which can significantly reduce the probability of communication signals being intercepted and deciphered without lowering the communication error rate.
4. The application prospects of Frequency-Controlled Array (FCA) radar differ from those of Phased Array Radar (PAR), where the core characteristic is that the array directional pattern has a distance dependence, and it can effectively control the distance pointing of the transmitted beams. Therefore, it has broad application prospects [9]. The following introduces several possible application methods:
4.1 For the new system of dual-station radars using frequency-controlled arrays as transmitters, a non-uniformly arranged frequency-controlled array can be used as the transmitter, while an equally arranged phased array can be used as the receiver (as shown in Figure 5).
The spacing between the elements of the uneven frequency-controlled array is set according to formula (7):
In the formula, denotes the spacing between the ith element. Assuming the baseband signal of the transmitter is, the signal transmitted by the ith element can be represented as:
Among them, the pulse width is considered. Correspondingly, in the case of uniform amplitude weighting, the directional pattern of the transmit array at a far-field point is:
In the formula, is the reference distance, and is a fixed constant. It is evident that the array factor amplitude is related to the distance parameter, but not to the azimuth angle parameter. Therefore, by combining phased array receivers that are only oriented with respect to the azimuth angle, a "point-shaped" transmit-receive array pattern can be formed (as shown in Figure 6).
4.2 Cognitive Radar Based on Frequency-Controlled Arrays
As shown in Figure 7, by adjusting the frequency increment of the adaptive updating, the radar receiver's output SINR (Signal-to-Interference-plus-Noise Ratio) is maximized, thereby achieving optimal clutter and interference suppression effects. The specific process is as follows:
1  
Initial frequency increment is used to calculate the corresponding receiver output SINR, and the change of SINR is feedback to the transmitter.
2  
If the SINR of the current iteration is better than that of the previous one, feedback information is sent; otherwise, it means [84]:
1  
Adjust the frequency increment parameters of the transmitter of the Frequency Controlled Array Radar according to the SINR comparison results:
In the formula, denotes the frequency incremental step for the nth time.
Through the above iterative processing, radar clutter and interference can be suppressed, and the performance of radar target detection and tracking can be improved.
4.3 RF-based Radar Absorption Technology
In recent years, there have been numerous research papers on radar radio frequency stealth:
•  
The document [106] proposes a radar beamforming method based on phase coding with low-probability of interception.
•  
The document [107] proposes the design of sampling interval for radar tracking considering radio frequency stealth, and the adaptive design method based on the minimum radiated power changes in target distance and radar cross-section.
•  
The literature [105] proposes an optimal search method for radar radio frequency stealth that minimizes energy consumption and detection probability errors, and designs a power grading criterion [108] to minimize sidelobe power. This is achieved by optimizing the array element switch settings through an improved multi-objective optimization particle swarm algorithm.
•  
[109] Establishes a detection optimization model based on the probability of detection, proposes optimal control schemes under two radiation energy control strategies, and comprehensively considers the radio frequency stealth capability and target discovery ability to establish a multi-objective optimization model for configuring radar operating parameters.
•  
The literature [110,111] proposes an MIMO radar search mode RF cloaking optimization algorithm based on resource management, which can adaptively control the number of antenna subarrays, signal duty cycle, beam dwell time, and search frame period when MIMO radar executes a search task.
•  
The document [112] proposes a method for designing radio frequency stealth radar waveforms based on noise modulation.
Most RF stealth technologies require narrow main beams and low sidelobe peaks in the antenna array, thus necessitating the use of an array antenna. However, most literature on RF stealth focuses on phased arrays. Although phased arrays can flexibly achieve spatial scanning of beams, their array pattern strength distribution is independent of directional distance, only achieving directional radiation rather than fixed point radiation. Frequency-controlled arrays can address this shortcoming [113].
Drawing from the LAWRENCE's low-intercept probability phased array method [106], it is possible to achieve a uniform distribution of instantaneous radiated power in the 2D space of distance and azimuth by special encoding of frequency offsets among the elements of the array. This approach also reduces the probability of intercepted signals being demodulated through phase modulation. At the receiving end, by decoding the beam phase and forming the received beam, the high-gain transmit array pattern can be restored. The effectiveness of this scheme has been verified in the literature (see Figure 8), but further research is needed on the optimization of array parameters for reception and suppression of sidelobe peak levels.
4.4 Traditional wireless communication transmitters with frequency-controlled arrays emit digital communication information modulation at baseband, then radiate through the antenna. In this mode, eavesdropping receivers receive signals from sidelobes that contain the same information as the desired signal, differing only in SNR. If the eavesdropping receiver is sufficiently sensitive, it can demodulate useful communication information from the received signal.
To address this issue, the literature [114] proposes directional modulation technology based on phased arrays to realize a physical layer secure communication system [115]. Figure 9 compares the transmission signals using directional modulation techniques with those using traditional baseband modulation signals: The transmitted signals using directional modulation have a constellation diagram consistent with the conventional baseband modulation signals in the desired direction, while other azimuth points exhibit phase and amplitude distortions. The expected receiver can demodulate the received signal just like decoding baseband modulation signals, while eavesdroppers, even if receiving a communication signal with similar power, suffer from communication error performance degradation due to signal constellation diagram distortions, and may even fail to demodulate useful information.
This directional modulation technique accomplishes baseband modulation at the radio frequency end, making the transmitted signal constellation dependent on the spatial orientation of the receiver. If phased arrays in directional modulation are replaced with frequency-controlled arrays, combined with the distance-dependent beamforming technology of frequency-controlled arrays, it is expected to achieve effective point-to-point secure communication, which has significant application potential in military communications [91]. Figure 10 shows the array directional pattern after directional modulation when the desired communication receiver is located at that time.
5. The urgent problems in Frequency-Controlled Array Radar As a new radar technology, the frequency-controlled array radar faces many key technical problems, and the following only discusses its issues in array signal processing:
5.1 The issue of waveform optimization design for frequency-controlled array radar aims to resolve the distance-azimuth coupling problem in the emission beams of the frequency-controlled array. A radar system based on a frequency-controlled array and MIMO hybrid array is required: divide the frequency-controlled array into multiple subarrays, where all elements within each subarray emit similar signals to those of phased arrays, while the signals between subarrays are similar to those of MIMO ([116]). This requires that the independent signals emitted between subarrays possess good orthogonality and meet the basic requirements of waveforms for conventional radar (large time-bandwidth product, constant envelope).
Although MIMO radar waveform design has received widespread attention, most literature designs from the perspective of statistical signal processing, which is difficult to implement in practice. Moreover, existing waveform designs often do not consider the issue of time-bandwidth product, and practical waveforms also need to have good blur function characteristics (including range and Doppler resolution), strong adjacent band interference suppression performance, and lower sidelobes of matched filtering. Therefore, adaptive design of large time-bandwidth product LPI (Low Probability of Interception) waveforms for radio frequency stealth background is extremely challenging but holds significant practical significance.
Additionally, similar to phased arrays, when the crosstalk in the transmitting channel is significant, corresponding supplementary processing is required. However, there is currently no literature on this issue involving frequency-controlled arrays.
5.2 The issue of beamforming in frequency-controlled array (FCA) transmission and reception requires a thorough exploration of the advantages and disadvantages of FCA compared to phased arrays, and the research on RF cloaking beamforming methods that depend on distance and azimuth angles. By integrating the array parameter optimization design of FCA with 2D (distance and azimuth angle) beamforming, the signal energy of the transmitted beam can be flexibly concentrated into the desired detection area. For example:
•  
By referencing the spread spectrum technology of wireless communication, it can reduce the peak power of signals by widening the beam width of transmission and thus decrease the probability of radar being intercepted.
•  
In the receiving end, the coherent demodulation method is adopted to comprehensively restore the high-gain equivalent transmit beam, ensuring that the radar detection performance is not affected.
•  
Through the closed-loop feedback control mechanism based on environmental perception, the adaptive processing of RF cloaking transmission and reception beamforming algorithm is realized.
However, this process requires solving multiple technical challenges: achieving array parameter optimization configuration for fixed-point RF stealth, array directional pattern synthesis, ultra-low sidelobe design and its adaptive implementation.
5.3 Adaptive Target Detection and Tracking Issues in Frequency-Controlled Array Radar Although the frequency-controlled array can provide target distance information, there is coupling between distance and azimuth angle response, making it impossible to accurately locate the target.
To this end, it is necessary to study effective methods for beamforming in frequency-controlled array radars, achieving joint estimation of distance and azimuth angles for targets in the desired detection area; furthermore, by integrating cognitive radar technology, an adaptive target detection and tracking system that is environmentally aware can be realized through a closed-loop feedback control mechanism based on environmental perception. This establishes a theoretical framework for fully adaptive frequency-controlled array radars. However, there are numerous key issues to be addressed in aspects such as covariance matrix estimation, adaptive detection and tracking of radar targets, and environmentally aware processing.
Particular attention should be paid to the fact that the directional pattern of a frequency-controlled array (FCA) changes over time, which increases the difficulty of estimating the covariance matrix of noise and interference. This introduces new research issues for adaptive processing of FCA radar signals.
This paper systematically introduces the concept, principles, and application characteristics of FCA radar. It comprehensively reviews relevant domestic and international research literature, summarizes its current state in terms of concepts, basic principles, implementation methods, and radar applications, analyzes its application prospects in new generation dual-base radar systems, cognitive radars, radio frequency stealth radars, and directional secure communication, and discusses urgent technical challenges such as waveform optimization design, transmitting and receiving beamforming, and adaptive target detection and tracking.
Frequency-controlled array radar is an extension of phased array radar technology. It not only possesses all the advantages of phased array radar but also compensates for the lack of distance-independent beam pointing in phased array radars. Therefore, despite the numerous key technical challenges faced by FCA radar, further in-depth research remains highly valuable.
End

## Images

![Frequency-controlled array radar: Concept, principles, and applications [with MATLAB code]](01.jpg)
![Frequency-controlled array radar: Concept, principles, and applications [with MATLAB code]](02.jpg)
![Frequency-controlled array radar: Concept, principles, and applications [with MATLAB code]](03.jpg)
![Frequency-controlled array radar: Concept, principles, and applications [with MATLAB code]](04.jpg)
![Frequency-controlled array radar: Concept, principles, and applications [with MATLAB code]](05.jpg)
![Frequency-controlled array radar: Concept, principles, and applications [with MATLAB code]](06.jpg)
![Frequency-controlled array radar: Concept, principles, and applications [with MATLAB code]](07.jpg)
![Frequency-controlled array radar: Concept, principles, and applications [with MATLAB code]](08.jpg)
![Frequency-controlled array radar: Concept, principles, and applications [with MATLAB code]](09.jpg)
![Frequency-controlled array radar: Concept, principles, and applications [with MATLAB code]](10.jpg)
![Frequency-controlled array radar: Concept, principles, and applications [with MATLAB code]](11.jpg)

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
