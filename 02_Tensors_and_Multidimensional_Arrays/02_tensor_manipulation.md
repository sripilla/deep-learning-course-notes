# 🔧 Tensor Manipulation in PyTorch (L2 | CO1)

---

## 🔹 1. What is Tensor Manipulation?

Tensor manipulation refers to:

* Changing shape
* Rearranging dimensions
* Resizing data
* Transforming tensor structure

👉 Essential for preparing data for neural networks

---

## 🔹 2. Creating Tensors

```python
import torch

x = torch.arange(0, 10)
print(x)
```

---

## 🔹 3. Reshaping Tensors

### ✔ reshape()

Changes tensor shape without changing data

```python
x = torch.arange(0, 10)
y = x.reshape(2, 5)
print(y)
```

---

## 🔹 4. view() vs reshape()

### ✔ view()

* Returns a new view of tensor
* Requires contiguous memory

```python
x = torch.arange(0, 10)
y = x.view(2, 5)
```

### ✔ reshape()

* More flexible
* Works even if memory is not contiguous

👉 Use `reshape()` when unsure

---

## 🔹 5. Flattening Tensors

Converts multi-dimensional tensor → 1D

```python
x = torch.rand(2, 3)
y = x.flatten()
print(y)
```

---

## 🔹 6. Adding and Removing Dimensions

### ✔ unsqueeze()

Adds a dimension

```python
x = torch.tensor([1,2,3])
y = x.unsqueeze(0)
print(y.shape)
```

### ✔ squeeze()

Removes dimensions of size 1

```python
x = torch.rand(1, 3, 1)
y = x.squeeze()
print(y.shape)
```

---

## 🔹 7. Permuting Dimensions

Reorders dimensions of tensor

```python
x = torch.rand(2, 3, 4)
y = x.permute(2, 0, 1)
print(y.shape)
```

---

## 🔹 8. Transpose

Swaps dimensions

```python
x = torch.rand(2, 3)
y = x.T
print(y.shape)
```

---

## 🔹 9. Concatenation

Combines tensors

### ✔ torch.cat()

```python
a = torch.rand(2, 3)
b = torch.rand(2, 3)

c = torch.cat((a, b), dim=0)
print(c.shape)
```

---

## 🔹 10. Stacking

Creates new dimension

```python
a = torch.rand(2, 3)
b = torch.rand(2, 3)

c = torch.stack((a, b), dim=0)
print(c.shape)
```

---

## 🔹 11. Key Differences

| Operation | Purpose              |
| --------- | -------------------- |
| reshape   | Change shape         |
| view      | Memory-based reshape |
| flatten   | Convert to 1D        |
| unsqueeze | Add dimension        |
| squeeze   | Remove dimension     |
| cat       | Merge tensors        |
| stack     | Add new dimension    |

---

## ⚠️ Common Mistakes

* Using `view()` on non-contiguous tensors
* Shape mismatch during concatenation
* Confusing `cat()` vs `stack()`

---

## 🧾 Quick Summary

* Tensor manipulation = restructuring data
* reshape() is safest
* unsqueeze/squeeze handle dimensions
* cat vs stack → VERY IMPORTANT

---
