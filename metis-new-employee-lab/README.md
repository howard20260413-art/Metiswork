# Metis 測試用關卡：新進員工日常作業與異常排查考核

## 專案簡介
本專案為 **Metis 資安實作練習平台** 的測試用輕量網頁關卡 Image，結合 2D 辦公室探索與模擬 Linux 終端機互動，引導使用者完成 10 項日常基礎維運任務與最終定期員工考核（異常排查與機密檔案 Flag 取得）。

## 建置與推送至 ghcr.io

```bash
# 1. 登入 GitHub Container Registry
echo "<YOUR_GITHUB_PAT>" | docker login ghcr.io -u howard20260413-art --password-stdin

# 2. 建置輕量網頁關卡 Image
docker build -t ghcr.io/howard20260413-art/metis-new-employee-lab:v1.0.0 .

# 3. 推送至 ghcr.io
docker push ghcr.io/howard20260413-art/metis-new-employee-lab:v1.0.0
```

## 本機快速測試

```bash
docker run --rm -p 8080:80 ghcr.io/howard20260413-art/metis-new-employee-lab:v1.0.0
```
啟動後開啟瀏覽器前往 `http://localhost:8080` 即可進行完整關卡測試。

## Metis 管理後台設定對照

* **目標類型**：網站
* **映像**：`ghcr.io/howard20260413-art/metis-new-employee-lab:v1.0.0`
* **網站 port**：`80`
* **題目設定（依序作答）**：
  1. **階段一驗證碼**：`METIS-STAGE1-ONBOARD-OK`
  2. **階段二驗證碼**：`METIS-STAGE2-OPS-SECURE`
  3. **階段三驗證碼**：`METIS-STAGE3-INCIDENT-FIXED`
  4. **最終考核 Flag**：`METIS{new_emp_audit_passed_2026}`
