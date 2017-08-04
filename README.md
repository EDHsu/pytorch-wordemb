# pytorch-wordemb
Load pretrained word embeddings (word2vec, glove format) into torch.FloatTensor for PyTorch



## Install
PyTorch required. Please follow the official site installation guide.
```
pip install cffi
pip install torchwordemb
```


## Usage

```python
import torchwordemb
```

### torchwordemb.load_word2vec_bin(path)
read word2vec binary-format model from `path`.

returns `(vocab, vec)`
  - `vocab` is a `dict` mapping a word to its index.
  - `vec` is a  `torch.FloatTensor` of size `V x D`, where `V` is the vocabulary size and `D` is the dimension of word2vec.
  
```python
# vocab, vec = torchwordemb.load_word2vec_bin("/path/to/word2vec/model.bin")

vocab, vec = torchwordemb.load_word2vec_bin("./resource/word2vec.test.bin")

print(vec.size())
print(vec[vocab["user"]])

# print(vec[ w2v.vocab["apple"] ] )
```

### torchwordemb.load_word2vec_text(path)
read word2vec text-format model from `path`.
```python
import torchwordemb

# load FT format (.vec)
vocab, vec = torchwordemb.load_word2vec_text("/path/to/file.vec")

print(vec.size())
print(vec[vocab["老鼠會"]])
```

### torchwordemb.load_glove_text(path)
read GloVe text-format model from `path`.
