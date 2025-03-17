# How to prepare environment?

## Download sources

Download all files from OneDrive.
Replays folder must be downloaded separately, 
because we have a size limitation for the downloading of several files on the OneDrive side.
After downloading replays folder from OneDrive you will have `replays.7z` file.

## Extract replays

Unzip replays from `replays.7z` by using 7z util.
As result, we must have replays inside replays folder: `data\replays`

## Prepare python environment

  - Setup Python (recommend 3.9 version)
    - Windows https://www.codewithharry.com/blogpost/install-python-in-windows/ (Download Python 3.9)
    - Linux https://linuxize.com/post/how-to-install-python-3-9-on-ubuntu-20-04/
  - Check that your python version is 3.9 `python --version`. If not, try using `python3.9` instead of `python`
  - Create virtual environment inside the projects directory by using command: ```python -m venv .venv```
    - Activate virtual environment
      - Linux: `source .venv/bin/activate`
      - Windows: `.\.venv\Scripts\Activate.ps1`)
  - Install `wg_replay_reader` from the submodule directory:
    ```bash
    cd ./wg_replay_reader
    pip install -e .
    pip install -r requirements.txt
    pip install -r requirements-obstacles.txt
    cd ..
    ```
  - [Optional] Install `replay_visualizer` from the submodule directory:
    ```bash
    cd ./replay-visualizer
    pip install -e .
    pip install -r requirements.txt
    cd ..
    ```

## How to use replay_tick_to_image?
- Setup `replay_visualizer`
- Example of usage is presented in `replay_tick_to_image.py` as a inner unit test (you can run it as `pytest` test):
```python
class TestReplayToImageFunctions:
    def test_get_image_from_replay(self):
        # ...
        pass
```
```bash
pip install pytest
pytest replay_tick_to_image.py
```


  
