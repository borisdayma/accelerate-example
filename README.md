## Instructions

* install `requirements.txt`

* Run the script

  * CPU or GPU if available: `python ./main.py`

  * force CPU: `python ./main.py --cpu`

  * multi GPU and single/multi TPU:
    * `accelerate config`
    * `accelerate launch ./main.py`

## Notes

* I don't think `wandb.init()` can be called in all processes

* `accelerator.is_local_main_process` can be used by Trainer's to know the main process

* `accelerate.wait_for_everyone()` can be used to ensure all other processes are done (for example before logging a model)
