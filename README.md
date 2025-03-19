# Bayes Adaptive Monte Carlo Tree Search for Offline Model-based Reinforcement Learning

- Please set up the virtual environment according to [OfflineRL-Kit](https://github.com/yihaosun1124/OfflineRL-Kit).

- Please download the dynamics/reward models and hyperparameter files from [data](https://drive.google.com/drive/folders/1XnyMbwJUrsW-r0DQhCzJUkKpBNmrS2KW?usp=sharing) to the folder 'data'.

- The main metric is the 'eval/normalized_episode_reward', which is recorded in the 'policy_training_progress.csv' files which will be automatically generated in the 'log' folder. We have provided a script to calculate the scores in Table 10 based on the raw data in the csv files. You can simply run:
    ```bash
    python csv_calculator.py
    ```

- How to run BA-MCTS to get the corresponding results in Table 10:
    ```bash
    python run_bambrl.py
    ```
    - Please change the variable "load_path_id" in Line 361 of the file 'run_bambrl.py' to train a policy for a specific env under a certain random seed.
    - **You may need to compile the mcts component (written in C++) to get the program running:**
        ```bash
        cd offlinerlkit/utils/ctree
        python setup.py build_ext --inplace
        ```

- How to run MOBILE to get the corresponding results in Table 10:
    ```bash
    python run_mobile.py
    ```
    - Please change the variable "load_path_id" in Line 277 of the file 'run_mobile.py' to train a policy for a specific env under a certain random seed.