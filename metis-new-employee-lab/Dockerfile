# 使用輕量級 Python Alpine 基底映像檔
FROM python:3.11-alpine

# 建立非特權員工使用者與工作目錄
RUN addgroup -S employee && adduser -S employee -G employee \
    && mkdir -p /opt/metis-lab /home/employee/workspace \
    && chown -R employee:employee /opt/metis-lab /home/employee

WORKDIR /opt/metis-lab

# 複製應用程式與初始模擬工作區
COPY app/ /opt/metis-lab/app/
COPY workspace/ /opt/metis-lab/seed_workspace/

RUN chown -R employee:employee /opt/metis-lab

# 開放 HTTP 80 埠（配合 Metis 網站目標設定）
EXPOSE 80

# 啟動輕量網頁服務
CMD ["python3", "/opt/metis-lab/app/server.py"]
