# Mauritius Sea Cable

The aim of this project is to provide a simple graphical user interface to show the Health Status of submarine cables connected to Mauritius.

![ProjectImage](https://github.com/MrSunshyne/mauritius-sea-cable/raw/master/public/images/og-image.jpg)

**[View the Live Website](https://mrsunshyne.github.io/mauritius-sea-cable/)**

> This project is inspired by the beautiful website [baliseacable.com](baliseacable.com)

## Data Source

The data source is yet to be made available.
It is expected to be in the following format :

```json
// file: all-servers.json
{
    LION : <SpeedtestResult>,
    MARS: <SpeedtestResult>,
    SAFE1:<SpeedtestResult>,
    SAFE2:<SpeedtestResult>,
    SAFE3:<SpeedtestResult>
}
// Where Speedtest result has the following signature
Interface SpeedtestResult {
    timestamp: '',
    upload: '',
    download: '',
    ping: ''
}
```

## Project setup

```bash
git clone git@github.com:reallyaditya/speedtest-mauritius.git
npm install
```

**N.B. Make sure to clone the repo using SSH**

### Compiles and hot-reloads for development

```bash
npm run serve
```

### Compiles and minifies for production

```bash
npm run build
```

### Python 3 Dependencies

- Official Speedtest-cli from [Ookla](https://www.speedtest.net/apps/cli)

### Setting up GitHub Repo

The JSON results obtained are synced to a GitHub repo and then fetched to display the latter. To set up the Python script to push to your GitHub repo, follow the instructions below:

- Change the speed test server codes to the ones you want in `speedtest.py`

```python
server_dict = {'LION': {'reunion': 24492, 'madagascar': 7755},
               'SAFE': {'india': 24682, 'south_africa': 1285, 'malaysia':12544},
               'MARS': {'rodrigues': 27454}
               }
```

- You can get a list of nearby speed test servers and their codes by running the command below:

```bash
speedtest --servers
```

- Having cloned the repo using SSH, change the path of the project directory accordingly in the `speedtest.py` script.

```python
77 os.chdir('absolute_path_to_project_directory')
```

- Just run the `speedtest.py` script to do a speed test and push the results to your GitHub repo.
