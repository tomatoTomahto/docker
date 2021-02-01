# The base image should correspond to the DBR runtime (ie. DBR 7.x runs on Ubuntu 18.04) - see here: https://docs.microsoft.com/en-us/azure/databricks/release-notes/runtime/7.6#system-environment 
FROM ubuntu:18.04 
 
# These are all requirements needed for a custom image - see here: https://docs.microsoft.com/en-us/azure/databricks/clusters/custom-containers#requirements 
RUN apt-get update \
  && apt-get install --yes software-properties-common \
  && add-apt-repository ppa:deadsnakes/ppa \
  && apt-get update \ 
  && apt-get install --yes \
    openjdk-8-jdk \ 
    iproute2 \ 
    bash \ 
    sudo \ 
    coreutils \
    procps \
    libcurl4-openssl-dev \
    libssl-dev \
    build-essential \
    libpython3.7-dev \
    python3-dev \
    python3.7 \
    virtualenv \ 
  && /var/lib/dpkg/info/ca-certificates-java.postinst configure \ 
  && apt-get clean \ 
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* 

# Create a virtual environment to install all Python packages to -- note, Conda can bee used as well 
RUN virtualenv -p python3.7 --system-site-packages /databricks/python3 

# Install libraries
RUN /databricks/python3/bin/pip install \
  pip==20.2.4 \ 
  absl-py==0.10.0 \
  aiobotocore==1.1.2 \
  aiohttp==3.6.3 \
  aioitertools==0.7.0 \
  alembic==1.4.3 \
  anyconfig==0.9.11 \
  argon2-cffi==20.1.0 \
  arrow==0.17.0 \
  asn1crypto==0.24.0 \
  astunparse==1.6.3 \
  async-generator==1.10 \
  async-timeout==3.0.1 \
  atomicwrites==1.4.0 \
  attrs==20.2.0 \
  ax-platform==0.1.14 \
  backcall==0.1.0 \
  binaryornot==0.4.4 \
  bleach==3.2.1 \
  boto==2.49.0 \
  boto3==1.14.32 

RUN /databricks/python3/bin/pip install \
  botocore==1.17.32 \
  botorch==0.3.1 \
  cachetools==4.1.1 \
  certifi==2020.6.20 \
  cffi==1.12.2 \
  cfgv==3.2.0 \
  chardet==3.0.4 \
  click==7.1.2 \
  cloudpickle==1.6.0 \
  confuse==1.3.0 \
  cookiecutter==1.7.2 \
  coverage==4.5.4 \
  cryptography==2.6.1 \
  cycler==0.10.0 \
  Cython==0.29.6 \
  databricks-cli==0.12.1 \
  decorator==4.4.0 \
  defusedxml==0.6.0 \
  descartes==1.1.0 \
  docker==4.3.1 \
  docopt==0.6.2 \
  docutils==0.14 \
  entrypoints==0.3 \
  environs==6.1.0 \
  flake8==3.7.9 \
  Flask==1.1.2 \
  flask-oidc==1.4.0 \
  fsspec==0.8.3 \
  future==0.18.2 \
  fuzzywuzzy==0.18.0 \
  gast==0.3.3 \
  gitdb==4.0.5 \
  GitPython==3.1.9 \
  google-auth==1.22.1 \
  google-auth-oauthlib==0.4.1 \
  google-pasta==0.2.0 \
  gorilla==0.3.0 \
  gpytorch==1.2.0 \
  grpcio==1.32.0 \
  gunicorn==20.0.4 \
  h5py==2.10.0 \
  hdfs==2.5.8 \
  htmlmin==0.1.12 \
  httplib2==0.18.1 \
  hyperopt==0.2.4 \
  identify==1.5.6 \
  idna==2.8 \
  ImageHash==4.1.0 \
  importlib-metadata==2.0.0 \
  iniconfig==1.0.1 \
  ipykernel==5.1.0 \
  ipython==7.4.0 \
  ipython-genutils==0.2.0 \
  ipywidgets==7.5.1 \
  itsdangerous==1.1.0 \
  jedi==0.13.3 \
  Jinja2==2.11.2 \
  jinja2-time==0.2.0 \
  jmespath==0.9.4 \
  joblib==0.17.0 \
  jsonschema==3.2.0 \
  jupyter==1.0.0 \
  jupyter-client==6.1.7 \
  jupyter-console==6.2.0 \
  jupyter-core==4.6.3 \
  jupyterlab==0.31.1 \
  jupyterlab-launcher==0.10.5 \
  jupyterlab-pygments==0.1.2 \
  kedro[spark,pandas,pickle,pyspark]==0.16.5 \
  Keras-Preprocessing==1.1.2 \
  kiwisolver==1.2.0 \
  llvmlite==0.34.0

