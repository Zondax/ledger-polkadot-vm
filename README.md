[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

While we recommend setting up your enviroment as described in [here](https://github.com/ZondaX/ledger-polkadot#building), this repository provides a complete and ready reproducible build environment based on a virtual machine setup.

# Installing dependencies

- Install vagrant
    https://www.vagrantup.com/

- Install ansible

    - If you are running Ubuntu, you can use `sudo apt install ansible`
    - For other OSs please check ansible documentation.

- Install virtualbox
    https://www.virtualbox.org/wiki/Downloads

# Generate development machine
- Clone this repository

- Start virtual machine
    ```
    vagrant up
    ```

# Use the virtual machine

- Connect to your virtual machine

    ```
    vagrant ssh
    ```
- As an example, to build the ledger app:
    ```
    cd ledger-polkadot
    make
    ```
  
  for other tasks steps, please follow the instructions [here](https://github.com/ZondaX/ledger-polkadot#building)


# Destroy virtual machine

- If you want to start from scratch or remove/delete everything, run:

    ```
    vagrant destroy
    ```
