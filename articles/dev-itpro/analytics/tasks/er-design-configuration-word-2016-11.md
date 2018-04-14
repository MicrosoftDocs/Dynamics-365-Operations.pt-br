--- 
title: "Criar uma configuração para gerar relatórios no formato Microsoft Word para relatório eletrônico (ER)"
description: "As seguintes etapas explicam como um usuário na função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para criar relatórios como arquivos do Microsoft Word."
author: NickSelin
manager: AnnBe
ms.date: 12/21/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7f80dc8411d38d051b01d77e35635a920d8803a6
ms.openlocfilehash: 300cf6ed1a5a7098e71b812d682c1b51c2cf786c
ms.contentlocale: pt-br
ms.lasthandoff: 11/06/2017

---
# <a name="design-a-configuration-for-generating-reports-in-microsoft-word-format-for-electronic-reporting-er"></a>Criar uma configuração para gerar relatórios no formato Microsoft Word para relatório eletrônico (ER)

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

As seguintes etapas explicam como um usuário na função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para criar relatórios como arquivos do Microsoft Word. Essas etapas podem ser executadas na empresa GBSI.

Para completar essas etapas, você deve primeiro concluí-las na guia de tarefas "Criar uma configuração ER para gerar relatórios no formato OPENXML". Com antecedência, você também precisa baixar e salvar os seguintes modelos localmente para o modelo de relatório:

[Modelo de relatório de pagamento](https://go.microsoft.com/fwlink/?linkid=862266)

[Modelo limitado de relatório de pagamento](https://go.microsoft.com/fwlink/?linkid=862266)

Este procedimento é para um recurso que foi adicionado à versão 1611 do Microsoft Dynamics 365 for Operations.


## <a name="select-the-existing-er-report-configuration"></a>Selecionar a configuração de relatório de ER existente
1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
    * Verifique se o provedor de configuração "Litware, Inc." está selecionado como ativo.  
2. Clique em Configurações de relatórios.
    * Reutilizaremos a configuração ER existente que foi originalmente criada para gerar a saída de relatório no formato OPENXML.  
3. Na árvore, expanda 'Modelo de pagamento'.
4. Na árvore, selecione "Modelo de pagamento\Relatório de planilha de amostra".
5. Clique em Designer.

## <a name="replace-the-excel-template-with-the-word-template"></a>Substituir o modelo do Excel pelo modelo do Word
    * Atualmente, o documento do Excel é usado como modelo para gerar a saída no formato OPENXML. Importaremos o modelo do relatório no formato Word.  
1. Clique em Anexos.
    * Substitua o modelo do Excel existente pelo modelo do Word que você baixou antes, o modelo de relatório de pagamento. Observe que esse modelo contém apenas o layout do documento que desejamos gerar como saída de ER.  
2. Clique em Excluir.
3. Clique em Sim.
4. Clique em Novo.
5. Clique em Arquivo.
6. Clique em Procurar. Procure e selecione o arquivo SampleVendPaymDocReport.docx que você baixou anteriormente. Clique em OK.
    * Selecione o modelo que você baixou na etapa anterior.  
7. No campo Modelo, insira ou selecione um valor.

## <a name="extend-the-word-template-by-adding-a-custom-xml-part"></a>Estender o modelo do Word adicionando uma parte XML personalizada
1. Clique em Salvar.
    * Além de armazenar alterações de configuração, a ação Salvar também atualiza o modelo do Word anexo. A estrutura do formato criado é transferida ao documento do Word anexo como nova parte XML personalizada com o nome "Relatório". Observe que o modelo do Word anexo contém não só o layout do documento que desejamos gerar como saída de ER, como também contém a estrutura dos dados que o ER preencherá nesse modelo no momento da execução.  
2. Clique em Anexos.
    * Agora você precisa associar os elementos da parte XML personalizada "Relatório" às partes do documento do Word.  
    * Se estiver familiarizado com documentos do Word que podem ser criados como formulários contendo controles associados a elementos das partes XML personalizadas, siga todas as etapas da próxima subtarefa para criar esse documento. Para obter mais detalhes, consulte este link https://support.office.com/en-us/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b?ui=en-US&rs=en-US&ad=US. Caso contrário, ignore todas as etapas na próxima subtarefa.  

## <a name="get-word-with-custom-xml-part-to-do-data-bindings"></a>Obter o Word com a parte XML personalizada para realizar associações de dados
    * Abra este documento no Word e faça o seguinte: - Abra a guia Desenvolvedor do Word (personalize a faixa de opções se ela ainda não estiver habilitada).  - Selecione o painel de mapeamento do XML.  - Selecione a parte XML personalizada "Relatório" na pesquisa.  - Realize o mapeamento dos elementos da parte personalizada selecionada e os controles de conteúdo do documento do Word.  - Salve o documento do Word atualizado em uma unidade local.  

## <a name="upload-the-word-template-with-custom-xml-part-bounded-to-content-controls"></a>Atualizar o modelo do Word com a parte XML personalizada associada a controles de conteúdo
1. Clique em Excluir.
2. Clique em Sim.
    * Adicione um novo modelo. Se você completou as etapas da subtarefa anterior, selecione o documento do Word que você preparou e salvou localmente. Caso contrário, selecione o modelo do MS Word SampleVendPaymDocReportBounded.docx que você baixou antes.  
3. Clique em Novo.
4. Clique em Arquivo.
5. Clique em Procurar. Procure e selecione o arquivo SampleVendPaymDocReportBounded.docx que você baixou anteriormente. Clique em OK.
6. No campo Modelo, selecione o documento que você baixou na etapa anterior.
7. Clique em Salvar.
8. Feche a página.

## <a name="execute-the-format-to-create-word-output"></a>Executar o formato para criar a saída do Word
1. No Painel de Ação, clique em Configurações.
2. Clique em Parâmetros de usuário.
3. Selecione Sim no campo Executar configurações.
4. Clique em OK.
5. Clique em Editar.
6. Selecione Sim no campo Executar Rascunho.
7. Clique em Salvar.
8. Feche a página.
9. Feche a página.
10. Vá para Contas a pagar > Pagamentos > Diário de pagamentos.
11. Clique em Linhas.
12. Na lista, marque ou desmarque todas as linhas.
13. Clique em Status do pagamento.
14. Clique em Nenhum.
15. Clique em Gerar pagamentos.
16. Clique em OK.
17. Clique em OK.
    * Analise a saída gerada. Observe que a saída criada é apresentada no formato Word e contém os detalhes dos pagamentos processados.  


