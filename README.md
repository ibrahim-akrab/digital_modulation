# digital_modulation
Simulate the performance of different modulation schemes: BPSK, QPSK, FSK, QAM(16-64) in an AWGN environment.
## files organization
each modulation scheme is given a separate directory containing its model file and all its figures
### notes:
* All figures are in a `*.fig` format so they need to be opened in matlab so they can be more interactive, and they needn't be added here in the document at they will make it tedious and lengthy.
* the number at the end of the figure name (if exists) refers to the `Eb/No` value that has been used to get this output.
> I have used large numbers of `Eb/No` in some models just to show how it all converges to the ideal state where the demodulated signal is so close the modulated signal with a little bit of noise. The number of `Eb/No` can be seen as the robustness of the modulation scheme to random noise of the channel.
* all figures are generated using 1000 `samples per frame` (1000 point). 

## general steps to reproduce the ber graph
* run the **matlab** program.
* write `bertool` in matlab command window to open the tool that draws the ber vs Eb/No
* navigate to the `theoritical` tab.
* choose the modulation scheme that you want to draw its theoritical chart.
* set the Eb/No range to `-10:10` to draw it in that range.
* click the `plot` button and you should see it plotted in a graph.
* now navigate to `Monte Carlo` tab to draw the graph of the real model.
* choose the range as done before.
* write the `BER variable name` that is in the model.
> in all my models, I have names them just `ber`. 
* click `browse` and choose the model file in the format of `*.slx` that needs to be simulated.
* you should see the tool starting to draw the graph for you.

## general steps to reproduce the constellation diagrams
* run the **matlab** program.
* navigate the `current folder` panel to refer to the main project directory.
* open the directory of the model you want to simulate.
* open the model file `*.slx` (eg. `bpsk.slx`) by clicking on it.
* double click the `random integer generator` to make sure its `samples per frame` is set to `1000` to make sure we see many points to notice some pattern.
* set the value of `EbNo` from the workspace to the value that you want to simulate the `AWGN channel` at.
* press the `Run` button from the top bar to run the simulation.
* you should see the constellation diagrams popping up with the reference constellation points set to each specific model.

## BPSK

BPSK is a modulation scheme which shifts the phase of the output signal depending on the input. In this case, the input is binary and the zeros and ones are represented by two different phase states in the carrier signal. The phase difference is 180 degrees.

## QPSK

QPSK is a variation of PSK in which two bits are modulated at once, selecting one of four possible carrier phase shifts (0°, 90°, 180°, or 270°). QPSK doubles the bandwidth efficiency leaving more space for other users.

## FSK

FSK is a digital modulation scheme in which the frequency of the carrier signal varies according to the digital signal changes. The output of a FSK-modulated wave is high in frequency for a binary High input and is low in frequency for a binary Low input.

## QAM

QAM is a family of digital modulation methods widely used in modern telecommunications to transmit information. It conveys two digital bit streams, by changing (modulating) the amplitudes of two carrier waves, using the amplitude-shift keying (ASK) digital modulation scheme. The two carrier waves of the same frequency are out of phase with each other by 90°, a condition known as orthogonality and as quadrature. Being the same frequency, the modulated carriers add together, but can be coherently separated (demodulated) because of their orthogonality property.
In short, QAM can be seen as a way of encoding a message by changing the amplitude of each of the carrier signals to land somewhere on the constellation diagram so that it can be separated easily later.

