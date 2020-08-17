# FedML APIs (core) Introduction
FedML-core separates the communication and the model training into two core components. The first is the communication protocol component (labeled as \textit{distributed} in the figure). It is responsible for low-level communication among different works in the network. The communication backend is based on MPI (message passing interface) \footnote{\url{https://pypi.org/project/mpi4py/}}. We consider adding more backends as necessary, such as RPC (remote procedure call). Inside the communication protocol component, a \texttt{TopologyManager} supports the flexible topology configuration required by different distributed learning algorithms. 
The second is the on-device deep learning component, which is built based on the popular deep learning framework PyTorch or TensorFlow. For flexibility, there is no restriction on the framework for this part. Users can implement trainers and coordinators according to their needs. In addition, low-level APIs support security and privacy-related algorithms (introduced in Section \ref{sec:pi}).