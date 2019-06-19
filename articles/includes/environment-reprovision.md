Ao copiar um banco de dados entre ambientes, você precisará executar a ferramenta de reprovisionamento de ambiente para que o banco de dados copiado fique totalmente funcional, para garantir que todos os componentes do Retail estejam atualizados.

> [!IMPORTANT]
> Recomendamos que você execute esse procedimento mesmo que não esteja usando vários componentes do Retail, porque a funcionalidade do Retail é incluída em todos os ambientes. 

Antes de prosseguir, você deve verificar se os seguintes pré-requisitos são atendidos:
1. Se você estiver fazendo upgrade para a versão de julho de 2017 (também conhecida como 7.2) 7.2.11792.56024, aplique os hotfixes X++ de aplicativo a seguir no ambiente de destino antes de executar o upgrade de dados no ambiente. Isso evitará que vários erros ocorram durante o upgrade de dados:

    - KB 4036156 - upgrade secundário de versão do Retail - "A sequência de números da grade não está definida". Este pacote de correção também inclui o KB 4035399 e KB 4035751. Você deve possuir, pelo menos, o Platform Update 9 para usar este pacote. Se você não tem certeza, instale os binários mais recentes.
    
2. Se você estiver atualizando do Microsoft Dynamics AX 2012, instale estas correções X++ de aplicativo no ambiente de destino antes de executar o upgrade de dados:
    - KB 4033183 - O upgrade não varejo do Dynamics AX 2012 R2 ou Dynamics AX 2012 R3 Pre-CU8 falha e exibe a mensagem "Objeto não encontrado para dbo.RETAILTILLLAYOUTZONE.
    - KB 4040692 - O upgrade do Dynamics AX 2012 R3 para o Microsoft Dynamics 365 for Operations 7.2 falha no índice duplicado RetailSalesLine no SalesLineIdx.
    - KB 4035490 - Problema de desempenho com o script de upgrade do campo GeneralJournalAccountEntry MainAccount.


Siga estas etapas para executar a ferramenta de reprovisionamento de ambiente.

1. Na biblioteca de ativos compartilhados, selecione **Pacote de software implantável**.
2. Baixe a ferramenta de reprovisionamento de ambiente.
3. Na biblioteca de ativos do seu projeto, selecione **Pacote de software implantável**.
4. Selecione **Novo** para criar um novo pacote.
5. Digite um nome e uma descrição para o pacote. Você pode usar **Ferramenta de reprovisionamento de ambiente** como o nome do pacote.
6. Carregue o pacote baixado anteriormente.
7. Na página **Detalhes de ambiente** do ambiente de destino, selecione **Manter** > **Aplicar atualizações**.
8. Selecione a ferramenta de reprovisionamento de ambiente carregada anteriormente e selecione **Aplicar** para aplicar o pacote.
9. Monitore o progresso da implantação do pacote. 

Para obter mais informações sobre como aplicar um pacote implantável, consulte [Aplicar um pacote implantável](../deployment/create-apply-deployable-package.md). Para obter mais informações sobre como aplicar um pacote implantável manualmente, consulte [Instalar um pacote implantável](../deployment/install-deployable-package.md).
