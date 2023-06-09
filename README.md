# eks-nanoGPT
Raw results after incorporating our patent-pending and proprietary technologies into the [nanoGPT](https://github.com/karpathy/nanoGPT) project.

We incorporated our version of layers that use linear operators to produce the results shared here. We used the command:

<code>python train.py config/train_shakespeare_char.py --device=cpu --compile=False --eval_iters=20 --log_interval=1 --block_size=48 --batch_size=12 --n_layer=2 --n_head=4 --n_embd=32 --max_iters=4000 --lr_decay_iters=4000 --dropout=0.0 --learning_rate=1e-1 --min_lr=1e-2 > output-n_embd32
</code>

to produce the file output-n_embd32.

Then, we used the command:

<code> python sample.py --out_dir=out-shakespeare-char --device=cpu > sample-output
</code>

Both train.py and sample.py are from the original [nanoGPT](https://github.com/karpathy/nanoGPT) project.
