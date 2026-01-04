# Al-Li-Binary-Phase-Diagram
using blocklund's COST507 and PyCalphad


Code as follows:

%matplotlib inline
import matplotlib.pyplot as plt
from pycalphad import Database, binplot
import pycalphad.variables as v

db_alli = ('COS507-modified.tbd')
my_phases_alli = ['FCC_A1', 'ALLI', 'AL2LI3', 'AL4LI9', 'LIQUID', 'BCC_A2']
binplot(db_alli, ['AL', 'LI', 'VA'], my_phases_alli, {v.X('LI'):(0,1,0.001), v.T: (100,1000,1), v.P:101325, v.N: 1},plot_kwargs={'tielines':False})

plt.tight_layout()
plt.savefig('ALLI_phase_diagram.pdf', bbox_inches='tight')
plt.show()
