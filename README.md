# Decoding-Text-Message

This repository decodes an English sentence from a long sequence of non-text observations. To do so, the code implements the same basic algorithm used in most engines for automatic speech recognition.  In a speech recognizer, these observations would be derived from real-valued measurements of acoustic waveforms.  Here, for simplicity, the observations only take on binary values, but the high-level concepts are the same.

Consider a discrete HMM with $n=27$ hidden states $S_t \in \\{1,2,\ldots,27\\}$ and binary observations $O_t \in \\{0,1\\}$. The data files contain parameter values for the initial state distribution $\pi_i = P(S_1 = i)$, the transition matrix $a_{ij} = P(S_{t+1} = j|S_t = i)$, and the emission matrix $b_{ik} = P(O_t = k|S_t = i)$, as well as a long bit sequence of $T = 430000$ observations.

The Viterbi algorithm is used to compute the most probable sequence of hidden states conditioned on this particular sequence of observations.

## Hidden Message

<div align="center">
  
![image](https://github.com/aayushg97/Decoding-Text-Message/assets/30308551/0c7f317c-bf59-45ff-8247-3c73b025448b)

</div>

Suppose that the hidden states $\\{1,2,\ldots,26\\}$ represent the letters $\\{{\tt a,b,\ldots,z}\\}$ of the English alphabet, and suppose that hidden state 27 encodes a space between words.  The most probable sequence of hidden states (ignoring repeated elements) reveals a famous quotation, as well as an interesting commentary on our times.

$\textbf{A house divided against itself cannot stand}$
