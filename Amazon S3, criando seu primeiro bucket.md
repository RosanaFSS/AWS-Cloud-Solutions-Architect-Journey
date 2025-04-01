<h1 align="center"> $$\textcolor{#33fffe}{\textnormal{Amazon S3, criando seu primeiro bucket}}$$ </h1>
<p align="center">CloudFaster Academy   -   ADVC Program<br> 
September 18, <bold>2023</bold>  &nbsp;&nbsp;&nbsp;and&nbsp;&nbsp;&nbsp;  January 16, 2024</p>
<br>

<br>
<h2  align="center" class="bold" style="font-weight: bold"> Amazon S3</h2>
<p align="center">
<p>O Amazon S3 (Simple Storage Service) é um serviço de armazenamento de objetos altamente escalável, durável e seguro oferecido pela Amazon Web Services (AWS). Projetado para acomodar desde alguns gigabytes até exabytes de dados, o S3 é uma solução versátil para armazenamento na nuvem, adequada para uma variedade de casos de uso, incluindo backup, arquivamento, distribuição de conteúdo e hospedagem de sites. Além da escalabilidade e durabilidade, o S3 oferece recursos avançados, como controle de acesso granular, versões de objetos, transferência de dados criptografada e integração fácil com outros serviços da AWS, tornando-o uma escolha fundamental para o armazenamento e gerenciamento eficiente de dados na nuvem.
</p>

 
<h2  align="center" class="bold" style="font-weight: bold">Conteúdo</h2>
<p align="center">Neste laboratório você aprenderá a provisionar seu primeiro bucket no Amazon S3.</p>

<h2  align="center" class="bold" style="font-weight: bold">Arquitetura do laboratório</h2>

<p align="center"> <img width="700px" src="https://github.com/user-attachments/assets/4a255335-c830-4a62-9590-594cf24b9368"> </p>

<h2  align="center" class="bold" style="font-weight: bold">Tarefas</h2>
<p align="center">1. Faça login na AWS.<br>
2. Navegue até o Amazon S3.<br>
3. Faça as definições de criação de um bucket S3.<br>
4. Configure o Versionamento.<br>
5. Revise as configurações.<br>
6. Crie o bucket.<br>
7. Verifique a criação do bucket.</p>

<br>
<br>
<p align="center">Vamos iniciar!</p>


<br>
<h1 align="left"> $$\textcolor{#33fffe}{\textnormal{Amazon S3, criando seu primeiro bucket}}$$<br>
$$\textcolor{white}{\textnormal{Prática}}$$ </h1>

<h3 align="left"> $$\textcolor{white}{\textnormal{Passo 1 - aça login na AWS}}$$ </h3>
<p align="left">Acesse o site da AWS e faça login na sua conta, usando as credenciais ao lado.</p>

<p align="left"> <img width="900px" src="https://github.com/user-attachments/assets/853fd015-ef99-4b74-a27e-988073037129"> </p>


<br>

<h3 align="left"> $$\textcolor{white}{\textnormal{Passo 2 - Navegue até o Amazon S3}}$$ </h3>
<p align="left">Clique em "serviços" e acesse o "S3" na seção "armazenamento".</p>

<p align="left"> <img width="900px" src="https://github.com/user-attachments/assets/8a921310-abcb-4f8a-8eb9-eef04eb6ef2c"> </p>



<br>

<h3 align="left"> $$\textcolor{white}{\textnormal{Passo 3 - Crie um novo bucket}}$$ </h3>
<p align="left">Clique em "criar bucket".</p>

<p align="left"> <img width="900px" src="https://github.com/user-attachments/assets/e0b025a8-a872-41e5-a80b-55e635dcf72a"> </p>

<br>

<h3 align="left"> $$\textcolor{white}{\textnormal{Passo 4 - Preencha as Configurações do Bucket}}$$ </h3>
<p align="left">Agora, você definirá algumas configurações necessárias para a criação de um bucket S3. Em "nome do bucket" atribua um nome (ex: primeiro-bucket-16-04).
Dica: o nome do bucket deve ser globalmente exclusivo, pois todos os buckets no Amazon S3 compartilham o mesmo espaço de nomes global. Opte por especificar que é o seu primeiro bucket e acrescente sua data de nascimento ou o dia/mês em que esteja realizando esse laboratório).</p>
<p align="left">Em "propriedade de objeto" selecione "ACLs desabilitadas (recomendado)".</p>

<br>

<p align="left">Em "configurações de bloqueio de acesso público deste bucket" marque "bloquear todo o acesso público".
Dica: o Amazon S3 oferece a opção de bloquear todas as solicitações de acesso público ao bucket e ao conteúdo dentro dele. Por recomendação de segurança, deixe todo o acesso público bloqueado.</p>


<p align="left"> <img width="900px" src="https://github.com/user-attachments/assets/639c9f81-8bdd-43e9-85a5-1d2063d26609"> </p>

<br>

<p align="left"> <img width="900px" src="https://github.com/user-attachments/assets/3065b18a-9f1a-4233-b2d4-6a87ffd3941e"> </p>

<br>

<h3 align="left"> $$\textcolor{white}{\textnormal{Passo 5 - Configure o Versionamento}}$$ </h3>
<p align="left">Em "versionamento de bucket" selecione "desativar".
Dica: o Amazon S3 permite manter versões antigas de objetos armazenados no bucket. Se algum objeto for substituído ou excluído, o S3 manterá as versões anteriores, o que é útil para recuperação de dados e conformidade. Para este laboratório, podemos deixar essa opção desabilitada. </p>
<p align="left">Em "propriedade de objeto" selecione "ACLs desabilitadas (recomendado)".</p>

<p align="left"> <img width="900px" src="https://github.com/user-attachments/assets/505a5d3a-3b3e-4ef2-86cc-244e19ed6b36"> </p>

<br>

<h3 align="left"> $$\textcolor{white}{\textnormal{Passo 6 - Revise as Configurações}}$$ </h3>
<p align="left">As demais configurações que não foram citadas, deverão permanecer como padrão. Volte ao início da página e revise se todas as definições estão de acordo com o conteúdo passado nesse laboratório. Assim que a revisão for concluída, role para o final da tela.</p>

<p align="left"> <img width="900px" src="https://github.com/user-attachments/assets/e520c784-90c2-4702-a0a2-3118a5de58a2"> </p>

<br>

<h3 align="left"> $$\textcolor{white}{\textnormal{Passo 7 - Finalize a Criação do Bucket}}$$ </h3>
<p align="left">Clique em "criar bucket" para que o mesmo seja criado. </p>

<p align="left"> <img width="900px" src="https://github.com/user-attachments/assets/42a580de-6755-4daf-9d8d-42007799396f"> </p>


<br>

<h3 align="left"> $$\textcolor{white}{\textnormal{Passo 8 - Verifique a Criação do Bucket}}$$ </h3>
<p align="left">Nessa tela, podemos ver a mensagem de êxito da criação do bucket. Também é possível visualizar o bucket criado na lista em "buckets de uso geral".
</p>

<p align="left"> <img width="900px" src="https://github.com/user-attachments/assets/c2ad6b1d-fedc-478a-8ea9-911364a58c0c"> </p>

<br>


<p align="left"> <img width="900px" src="https://github.com/user-attachments/assets/eee21fdd-2cf9-4734-9a05-f01f23937e89"> </p>


<br>
<br>

<p align="left"> <img width="900px" src="https://github.com/user-attachments/assets/eee21fdd-2cf9-4734-9a05-f01f23937e89"> </p>

![image](https://github.com/user-attachments/assets/50a64989-fc2e-432a-85e0-2c1cd17bd1e8)




