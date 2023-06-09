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

From the parameters to train.py you can see that we are using two multi-head attention layers (--n_layer=2) and embeddings of size 32 (--n_embd=32). This results in a parameter count of 0.03M or 30K as can be seen from sample-out. The original nanoGPT uses 0.8M parameters to produce the same loss (1.88). Our approach uses only 3.75% of the original parameter count. Also, note that we are using a learning rate of 0.1 and no rate decay.

Our results show that our approach passes information better across layers, converges better and has better numerical stability compared to the original nanoGPT. 

The larger your model is, the more we can save for you, in most cases. [Contact us](https://www.eskns.com/#contact) to see how we can help you!