RUN /databricks/python3/bin/pip install \
  Mako==1.1.3 \
  Markdown==3.3.1 \
  MarkupSafe==1.1.1 \
  marshmallow==3.8.0 \
  matplotlib==3.2.0 \
  mccabe==0.6.1 \
  missingno==0.4.2 \
  mistune==0.8.4 \
  mizani==0.7.1 \
  mlflow==1.3.0 \
  mock==4.0.2 \
  more-itertools==8.5.0 \
  multidict==4.7.6 \
  nbclient==0.5.0 \
  nbconvert==6.0.7 \
  nbformat==5.0.7 \
  nbstripout==0.3.3 \
  nest-asyncio==1.4.1 \
  networkx==2.4 \
  nodeenv==1.5.0 \
  notebook==6.1.4 \
  numba==0.51.2 \
  numexpr==2.7.1 \
  numpy==1.19.0 \
  oauth2client==4.1.3 \
  oauthlib==3.1.0 \
  okta==0.0.4 \
  opt-einsum==3.3.0 \
  packaging==20.4 \
  palettable==3.3.0 \
  pandas==1.1.3 \
  pandas-profiling==2.9.0 \
  pandocfilters==1.4.2 \
  parso==0.3.4 \
  patsy==0.5.1 \
  pexpect==4.6.0 \
  phik==0.10.0 \
  pickleshare==0.7.5 \
  Pillow==7.2.0 \
  pip-tools==4.5.1 \
  plotly==4.9.0 \
  plotnine==0.7.1 \
  pluggy==0.13.1 \
  poyo==0.5.0 \
  pre-commit==2.1.1 \
  prometheus-client==0.8.0 \
  prompt-toolkit==2.0.9 \
  protobuf==3.13.0 \
  psutil==5.6.7 \
  psycopg2==2.7.6 \
  ptyprocess==0.6.0 \
  py==1.9.0 \
  py4j==0.10.7 \
  pyarrow==0.13.0 \
  pyasn1==0.4.8 \
  pyasn1-modules==0.2.8 \
  pycodestyle==2.5.0 \
  pycparser==2.19 \
  pycurl==7.43.0 \
  pyflakes==2.1.1 \
  Pygments==2.7.1 \
  pygobject \
  pyOpenSSL==19.0.0 \
  pyparsing==2.4.7 \
  pyrsistent==0.17.3 \
  PySocks==1.6.8 \
  pyspark==2.4.4 \
  pytest==3.10.1 

RUN /databricks/python3/bin/pip install \
  pytest-cov==2.10.1 \
  pytest-mock==1.13.0 \
  python-apt \
  python-dateutil==2.8.0 \
  python-dotenv==0.14.0 \
  python-editor==1.0.4 \
  python-json-logger==0.1.11 \
  python-slugify==4.0.1 \
  pytz==2020.1 \
  PyWavelets==1.1.1 \
  PyYAML==5.3.1 \
  pyzmq==18.0.0 \
  qtconsole==4.7.7 \
  QtPy==1.9.0 \
  querystring-parser==1.2.4 \
  requests==2.23.0 \
  requests-oauthlib==1.3.0 \
  retrying==1.3.3 \
  rsa==4.6 \
  s3fs==0.4.2 \
  s3transfer==0.3.3 \
  scikit-learn==0.23.0 \
  scipy==1.4.1 \
  seaborn==0.9.0 \
  semver==2.10.2 \
  Send2Trash==1.5.0 \
  shap==0.35.0 \
  simplejson==3.17.2 \
  six==1.12.0 \
  smmap==3.0.4 \
  SQLAlchemy==1.3.19 \
  sqlparse==0.4.1 \
  ssh-import-id==5.8 \
  statsmodels==0.12.0 \
  tables==3.5.2 \
  tabulate==0.8.7 \
  tangled-up-in-unicode==0.0.6 \
  tenacity==6.2.0

RUN /databricks/python3/bin/pip install \
  tensorboard==2.2.2 \
  tensorboard-plugin-wit==1.7.0 \
  tensorflow==2.2.0 \
  tensorflow-estimator==2.2.0 \
  termcolor==1.1.0 \
  terminado==0.9.1 \
  testpath==0.4.4 \
  text-unidecode==1.3 \
  threadpoolctl==2.1.0 \
  toml==0.10.1 \
  toposort==1.5 \
  torch==1.5.1 \
  torchvision==0.6.1 \
  tornado==6.0.2 \
  tqdm==4.43.0 \
  traitlets==4.3.2 \
  typing-extensions==3.7.4.3 \
  unattended-upgrades==0.1 \
  urllib3==1.21.1 \
  virtualenv==16.4.1 \
  visions==0.5.0 \
  wcwidth==0.1.7 \
  webencodings==0.5.1 \
  websocket-client==0.57.0 \
  Werkzeug==1.0.1 \
  widgetsnbextension==3.5.1 \
  wrapt==1.12.1 \
  xgboost==0.90 \
  xlrd==1.2.0 \
  XlsxWriter==1.3.6 \
  yarl==1.5.1 \
  zipp==3.3.0 

# Copy over custom wheel files
COPY pai-0.43.0-py3-none-any.whl /databricks/wheels/pai-0.43.0-py3-none-any.whl
COPY kedro_great_expectations-0.3.0-py3-none-any.whl /databricks/wheels/kedro_great_expectations-0.3.0-py3-none-any.whl

# Install custom wheel files
RUN /databricks/python3/bin/pip install \
  /databricks/wheels/pai-0.43.0-py3-none-any.whl --no-use-pep517 \
  /databricks/wheels/kedro_great_expectations-0.3.0-py3-none-any.whl --no-use-pep517 
