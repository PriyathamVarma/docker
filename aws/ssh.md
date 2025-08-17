# 🔐 How to SSH into Your EC2 Instance (Step-by-Step Guide)

---

## 1. Download the `.pem` Key

- When you launch an EC2 instance, AWS provides a **private key file** (`.pem`).
- This file proves your identity and lets you log into the server without a password.

Example:

```

test-ec2.pem

```

---

## 2. Set Correct Permissions for the Key

SSH requires that your private key is **not publicly accessible**.

Run:

```bash
chmod 400 test-ec2.pem
```

Why?

- `chmod 400` = only **you (the owner)** can read the file.
- If permissions are too open, SSH will **refuse to use the key** for security.

---

## 3. SSH Command to Connect

The general format is:

```bash
ssh -i <path-to-key.pem> ec2-user@<EC2_PUBLIC_IP>
```

For your case:

```bash
ssh -i test-ec2.pem ec2-user@34.207.202.63
```

Explanation:

- `ssh` → Secure Shell client.
- `-i test-ec2.pem` → Use your private key for authentication.
- `ec2-user` → Default username for **Amazon Linux**.
- `34.207.202.63` → Public IP of your EC2 instance.

---

## 4. First Connection Warning

When you connect for the **first time**, SSH shows:

```
The authenticity of host '34.207.202.63' can't be established.
ED25519 key fingerprint is SHA256:gmXOiMebLieqjoGJtlgnLzcErEBSD7vxRsAhTE5KVsE.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

This means:

- SSH has never seen this server before.
- Type `yes` to trust and continue.
- After that, the fingerprint will be saved in `~/.ssh/known_hosts`.

---

## 5. Successful Login

If everything is correct, you’ll see something like:

```
       __|  __|_  )
       _|  (     /   Amazon Linux 2023
     ___|\___|___|
```

✅ This means you are **inside your EC2 server**.
You can now run Linux commands directly on the remote machine.

---

## 6. (Optional) Make SSH Easier with Config

Typing the full command every time can be annoying.
You can set up an **SSH config**.

1. Open SSH config file:

   ```bash
   nano ~/.ssh/config
   ```

2. Add this block:

   ```
   Host my-ec2
       HostName 34.207.202.63
       User ec2-user
       IdentityFile ~/test-ec2.pem
   ```

3. Save and exit (`CTRL+O`, `ENTER`, `CTRL+X`).

Now you can log in with:

```bash
ssh my-ec2
```

---

## ✅ Summary

1. Download `.pem` file.
2. Restrict permissions → `chmod 400 my-key.pem`.
3. Connect using SSH → `ssh -i my-key.pem ec2-user@<IP>`.
4. Accept fingerprint on first login.
5. (Optional) Create SSH alias for faster logins.

You are now in full control of your EC2 instance 🚀
