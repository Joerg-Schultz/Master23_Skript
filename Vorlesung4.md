# Data Science
## Cookiecutter

[for Data Science](https://drivendata.github.io/cookiecutter-data-science/)

`pip install cookiecutter`

Im Verzeichnis `C:\Users\BenutzerName\AppData` Ansicht -> Optionen -> OrdnerOptionen ändern -> Ansicht -> Versteckte 
Ordner und Dateien -> Ausgeblendete Dateien anzeigen.

auf Kommandozeile gehe in das Verzeichnis, in dem das Projekt liegen soll.

`C:\Users\Joerg\AppData\Roaming\Python\Python38\Scripts\cookiecutter https://github.com/drivendata/cookiecutter-data-science`

## Intellij
### Start git
(if not automatically started)

VCS -> Enable Version Control Integration

`<CTRL>-k` -> check git status

### Set Python interpreter
Open cookiecutter directory in Intellij. To set Python interpreter:

- File -> Project Structure
- Project Settings -> Project -> SDK
- Dropdown -> Add SDK -> Python SDK...
- Virtualenv Environment -> New environment -> OK

### Scientific mode

[Intellij Documentation](https://www.jetbrains.com/help/idea/matplotlib-support.html)

To switch to scientific mode, press 'shift' twice. Start Typing 'scientific' in search field. Set 'View: Scientific 
Mode' to 'On'

#### Documentation

#### Block Execution

Start a line with `# %% ` to make it an executable block. Think Jupyter Notebook but in the plain code. No Kernels 
needed.


## Analyse Data
### csv reader

### pandas

## Data

Pose Prediction by [DeepLabCut](https://www.mackenziemathislab.org/deeplabcut)

## Generate distribution

```python
# %% distribution of the likelihood of the nose predictions
# load stuff
import pandas as pd
import matplotlib.pyplot as plt

# %% read deeplabcut csv file and extract nose likelihood
file_path = "C:\\Users\\Joerg\\Documents\\Uni\\Master23\\master23_deeplabcut\\data\\external\\Charles_Session3_sideDLC_snapshot-700000.csv"
df = pd.read_csv(file_path, skiprows=2,usecols=[3])

df.rename(columns={df.columns[0]: 'Nose Likelihood'}, inplace=True)

# %% Plot the distribution
plt.hist(df, bins=20, edgecolor='k')
plt.xlabel('Likelihood')
plt.ylabel('Frequency')
plt.title('Distribution of Likelihood for Nose Predictions')
plt.show()


```
