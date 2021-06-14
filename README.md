## Instructions

* install `requirements.txt`

* Run the script

  * on CPU or GPU if available: `python ./main.py`

  * force CPU: `python ./main.py --cpu`

  * on multi GPU and single/multi TPU:
    * set config with `accelerate config`
    * launch with `accelerate launch ./main.py`

## Notes

* I don't think `wandb.init()` can be called in all processes

* `accelerator.is_local_main_process` (one per node) or `accelerator.is_main_process` (one only) can be used by Trainer's to know the main process (local or global)

* `accelerate.wait_for_everyone()` can be used to ensure all other processes are done (for example before logging a model)
