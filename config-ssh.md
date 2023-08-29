要配置公钥，你需要遵循以下步骤：

1. 生成 SSH 密钥对：打开终端，并运行以下命令来生成 SSH 密钥对：

   ```bash
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```

   在命令中将 `"your_email@example.com"` 替换为你的邮箱地址。你可以选择使用不同的算法和密钥长度，但上述命令将生成一个 RSA 类型的密钥对。

2. 设置密钥存储位置和密码（可选）：系统会提示你选择密钥的存储位置，默认为 `~/.ssh/id_rsa`。如果你希望更改存储位置或为密钥添加额外的安全性，可以按照提示进行操作。

3. 添加公钥到 GitHub：使用以下命令显示公钥内容：

   ```bash
   cat ~/.ssh/id_rsa.pub
   ```

   将公钥内容复制到剪贴板。

4. 登录到 GitHub 帐户：前往 GitHub 的网站（https://github.com/），登录到你的帐户。

5. 添加公钥：点击右上角的头像图标，选择 Settings（设置）。在左侧导航栏中选择 SSH and GPG keys（SSH 和 GPG 密钥）。点击 New SSH key（新建 SSH 密钥）按钮。在 Title（标题）字段中，可以为公钥添加一个描述性的名称。然后，在 Key（密钥）字段中粘贴之前复制的公钥内容。最后，点击 Add SSH key（添加 SSH 密钥）按钮完成添加。

6. 验证配置：在终端中运行以下命令来测试是否配置成功：

   ```bash
   ssh -T git@github.com
   ```

   你将收到一条欢迎消息，表明配置成功。

现在你已经成功配置了公钥，并可以使用 SSH 协议与 GitHub 进行交互，例如使用 Git 命令进行代码推送和拉取操作。