# FPGA CNN

FPGA implementation of [Cellular Neural Network](http://www.scholarpedia.org/article/Cellular_neural_network) (CNN)  
![CNN formula](https://github.com/dem123456789/FPGA-CNN/blob/master/Fomula.PNG "CNN")

## Initialization
#### CNN 
`CNN.v` is Top-level design with initialization for A, B, I template  
`SixteenbySixteen.java` generates Verilog code for 16x16 layer module [sixteenbysixteen.v](https://github.com/dem123456789/FPGA-CNN/blob/master/Quartus/sixteenbysixteen.v)
#### Default 
[CornerDetection](http://en.wikipedia.org/wiki/Corner_detection)  
Other available templates in [here](https://github.com/dem123456789/FPGA-CNN/blob/master/Template_library_v3.1.pdf)
 
## Instruction

1. Change the `size` variable in SixteenbySixteen can generate different dimension module  
2. Contain a 4x4 layer module [fourbyfour.v](https://github.com/dem123456789/FPGA-CNN/blob/master/Quartus/fourbyfour.v)  
3. fourbyfour.v and sixteenbysixteen.v use one multiplier and two adders in calculation of equation 1  
4. Any files ended with 18mul are associated with the version using 18 multipliers and finishing equation 1 calculation in one clock cycle  
5. Top level design CNN.v and CNNfourbyfour.v is shared with both versions  
6. Change the module link, for example, sixteenbysixteen u1 to sixteenbysixteen18mul u1  
will change to the version which does equation 1 calculation in one clock cycle
7. Eq1 Initial folder contains the work by Sangeetha J. who completes using one multiplier and one adder to calculate template A times output Y or template B times input U. The default version which using one multiplier and two adders in calcualtion of equation 1 is based on her contribution

#### Default 
`size = 16;`  
CNN.v is using sixteenbysixteen.v
## Contributing

1. Fork
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

## Source

*SP-CNN: A Scalable and Programmable CNN-based Accelerator*,
Dilan Manatunga, Hyesoon Kim, Saibal Mukhopadhyay
GOMACTech, Mar. 2015 

## Credits

*Enmao Diao  
Ria Gupte  
Hyesoon Kim    
Joshua Lee    
Sangeetha J.*

## License

The MIT License (MIT)

Copyright (c) [2015] [Enmao Diao]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
