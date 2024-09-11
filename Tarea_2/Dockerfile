FROM pypy:bookworm

RUN useradd -ms /bin/bash pypyer

EXPOSE 8888

USER pypyer

WORKDIR /home/pypyer

COPY requirements.txt .

RUN pypy3 -m pip install --no-cache-dir -r requirements.txt

RUN pypy3 -m pip install jupyter notebook ipykernel

RUN pypy3 -m IPython kernel install --user --name=PyPy3

CMD ["/home/pypyer/.local/bin/jupyter-notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser"]