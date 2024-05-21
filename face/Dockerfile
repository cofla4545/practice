# 베이스 이미지 설정
FROM python:3.9-slim-buster

# 환경 변수 설정
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# 필요한 시스템 패키지 설치
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    ffmpeg \
    libsm6 \
    libxext6 \
    libgl1-mesa-glx \
    && rm -rf /var/lib/apt/lists/*

# 작업 디렉토리 설정
WORKDIR /app

# requirements.txt 복사 및 패키지 설치
COPY requirements.txt /app/
RUN pip install --upgrade pip && pip install -r requirements.txt

# 소스 코드 복사
COPY . /app/

# 포트 설정
EXPOSE 5003

# 컨테이너 시작 명령어 설정
CMD ["python", "app.py"]
