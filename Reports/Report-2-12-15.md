# Contrast Set Learning

## This week's progress..
- Fixed CART, CART was a Classifier, now is a regressor. No difference..
- Rewrote [Planning.py](https://github.com/ai-se/Defect-Prediction/blob/master/SOURCE/Planning.py) to encorporte ideas from our discussion this week.

### Modifications to Contrast Set Learning..
1 . [Issue \#1](https://github.com/ai-se/Defect-Prediction/issues/1): Use 'alpha to find better nodes'
2. [Issue \#2](https://github.com/ai-se/Defect-Prediction/issues/2): Too many Potential Contrast Sets.
3. [Issue \#3](https://github.com/ai-se/Defect-Prediction/issues/3): Thresholds in CART for better defect prediction.
More ideas in [Issues](https://github.com/ai-se/Defect-Prediction/issues?q=)

### The Quartiles 
```

rank ,         name ,    med   ,  iqr 
----------------------------------------------------
   1 ,       lucene ,    -24.34  ,  0.00 (*              |              ), -24,  -24,  -24
   1 ,        log4j ,    -20.69  ,  0.00 (  *            |              ), -20,  -20,  -20
   1 ,          poi ,    -11.96  ,  0.00 (       *       |              ), -11,  -11,  -11
   1 ,        camel ,    -9.70  ,  0.00 (        *      |              ), -9,  -9,  -9
   1 ,       xerces ,    -9.45  ,  0.00 (         *     |              ), -9,  -9,  -9
   1 ,        jedit ,    -7.18  ,  0.00 (          *    |              ), -7,  -7,  -7
   2 ,      forrest ,    0.00  ,  0.00 (              *|              ), 0,  0,  0
   2 ,     velocity ,    5.56  ,  0.00 (               |  *           ), 5,  5,  5
   2 ,          ivy ,    6.32  ,  0.00 (               |  *           ), 6,  6,  6
   2 ,      synapse ,    8.57  ,  0.00 (               |    *         ), 8,  8,  8
   2 ,       pbeans ,    10.00  ,  0.00 (               |    *         ), 10,  10,  10
   2 ,        xalan ,    13.10  ,  0.00 (               |      *       ), 13,  13,  13
   2 ,          ant ,    25.00  ,  0.00 (               |             *), 25,  25,  25
```

### Raw Results
```
## ant
Gain =  31.71 %
Gain =  27.12 %
Gain =  40.65 %
Gain =  33.61 %
Gain =  6.25 %
Gain =  31.45 %
Gain =  18.35 %
Gain =  26.79 %
Gain =  40.48 %
Gain =  25.00 %
## camel
Gain =  1.27 %
Gain =  4.17 %
Gain =  -7.73 %
Gain =  -21.14 %
Gain =  -7.90 %
Gain =  -16.89 %
Gain =  7.42 %
Gain =  -12.33 %
Gain =  -11.83 %
Gain =  -9.70 %
## forrest
Gain =  0.00 %
Gain =  -133.33 %
Gain =  25.00 %
Gain =  0.00 %
Gain =  0.00 %
Gain =  0.00 %
Gain =  14.29 %
Gain =  16.67 %
Gain =  -75.00 %
Gain =  0.00 %
## ivy
Gain =  -25.00 %
Gain =  -5.49 %
Gain =  -4.26 %
Gain =  -6.32 %
Gain =  -36.90 %
Gain =  0.00 %
Gain =  9.78 %
Gain =  -4.26 %
Gain =  7.87 %
Gain =  6.32 %
## jedit
Gain =  -32.79 %
Gain =  -3.20 %
Gain =  -6.63 %
Gain =  -14.50 %
Gain =  17.27 %
Gain =  -12.44 %
Gain =  -10.41 %
Gain =  14.55 %
Gain =  11.35 %
Gain =  -7.18 %
## log4j
Gain =  -34.55 %
Gain =  -5.80 %
Gain =  -23.64 %
Gain =  -1.43 %
Gain =  -2.90 %
Gain =  -12.07 %
Gain =  -15.52 %
Gain =  -28.00 %
Gain =  -7.25 %
Gain =  -20.69 %
## lucene
Gain =  -25.90 %
Gain =  -28.86 %
Gain =  -28.87 %
Gain =  -16.44 %
Gain =  -22.07 %
Gain =  -42.55 %
Gain =  -16.77 %
Gain =  -23.45 %
Gain =  -21.53 %
Gain =  -24.34 %
## pbeans
Gain =  -82.35 %
Gain =  -5.00 %
Gain =  -22.22 %
Gain =  -11.11 %
Gain =  -5.26 %
Gain =  0.00 %
Gain =  -10.53 %
Gain =  0.00 %
Gain =  -12.00 %
Gain =  10.00 %
## poi
Gain =  -3.18 %
Gain =  18.95 %
Gain =  10.58 %
Gain =  -11.26 %
Gain =  -10.12 %
Gain =  -3.65 %
Gain =  -15.57 %
Gain =  6.49 %
Gain =  3.65 %
Gain =  -11.96 %
## synapse
Gain =  -8.82 %
Gain =  34.29 %
Gain =  38.24 %
Gain =  29.41 %
Gain =  14.71 %
Gain =  -20.59 %
Gain =  -11.43 %
Gain =  25.71 %
Gain =  21.21 %
Gain =  8.57 %
## velocity
Gain =  0.00 %
Gain =  6.32 %
Gain =  8.89 %
Gain =  -17.24 %
Gain =  5.75 %
Gain =  1.18 %
Gain =  -16.67 %
Gain =  -1.09 %
Gain =  12.77 %
Gain =  5.56 %
## xalan
Gain =  40.79 %
Gain =  -7.21 %
Gain =  -7.63 %
Gain =  9.20 %
Gain =  8.30 %
Gain =  4.07 %
Gain =  4.30 %
Gain =  9.16 %
Gain =  -4.53 %
Gain =  13.10 %
## xerces
Gain =  -20.18 %
Gain =  3.48 %
Gain =  -21.24 %
Gain =  -27.12 %
Gain =  14.96 %
Gain =  -35.61 %
Gain =  -12.93 %
Gain =  -2.46 %
Gain =  -12.73 %
Gain =  -9.45 %
```