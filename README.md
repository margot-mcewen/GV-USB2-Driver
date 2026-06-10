GV-USB2 Linux Driver
====================

A linux driver for the IO-DATA GV-USB2 SD capture device, modified to work with more recent versions of kernel.

> [!CAUTION]
> I don't know what I'm doing!

I have removed two lines from `gvusb2-vl2.c` on the basis that they are now deprecated.

``` diff
static const struct vb2_ops gvusb2_vb2_ops = {
	.queue_setup     = gvusb2_vb2_queue_setup,
	.buf_queue       = gvusb2_vb2_buf_queue,
	.start_streaming = gvusb2_vb2_start_streaming,
	.stop_streaming  = gvusb2_vb2_stop_streaming,
-	.wait_prepare    = vb2_ops_wait_prepare,
-	.wait_finish     = vb2_ops_wait_finish,
};
```

This seems to work, but as I say, I don't know what I'm doing, and this might be a bad idea.

🙈
