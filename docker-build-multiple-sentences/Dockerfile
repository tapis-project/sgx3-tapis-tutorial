#image tapis/sentiment-analysis:1.0.1

FROM huggingface/transformers-pytorch-cpu:4.18.0

# Add user tapis
RUN useradd -m tapis
USER tapis

WORKDIR /home/tapis
RUN mkdir .cache
RUN chmod 777 .cache


COPY --chown=tapis:tapis analyze_sentiment.py .
RUN chmod -R 777 /home/tapis
ENV TRANSFORMERS_CACHE=/home/tapis/.cache
ENTRYPOINT ["python3","/home/tapis/analyze_sentiment.py"]
