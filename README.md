# Python_Portfolio
Code written for Bisc450-Computational Biology

## Analyzing Data
[3]: import numpy
[4]: numpy.loadtxt(fname = 'inflammation-01.csv', delimiter = ',')
[4]: array([[0., 0., 1., …, 3., 0., 0.],
[0., 1., 2., …, 1., 0., 1.],
[0., 1., 1., …, 2., 1., 1.],
…,
[0., 1., 1., …, 1., 1., 1.],
[0., 0., 0., …, 0., 2., 0.],
[0., 0., 1., …, 1., 1., 0.]])
[5]: data = numpy.loadtxt(fname = 'inflammation-01.csv', delimiter = ',')
[6]: print(type(data))
<class 'numpy.ndarray'>
[7]: print(data.shape)
(60, 40)
[9]: print('first value in data:', data[0,0])
first value in data: 0.0
[10]: print('middle value in data:', data[0,0])
middle value in data: 0.0
[11]: print(data[0:4, 0:10])
[[0. 0. 1. 3. 1. 2. 4. 7. 8. 3.]
[0. 1. 2. 1. 2. 1. 3. 2. 2. 6.]
[0. 1. 1. 3. 3. 2. 6. 2. 5. 9.]
[0. 0. 2. 0. 4. 2. 2. 1. 6. 7.]]
[13]: print(data[5:10, 0:10])
1
[[0. 0. 1. 2. 2. 4. 2. 1. 6. 4.]
[0. 0. 2. 2. 4. 2. 2. 5. 5. 8.]
[0. 0. 1. 2. 3. 1. 2. 3. 5. 3.]
[0. 0. 0. 3. 1. 5. 6. 5. 5. 8.]
[0. 1. 1. 2. 1. 3. 5. 3. 5. 8.]]
[14]: small = data[:3, 36:]
[15]: print('small is:')
small is:
[17]: print (small)
[[2. 3. 0. 0.]
[1. 1. 0. 1.]
[2. 2. 1. 1.]]
[21]: maxval, minval, stdval = numpy.amax(data), numpy.amin(data), numpy.std(data)
[22]: print(maxval)
print(minval)
print(stdval)
20.0
0.0
4.613833197118566
[23]: maxval = numpy.amax(data)
minval = numpy.amin(data)
stdval = numpy.std(data)
[24]: print(maxval)
print(minval)
print(stdval)
20.0
0.0
4.613833197118566
[25]: print('maximum inflammation:', maxval)
print('minimum inflammation:', minval)
print('standard deviation:', stdval)
maximum inflammation: 20.0
minimum inflammation: 0.0
standard deviation: 4.613833197118566
2
[26]: # Sometimes we want to look at variations in statistical values, such as␣
,→maximum inflammation per patient,
# or average for one day
patient_0 = data[0, :] # 0 ont the first axis (rows), everything on the second␣
,→(columns)
print('maximum inflammation for patient 0:', numpy.amax(patient_0))
maximum inflammation for patient 0: 18.0
[27]: print('maximum inflammation for patient 2:', numpy.amax(data[2, :]))
maximum inflammation for patient 2: 19.0
[28]: print(numpy.mean(data, axis = 0))
[ 0. 0.45 1.11666667 1.75 2.43333333 3.15
3.8 3.88333333 5.23333333 5.51666667 5.95 5.9
8.35 7.73333333 8.36666667 9.5 9.58333333 10.63333333
11.56666667 12.35 13.25 11.96666667 11.03333333 10.16666667
10. 8.66666667 9.15 7.25 7.33333333 6.58333333
6.06666667 5.95 5.11666667 3.6 3.3 3.56666667
2.48333333 1.5 1.13333333 0.56666667]
[29]: print(numpy.mean(data, axis = 0).shape)
(40,)
[30]: print(numpy.mean(data, axis = 1))
[5.45 5.425 6.1 5.9 5.55 6.225 5.975 6.65 6.625 6.525 6.775 5.8
6.225 5.75 5.225 6.3 6.55 5.7 5.85 6.55 5.775 5.825 6.175 6.1
5.8 6.425 6.05 6.025 6.175 6.55 6.175 6.35 6.725 6.125 7.075 5.725
5.925 6.15 6.075 5.75 5.975 5.725 6.3 5.9 6.75 5.925 7.225 6.15
5.95 6.275 5.7 6.1 6.825 5.975 6.725 5.7 6.25 6.4 7.05 5.9 ]
