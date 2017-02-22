# Homework_1

import numpy as np
import pandas as pd
from io import StringIO
import urllib2
url = 'http://archive.ics.uci.edu/ml/machine-learning-databases/postoperative-patient-data/post-operative.data'
raw_data = urllib2.urlopen(url)
names = ['L-Core', 'L-Surf', 'L-O2', 'L-BP', 'Surf-STBL', 'Core-STBL', 'BP-STBL', 'Comfort', 'Decision']
dataset = np.genfromtxt(raw_data, delimiter=",", names = names)
dataset = unicode(dataset)
df = pd.read_csv(StringIO(dataset), names = names)
df
