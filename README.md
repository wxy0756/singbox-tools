# 常见组合调用方式

## 1️⃣ 仅 4 直连协议（不走 Argo）

```bash
hypt=2082 \
vlrt=2083 \
vmpt=2080 \
trpt=2081 \
bash <(curl -Ls https://raw.githubusercontent.com/jyucoeng/singbox-tools/refs/heads/main/sb.sh)
```

## 2️⃣ VMess + Trojan + Argo（最常用）

```bash
vmpt=2080 \
trpt=2081 \
argo=vmpt \
bash <(curl -Ls https://raw.githubusercontent.com/jyucoeng/singbox-tools/refs/heads/main/sb.sh)
```

> **说明**：
> - `argo=vmpt` → Argo 转发 VMess
> - 若改为 `argo=trpt` → Argo 转发 Trojan

## 3️⃣ VMess + Hysteria2

```bash
vmpt=2080 \
hypt=2082 \
bash <(curl -Ls https://raw.githubusercontent.com/jyucoeng/singbox-tools/refs/heads/main/sb.sh)
```

## 4️⃣ 仅 VLESS Reality（纯直连）

```bash
vlrt=2083 \
bash <(curl -Ls https://raw.githubusercontent.com/jyucoeng/singbox-tools/refs/heads/main/sb.sh)
```

## 5️⃣ 仅 Hysteria2

```bash
hypt=2082 \
bash <(curl -Ls https://raw.githubusercontent.com/jyucoeng/singbox-tools/refs/heads/main/sb.sh)
```

# 重要细节

> ⚠️ **1. 变量名是“是否存在”，不是值判断**
> 
> 只要变量 存在 就启用协议：
> 
> - `vmpt=2080`   # 启用
> - `vmpt=`       # 仍然启用

> ⚠️ **2. Argo 只对 VMess / Trojan 生效**
> 
> ```bash
> [ -n "$argo" ] && [ -n "$vmag" ]
> ```
> 
> 所以：
> 
> - ❌ Argo + Hysteria2（无效）
> - ❌ Argo + VLESS Reality（无效）
> - ✅ Argo + VMess / Trojan
