FROM python:3.9

WORKDIR /app

EXPOSE 5050
COPY Pipfile Pipfile.lock ./

RUN pip install pipenv
RUN pipenv --version
#RUN  cat Pipfile.lock |
#    | grep -B1 '"hashes"|"version"|"extras": '
#    | grep -v '"markers": |"hashes": '
#    | grep ": {|version"
#    | sed -e 's/: {$//g'
#    | tr '\n' ',' | tr -s ' ' ' '
#    | sed -e 's/, "version": "//g;s/", "/ /g;s/"//g;s/,//g'
#    | tr ' ' '\n'
#    | grep -v "^$" > requirements.txt
RUN pipenv requirements > requirements.txt
#RUN print(requirements.txt)
RUN pip install -r requirements.txt


COPY . ./ 

CMD ["python","main.py"]