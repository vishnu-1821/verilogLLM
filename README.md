# verilogLLM

How to run this thing?
1. Use a venv 
2. Initialize a venv with “python3 venv virt”
3. source virt/bin/activate
4. pip freeze --local > requirements.txt -> this is to save requirements
5. Then install all the dependencies with “python3 -m virt pip3 install -r requirements.txt”
6. Once you’re done installing the dependencies, use one of the following deepspeed commands to start the training
      deepspeed --num_gpus 1y --num_nodes 1 run_clm.py --model_name_or_path=/home/abhijitp/codegen-350M-multi --save_steps=100 --per_device_train_batch_size=1 --learning_rate 2e-5 --num_train_epochs 1 --output_dir=CodeGen/codegen-350M-verilog-3-epochs --report_to 'wandb' --dataset_name code_snippets.csv --tokenizer_name /home/abhijitp/codegen-350M-multi --block_size 1024 --gradient_accumulation_steps 32 --do_train --do_eval --fp16 --overwrite_output_dir --deepspeed ds_config.json
7. Change all the directories and settings to match your files.

