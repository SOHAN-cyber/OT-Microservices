FROM python:latest
MAINTAINER OpsTree Solutions
LABEL application="attendance" \
      stack="OT-Microservices"

WORKDIR /attendance/
COPY attendance/requirements.txt /attendance/
RUN pip3 install -r requirements.txt

COPY attendance/attendance_api.py /attendance/
COPY attendance/config.yaml /app/config/config.yaml
EXPOSE 8081
ENTRYPOINT ["gunicorn"]
CMD ["--bind", "0.0.0.0:8081", "attendance_api:app"]
