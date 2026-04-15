Pergunta 1: Por que a Secret aparece no log como *** e a variável aparece normalmente?

R: O GitHub Actions possui um mecanismo de proteção que identifica e mascara automaticamente qualquer valor vindo de secrets. Isso evita a exposição acidental de senhas e tokens nos logs. Já as variables (vars) são para dados não sensíveis, por isso ficam visíveis.

Pergunta 2: O Job deploy_app consegue ler a variável BUILD_VERSION criada no Job build_app? Por quê?

R: Não diretamente. Cada Job roda em uma máquina virtual (runner) isolada. Quando o Job de build termina, seu ambiente é destruído. Para passar dados entre Jobs, seria necessário usar outputs ou artifacts.
