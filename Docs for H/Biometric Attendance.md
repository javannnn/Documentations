Here is a breakdown of the steps to use the tool:

1.  Pre-requisites: The tool requires Python 3.6 or higher to be installed on your system.
    
2.  Usage: The tool can be used in two ways: through the GUI or the CLI. The GUI has a simple form to guide you through the process, while the CLI requires some technical knowledge.
    
3.  GUI: To use the GUI, download the biometric-attendance-sync-tool-[version]-[distribution].zip file from the releases folder and unzip it. Then, run the attendance-sync file from the folder. This should set up all dependencies automatically and start the GUI.
    
4.  CLI: To use the CLI, navigate to the biometric-attendance-sync-tool folder and run the following commands:
    
```
python3 -m venv venv
```

```
source venv/bin/activate
```
  
```
pip install -r requirements.txt
```
5.  Setup Configurations:

-   make a copy of the local_config.py.template file and rename it to local_config.py.
-   Fill in the relevant sections in this file as per the comments in it.
-   You will need to provide ERPNext connection details (API Key, API Secret, URL, Version) and operational details of the script (pull frequency, logs directory, import start date)

6.  Run Script:

-   Run the script using

```
python3 erpnext_sync.py
```

7.  Windows:

-   install pywin32 using pip install pywin32
-   install the windows service using `python erpnext_sync_win.py install`
-   update the installed windows service using `python erpnext_sync_win.py update`
-   stop the windows service using `net stop ERPNextBiometricPushService`

8.  Build Executable file for GUI:

-   Activate virtual environment
-   navigate to the repository folder (where gui.py located) by 
```
cd biometric-attendance-sync-tool
```

-   Run the following commands:
```
pip install pyinstaller
```
```
python -m PyInstaller --name="attendance-sync" --windowed --onefile gui.py
```