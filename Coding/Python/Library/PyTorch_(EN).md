# PyTorch Functions by Expertise Level

## `Introduction`
**PyTorch** is one of the most powerful machine learning and deep learning libraries:

- ✅ Building neural network models
- ✅ Automatic gradient calculation (Autograd)
- ✅ Full GPU/TPU support

## `Core Benefits`

| Feature | Explanation |
|---------|-------------|
| ⚡ High Performance | Accelerated operations using GPU |
| 🧠 High Flexibility | Dynamic models using Dynamic Computation Graph |
| 📊 Python Integration | Seamless integration with Python scientific libraries |

---
<br><br><br>

## `Beginner Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `torch.tensor(data)` | Create tensor | `torch.tensor([1, 2, 3])` | tensor [1, 2, 3] |
| `torch.zeros(size)` | Zero-filled tensor | `torch.zeros(2, 3)` | 2x3 zero tensor |
| `torch.ones(size)` | One-filled tensor | `torch.ones(2)` | tensor [1, 1] |
| `torch.rand(size)` | Random-valued tensor | `torch.rand(2, 2)` | 2x2 tensor with values 0-1 |
| `tensor.shape` | Tensor shape | `x.shape` | Dimensions (2, 3) |
| `tensor.dtype` | Tensor data type | `x.dtype` | torch.float32 |
| `tensor.to(device)` | Move tensor to device | `x.to('cuda')` | Tensor on GPU |
| `torch.add(x, y)` | Add tensors | `torch.add(x, y)` | Sum of x and y |
| `torch.mm(x, y)` | Matrix multiplication | `torch.mm(x, y)` | Matrix product |
| `torch.sum(x)` | Tensor sum | `torch.sum(x)` | Total sum |

---
<br><br><br>

## `Intermediate Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `torch.nn.Linear(in, out)` | Linear layer | `nn.Linear(10, 5)` | 10 → 5 layer |
| `torch.nn.Conv2d(in, out, k)` | Convolutional layer | `nn.Conv2d(3, 16, 3)` | 3x3 conv layer |
| `torch.nn.ReLU()` | ReLU activation | `nn.ReLU()` | Activation function |
| `torch.optim.SGD()` | SGD optimizer | `optim.SGD(model.parameters(), lr=0.01)` | Optimizer object |
| `nn.CrossEntropyLoss()` | Loss function | `nn.CrossEntropyLoss()` | Loss function |
| `model.eval()` | Evaluation mode | `model.eval()` | Disables Dropout/BatchNorm |
| `torch.save(model, path)` | Save model | `torch.save(model, 'model.pth')` | Model file |
| `torch.load(path)` | Load model | `torch.load('model.pth')` | Loaded model |
| `DataLoader(dataset, batch)` | Data loader | `DataLoader(ds, batch_size=32)` | Data loader |
| `torchvision.transforms` | Image transforms | `transforms.Compose([...])` | Image transforms |

---
<br><br><br>

## `Advanced Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `torch.autograd.grad()` | Compute gradients | `torch.autograd.grad(output, input)` | Output gradients |
| `@torch.jit.script` | Convert to TorchScript | `@torch.jit.script def foo(x):` | Optimized model |
| `torch.distributed` | Distributed training | `torch.distributed.init_process_group()` | Distributed setup |
| `torch.nn.Parameter()` | Model parameter | `nn.Parameter(torch.rand(10))` | Learnable parameter |
| `torch.nn.utils.clip_grad_` | Gradient clipping | `clip_grad_norm_(model.parameters(), 1.0)` | Clipped gradients |
| `torch.onnx.export()` | Export to ONNX | `torch.onnx.export(model, ...)` | ONNX model |
| `torch.jit.trace()` | Model tracing | `torch.jit.trace(model, example_input)` | Traced model |
| `torch.nn.DataParallel` | Parallel training | `DataParallel(model)` | Parallel model |
| `torch.cuda.amp` | Mixed precision | `autocast(enabled=True)` | Faster training |
| `torch.nn.functional` | NN functions | `F.interpolate(x, scale_factor=2)` | Image resizing |

---
<br><br><br>

## `Expert Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `torch.autograd.Function` | Custom function | `class MyFunc(Function): ...` | Custom operation |
| `torch.nn.Module` | Custom model | `class MyModel(nn.Module): ...` | Custom model |
| `torch._C` | C++ interface | `torch._C._jit_pass_constant_propagation` | Low-level access |
| `torch.utils.benchmark` | Performance timing | `Timer(stmt='x + y', ...)` | Execution timing |
| `torch.profiler` | Performance analysis | `torch.profiler.profile(...)` | Performance profile |
| `torch.utils.tensorboard` | Training visualization | `SummaryWriter()` | Training logging |
| `torch.distributions` | Probability distributions | `distributions.Normal(0, 1)` | Probability distribution |
| `torch.sparse` | Sparse tensors | `torch.sparse_coo_tensor(...)` | Sparse tensors |
| `torch.jit.script_if_tracing` | Tracing optimization | `@script_if_tracing def foo(x):` | Tracing optimization |
| `torch.overrides` | Behavior modification | `@overrides.handle_torch_function` | PyTorch behavior override |