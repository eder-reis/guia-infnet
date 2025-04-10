**Curso:** Pós em Arquitetura de Software.<br>
**Aula:** Integração Contínua, DevOps e Computação em Nuvem<br>
**Ano Semestre:** 25E1_3<br>

# Integração Contínua, DevOps e Computação em Nuvem [25E1_3]

Entrega de trabalho.

### Desafio:

1. Utilize o Docker para criar uma imagem personalizada de alguma aplicação previamente feita por você.

    - Publique a sua imagem no Docker Hub.

2. Suba sua imagem em algum cluster kubernetes, seguindo as seguintes especificações:

    - Utilize Deployment para subir sua aplicação com 4 réplicas.
    - Exponha sua aplicação de modo que ela fique acessível fora do Cluster (NODEPORT).
    - Se sua aplicação fizer uso de banco de dados, crie um POD com o mesmo e deixe-o acessível através do ClusterIP. Se sua aplicação não fizer uso de um BD suba uma imagem do Redis e crie um ClusterIP para o mesmo.
    - Crie algum probe para sua aplicação (Readness ou Liveness.)

3. Crie a estrutura para monitorar sua aplicação com o Prometheus e o Grafana (ou qualquer ferramenta a sua escolha: você deve ter um servidor de métricas e alguma ferramenta para dashboards).
    - Apenas o Grafana deverá ficar acessível para fora do Cluster.
    - Utilize um PVC para escrever os dados do Prometheus de maneira persistente.
    - Crie dashboards do Grafana que exponha dados sensíveis da sua aplicação (memória, cpu, etc.)

4. Utilize o Jenkins (ou qualquer ferramenta) para criar um pipeline de entrega do seu projeto.

5. Execute um stress test do seu projeto e tire print do Dashboard sofrendo alterações.

# Imagens do Docker Desktop
* Container:
![Screenshot](EntregaTrabalho/Imagens/Containers.jpg)
* Imagens 
    * Locais:
    ![Screenshot](EntregaTrabalho/Imagens/Docker-Imagens-Locais.jpg)
    * Hub
    ![Screenshot](EntregaTrabalho/Imagens/Docker-Imagens-no-Repositorio.jpg)

# Usando kubernetes

* Deployment com 4 réplicas:
![Screenshot](EntregaTrabalho/Imagens/k8s-replicas.jpg)
* Deployment da aplicação:
![Screenshot](EntregaTrabalho/Imagens/k8s-pods.jpg)
* Probe para a aplicação: (vide conforme arquivo Guia-deployment.yaml)
![Screenshot](EntregaTrabalho/Imagens/yaml-Probe.jpg)

# Estrutura para Monitorar a aplicação
* Informações do Kubernetes sobre os Pods, Deployments e Servicos.
![Screenshot](EntregaTrabalho/Imagens/k8s-monitoramento-pods.jpg)
![Screenshot](EntregaTrabalho/Imagens/k8s-monitoramento-deployments.jpg)
![Screenshot](EntregaTrabalho/Imagens/k8s-monitoramento-servicos.jpg)

* Sistemas de Monitoramento deverá ficar acessível fora do cluster.
![Screenshot](EntregaTrabalho/Imagens/Grafana.jpg)

> Atenção devido a aula do dia 8 de abril não ter sido gravada, não pude verificar como é feito a comunicação entre o Grafana e a Aplicação. Lembro ao examinador que as terças-feiras eu participo do Culto da minha igreja.

* Utilizar o Jenkins para subir a aplicação.
![Screenshot](EntregaTrabalho/Imagens/github-actions-resultado-Geral.jpg)
* Arquivo Yaml do git action:
![Screenshot](EntregaTrabalho/Imagens/Git-Action-Arquivo.jpg)
> Aqui o conforme acordado poderia fazer o Git Actions, se o examinador achar importante, pode verificar o arquivo da solução 

# Arquivo do Deployment do Kubernetes:
![Screenshot](EntregaTrabalho/Imagens/guia-deployment-yaml.jpg)
