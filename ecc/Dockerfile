FROM hyperledger/fabric-ccenv-sgx:latest

ARG CC_NAME="ecc"
ARG CC_PATH="/usr/local/bin"
ARG CC_LIB_PATH=${CC_PATH}"/enclave/lib"

RUN mkdir -p ${CC_LIB_PATH}

ENV SGX_SDK=/opt/intel/sgxsdk
ENV LD_LIBRARY_PATH=${SGX_SDK}/sdk_libs:${CC_LIB_PATH}

copy ${CC_NAME} ${CC_PATH}/chaincode
copy enclave/lib/*.so ${CC_LIB_PATH}/

WORKDIR ${CC_PATH}
