---
title: Configurar a integração da folha de pagamento entre o Talent e o Dayforce
description: Este tópico explica como configurar a integração entre o Microsoft Dynamics 365 for Talent e o Ceridian Dayforce para processar um ciclo de pagamento.
author: andreabichsel
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 59234ef44ad22383ae5daf71d4b663c6183e6c05
ms.sourcegitcommit: d599bc1fc60a010c2753ca547219ae21456b1df9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "1702809"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="140fa-103">Configurar a integração da folha de pagamento entre o Talent e o Dayforce</span><span class="sxs-lookup"><span data-stu-id="140fa-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="140fa-104">A integração entre o Microsoft Dynamics 365 for Talent e o Ceridian Dayforce depende de várias etapas de configuração descritas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="140fa-104">The integration between Microsoft Dynamics 365 for Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="140fa-105">Você deve configurar a integração no Talent e no Dayforce antes de poder processar uma execução de pagamento.</span><span class="sxs-lookup"><span data-stu-id="140fa-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="140fa-106">Ao usar um serviço como o Dayforce para concluir execuções de pagamento, é necessário ativar a integração no Talent.</span><span class="sxs-lookup"><span data-stu-id="140fa-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="140fa-107">A integração requer dados específicos do Talent.</span><span class="sxs-lookup"><span data-stu-id="140fa-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="140fa-108">Portanto, você deve verificar se os dados mapeados para o Dayforce estão configurados no Talent de forma compatível com a integração.</span><span class="sxs-lookup"><span data-stu-id="140fa-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="140fa-109">A integração usa as seguintes categorias amplas de dados:</span><span class="sxs-lookup"><span data-stu-id="140fa-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="140fa-110">Dados de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="140fa-110">Human resources data</span></span>
- <span data-ttu-id="140fa-111">Dados de remuneração</span><span class="sxs-lookup"><span data-stu-id="140fa-111">Compensation data</span></span>
- <span data-ttu-id="140fa-112">Dados da folha de pagamento, como ciclos de pagamento, períodos de pagamento e códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="140fa-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="140fa-113">Dados do trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-113">Worker data</span></span>

<span data-ttu-id="140fa-114">Este tópico descreve as etapas que você deve seguir para ativar a integração.</span><span class="sxs-lookup"><span data-stu-id="140fa-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="140fa-115">Também explica os tipos de dados e os detalhes de configuração que a integração requer.</span><span class="sxs-lookup"><span data-stu-id="140fa-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="140fa-116">Habilitar a integração</span><span class="sxs-lookup"><span data-stu-id="140fa-116">Enable the integration</span></span>

<span data-ttu-id="140fa-117">No Talent, você deve ativar a integração e inserir as informações de configuração para se conectar ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="140fa-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="140fa-118">Para que a transação da contabilidade que for produzida seja importada para o Microsoft Dynamics 365 for Finance and Operations, também é preciso configurar uma conta de armazenamento do Microsoft Azure e inserir a cadeia de conexão do Armazenamento do Azure no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="140fa-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 for Finance and Operations, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance and Operations.</span></span>

<span data-ttu-id="140fa-119">Para ativar a integração no Talent, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="140fa-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="140fa-120">Na página **Administração do sistema**, selecione **Configuração de integração**.</span><span class="sxs-lookup"><span data-stu-id="140fa-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="140fa-121">Digite o ponto de extremidade seguro do File Transfer Protocol (FTP) e o caminho seguro da pasta FTP.</span><span class="sxs-lookup"><span data-stu-id="140fa-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="140fa-122">Digite o nome e a senha do usuário que acessará o ponto de extremidade e o caminho da pasta seguros do FTP.</span><span class="sxs-lookup"><span data-stu-id="140fa-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="140fa-123">Teste a conexão, conforme necessário, e defina a opção **Habilitar integração da folha de pagamento** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="140fa-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="140fa-124">Quando a integração é ativada, o pacote e os arquivos de exportação de dados são criados e a frequência é configurada.</span><span class="sxs-lookup"><span data-stu-id="140fa-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="140fa-125">Você pode alterar essa frequência conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="140fa-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="140fa-126">Para obter mais informações sobre as contas de armazenamento do Azure e as cadeias de conexão do Armazenamento do Azure, consulte os seguintes tópicos do Azure:</span><span class="sxs-lookup"><span data-stu-id="140fa-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="140fa-127">Sobre as contas de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="140fa-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="140fa-128">Configurar cadeias de conexão do Armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="140fa-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/en-us/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="140fa-129">Detalhes técnicos quando a integração da folha de pagamento está habilitada</span><span class="sxs-lookup"><span data-stu-id="140fa-129">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="140fa-130">A ativação da integração da folha de pagamento tem dois efeitos principais:</span><span class="sxs-lookup"><span data-stu-id="140fa-130">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="140fa-131">Um projeto de exportação de dados denominado "Exportação de integração da folha de pagamento" é criado.</span><span class="sxs-lookup"><span data-stu-id="140fa-131">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="140fa-132">Este projeto contém as entidades e os campos necessários para a integração da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="140fa-132">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="140fa-133">Para revisar o projeto, vá para **Administração do sistema**, selecione o bloco **Gerenciamento de dados** e abra o projeto de dados da lista de projetos.</span><span class="sxs-lookup"><span data-stu-id="140fa-133">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="140fa-134">Esse trabalho em lotes executa o projeto de exportação de dados, criptografa o pacote de dados resultante e transfere o arquivo do pacote de dados para a empresa de SFTP configurada na tela **Configuração de integração**.</span><span class="sxs-lookup"><span data-stu-id="140fa-134">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="140fa-135">O pacote de dados transferido para a empresa de SFTP é criptografado usando uma chave exclusiva para o pacote.</span><span class="sxs-lookup"><span data-stu-id="140fa-135">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="140fa-136">A chave é um Azure Key Vault acessível somente pelo Ceridian.</span><span class="sxs-lookup"><span data-stu-id="140fa-136">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="140fa-137">Não é possível descriptografar e revisar o conteúdo do pacote de dados.</span><span class="sxs-lookup"><span data-stu-id="140fa-137">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="140fa-138">Se você precisar examinar o conteúdo do pacote de dados, exporte manualmente o projeto de dados "Exportação de integração da folha de pagamento", baixe-o e abra-o</span><span class="sxs-lookup"><span data-stu-id="140fa-138">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="140fa-139">A exportação manual não aplicará a criptografia nem transferirá o pacote.</span><span class="sxs-lookup"><span data-stu-id="140fa-139">Manual export will not apply encryption or transfer the package.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="140fa-140">Configurar seus dados</span><span class="sxs-lookup"><span data-stu-id="140fa-140">Configure your data</span></span> 

<span data-ttu-id="140fa-141">Para processar a folha de pagamento, você deve configurar dados de RH no Talent.</span><span class="sxs-lookup"><span data-stu-id="140fa-141">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="140fa-142">Você deve configurar dados organizacionais, como cargos e posições, juntamente com informações sobre benefícios e remuneração.</span><span class="sxs-lookup"><span data-stu-id="140fa-142">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="140fa-143">Esses dados fornecem as informações de emprego, pagamento e dedução necessárias para gerar o pagamento do empregado.</span><span class="sxs-lookup"><span data-stu-id="140fa-143">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="140fa-144">Dados de RH</span><span class="sxs-lookup"><span data-stu-id="140fa-144">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="140fa-145">Benefícios</span><span class="sxs-lookup"><span data-stu-id="140fa-145">Benefits</span></span> 

<span data-ttu-id="140fa-146">O RH fornece ferramentas para a configuração e manutenção dos benefícios, deduções e planos de remuneração do trabalhador que uma organização oferece ou processa para seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="140fa-146">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="140fa-147">Ao criar benefícios, tenha em mente os dados e configurações a seguir usados no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="140fa-147">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="140fa-148">Planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="140fa-148">Benefit plans</span></span>

- <span data-ttu-id="140fa-149">Plano (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-149">Plan (required)</span></span>
- <span data-ttu-id="140fa-150">Tipo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-150">Type (required)</span></span>
- <span data-ttu-id="140fa-151">Impacto da folha de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-151">Payroll impact (required)</span></span>
- <span data-ttu-id="140fa-152">Recuperar atrasos de pagamento</span><span class="sxs-lookup"><span data-stu-id="140fa-152">Recover arrears</span></span>
- <span data-ttu-id="140fa-153">Método de dedução</span><span class="sxs-lookup"><span data-stu-id="140fa-153">Deduction method</span></span>
- <span data-ttu-id="140fa-154">Prioridade da dedução</span><span class="sxs-lookup"><span data-stu-id="140fa-154">Deduction priority</span></span>
- <span data-ttu-id="140fa-155">Limitar período</span><span class="sxs-lookup"><span data-stu-id="140fa-155">Limit period</span></span>
- <span data-ttu-id="140fa-156">Valor de limite</span><span class="sxs-lookup"><span data-stu-id="140fa-156">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="140fa-157">Benefícios</span><span class="sxs-lookup"><span data-stu-id="140fa-157">Benefits</span></span>

- <span data-ttu-id="140fa-158">Plano (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-158">Plan (required)</span></span>
- <span data-ttu-id="140fa-159">Tipo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-159">Type (required)</span></span>
- <span data-ttu-id="140fa-160">Opção (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-160">Option (required)</span></span>
- <span data-ttu-id="140fa-161">ID do benefício (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-161">Benefit ID (required)</span></span>
- <span data-ttu-id="140fa-162">Frequência</span><span class="sxs-lookup"><span data-stu-id="140fa-162">Frequency</span></span>
- <span data-ttu-id="140fa-163">Base</span><span class="sxs-lookup"><span data-stu-id="140fa-163">Basis</span></span>
- <span data-ttu-id="140fa-164">Valor ou taxa</span><span class="sxs-lookup"><span data-stu-id="140fa-164">Amount or rate</span></span>
- <span data-ttu-id="140fa-165">Código de ganhos</span><span class="sxs-lookup"><span data-stu-id="140fa-165">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="140fa-166">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="140fa-166">Supported frequencies</span></span> 

- <span data-ttu-id="140fa-167">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="140fa-167">Weekly</span></span>
- <span data-ttu-id="140fa-168">Por quinzena</span><span class="sxs-lookup"><span data-stu-id="140fa-168">Bi-weekly</span></span>
- <span data-ttu-id="140fa-169">Quinzenal</span><span class="sxs-lookup"><span data-stu-id="140fa-169">Semi-monthly</span></span>
- <span data-ttu-id="140fa-170">Mensalmente</span><span class="sxs-lookup"><span data-stu-id="140fa-170">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="140fa-171">Bases com suporte</span><span class="sxs-lookup"><span data-stu-id="140fa-171">Supported bases</span></span> 

- <span data-ttu-id="140fa-172">Valor fixo</span><span class="sxs-lookup"><span data-stu-id="140fa-172">Fixed amount</span></span>
- <span data-ttu-id="140fa-173">Percentual de ganhos</span><span class="sxs-lookup"><span data-stu-id="140fa-173">Percent of earnings</span></span>
- <span data-ttu-id="140fa-174">Horas produtivas</span><span class="sxs-lookup"><span data-stu-id="140fa-174">Productive hours</span></span>

<span data-ttu-id="140fa-175">O Dayforce cria as deduções a seguir, com base no impacto da folha de pagamento definido no plano de benefícios.</span><span class="sxs-lookup"><span data-stu-id="140fa-175">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="140fa-176">Seleção no Talent</span><span class="sxs-lookup"><span data-stu-id="140fa-176">Selection in Talent</span></span>        | <span data-ttu-id="140fa-177">Resultado no Dayforce</span><span class="sxs-lookup"><span data-stu-id="140fa-177">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="140fa-178">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="140fa-178">None</span></span>                       | <span data-ttu-id="140fa-179">Nenhuma dedução é criada.</span><span class="sxs-lookup"><span data-stu-id="140fa-179">No deduction is created.</span></span>                      |
| <span data-ttu-id="140fa-180">Somente dedução</span><span class="sxs-lookup"><span data-stu-id="140fa-180">Deduction only</span></span>             | <span data-ttu-id="140fa-181">Uma dedução de funcionário é criada.</span><span class="sxs-lookup"><span data-stu-id="140fa-181">An employee deduction is created.</span></span>             |
| <span data-ttu-id="140fa-182">Somente contribuição</span><span class="sxs-lookup"><span data-stu-id="140fa-182">Contribution only</span></span>          | <span data-ttu-id="140fa-183">Uma dedução de empregador é criada.</span><span class="sxs-lookup"><span data-stu-id="140fa-183">An employer deduction is created.</span></span>             |
| <span data-ttu-id="140fa-184">Dedução e contribuição</span><span class="sxs-lookup"><span data-stu-id="140fa-184">Deduction and contribution</span></span> | <span data-ttu-id="140fa-185">Deduções de funcionário e empregador são criadas.</span><span class="sxs-lookup"><span data-stu-id="140fa-185">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="140fa-186">Para obter mais informações sobre como definir e gerenciar um programa de benefícios, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="140fa-186">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="140fa-187">Entregar um programa de benefícios do funcionário</span><span class="sxs-lookup"><span data-stu-id="140fa-187">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="140fa-188">Criar um novo benefício</span><span class="sxs-lookup"><span data-stu-id="140fa-188">Create a new benefit</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="140fa-189">Definir regras e políticas de qualificação para o benefício</span><span class="sxs-lookup"><span data-stu-id="140fa-189">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="140fa-190">Inscrever e remover benefícios de trabalhadores</span><span class="sxs-lookup"><span data-stu-id="140fa-190">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="140fa-191">Remuneração</span><span class="sxs-lookup"><span data-stu-id="140fa-191">Compensation</span></span> 

<span data-ttu-id="140fa-192">O gerenciamento de remuneração é usado para controlar o pagamento do salário base e de prêmios.</span><span class="sxs-lookup"><span data-stu-id="140fa-192">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="140fa-193">Os aumentos no salário base fixo e nos prêmios de um funcionário são controlados por meio de planos de remuneração fixos.</span><span class="sxs-lookup"><span data-stu-id="140fa-193">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="140fa-194">O pagamento de incentivos, como pagamentos de bônus, prêmios por desempenho, opções de ação e concessões, além de prêmios únicos, são controlados por meio de planos de remuneração variável.</span><span class="sxs-lookup"><span data-stu-id="140fa-194">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="140fa-195">O Dayforce usa informações de remuneração para calcular a taxa por hora ou anual de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="140fa-195">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="140fa-196">Planos de remuneração fixa e conversões de taxa de pagamento são necessários.</span><span class="sxs-lookup"><span data-stu-id="140fa-196">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="140fa-197">Os funcionários devem estar associados a um plano de remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="140fa-197">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="140fa-198">Para obter mais informações sobre planos de remuneração, veja os tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="140fa-198">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="140fa-199">Criar planos de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="140fa-199">Create fixed compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="140fa-200">Criar planos de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="140fa-200">Create variable compensation plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="140fa-201">Desenvolver estrutura e planos de remuneração/salário</span><span class="sxs-lookup"><span data-stu-id="140fa-201">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="140fa-202">Processar remuneração</span><span class="sxs-lookup"><span data-stu-id="140fa-202">Process compensation</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="140fa-203">Definir processo de remuneração e calcular resultados</span><span class="sxs-lookup"><span data-stu-id="140fa-203">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="140fa-204">Inscrever um funcionário em um plano de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="140fa-204">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="140fa-205">Inscrever um funcionário em um plano de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="140fa-205">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="140fa-206">Trabalhos</span><span class="sxs-lookup"><span data-stu-id="140fa-206">Jobs</span></span> 

<span data-ttu-id="140fa-207">Um trabalho é um conjunto de tarefas e responsabilidades exigidas de uma pessoa que realiza um trabalho.</span><span class="sxs-lookup"><span data-stu-id="140fa-207">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="140fa-208">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="140fa-208">For more information, see the following topics:</span></span>

- [<span data-ttu-id="140fa-209">Configurando os componentes de um trabalho</span><span class="sxs-lookup"><span data-stu-id="140fa-209">Setting up the components of a job</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="140fa-210">Definir novos trabalhos</span><span class="sxs-lookup"><span data-stu-id="140fa-210">Define new jobs</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="140fa-211">Posições</span><span class="sxs-lookup"><span data-stu-id="140fa-211">Positions</span></span>

<span data-ttu-id="140fa-212">Um cargo é uma instância individual de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="140fa-212">A position is an individual instance of a job.</span></span> <span data-ttu-id="140fa-213">Por exemplo, a posição "Gerente de vendas (Leste)" é uma das posições associadas ao trabalho "Gerente de vendas".</span><span class="sxs-lookup"><span data-stu-id="140fa-213">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="140fa-214">Uma posição existe em um departamento.</span><span class="sxs-lookup"><span data-stu-id="140fa-214">A position exists in a department.</span></span> <span data-ttu-id="140fa-215">Apenas um trabalhador pode ser associado a cada posição.</span><span class="sxs-lookup"><span data-stu-id="140fa-215">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="140fa-216">Considere os seguintes dados e configurações ao configurar as posições:</span><span class="sxs-lookup"><span data-stu-id="140fa-216">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="140fa-217">Posição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-217">Position (required)</span></span>
- <span data-ttu-id="140fa-218">Descrição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-218">Description (required)</span></span>
- <span data-ttu-id="140fa-219">Trabalho (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-219">Job (required)</span></span>
- <span data-ttu-id="140fa-220">Departamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-220">Department (required)</span></span>
- <span data-ttu-id="140fa-221">Tipo de posição (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-221">Position type (required)</span></span>
- <span data-ttu-id="140fa-222">Equivalente ao horário integral</span><span class="sxs-lookup"><span data-stu-id="140fa-222">Full-time equivalent</span></span>
- <span data-ttu-id="140fa-223">Horas normais anuais (obrigatórias)</span><span class="sxs-lookup"><span data-stu-id="140fa-223">Annual regular hours (required)</span></span>
- <span data-ttu-id="140fa-224">Pago por entidade legal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-224">Paid by legal entity (required)</span></span>
- <span data-ttu-id="140fa-225">Ciclo de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-225">Pay cycle (required)</span></span>
- <span data-ttu-id="140fa-226">Dimensão financeira padrão – Centro de custo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-226">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="140fa-227">Atribuição do trabalhador – Trabalhador, início da atribuição, fim da atribuição, código de motivo</span><span class="sxs-lookup"><span data-stu-id="140fa-227">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="140fa-228">Se várias posições no mesmo departamento estiverem associadas ao mesmo trabalho, elas serão consolidadas em uma única posição no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="140fa-228">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="140fa-229">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="140fa-229">For more information, see the following topics:</span></span>

- [<span data-ttu-id="140fa-230">Organizar sua força de trabalho usando departamentos, trabalhos e posições</span><span class="sxs-lookup"><span data-stu-id="140fa-230">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="140fa-231">Configurar posições</span><span class="sxs-lookup"><span data-stu-id="140fa-231">Set up positions</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="140fa-232">Departamentos</span><span class="sxs-lookup"><span data-stu-id="140fa-232">Departments</span></span>

<span data-ttu-id="140fa-233">Um departamento é uma unidade operacional que representa uma categoria ou uma área funcional de uma organização.</span><span class="sxs-lookup"><span data-stu-id="140fa-233">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="140fa-234">Um departamento é responsável por uma área específica da organização, como vendas, contabilidade ou recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="140fa-234">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="140fa-235">Você pode usar departamentos para relatar áreas funcionais.</span><span class="sxs-lookup"><span data-stu-id="140fa-235">You can use departments to report on functional areas.</span></span> <span data-ttu-id="140fa-236">Os departamentos podem ter a responsabilidade de lucros e perdas.</span><span class="sxs-lookup"><span data-stu-id="140fa-236">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="140fa-237">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="140fa-237">For more information, see the following topics:</span></span>

- [<span data-ttu-id="140fa-238">Criar um departamento e associá-lo à hierarquia de departamentos</span><span class="sxs-lookup"><span data-stu-id="140fa-238">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="140fa-239">Definir novos departamentos</span><span class="sxs-lookup"><span data-stu-id="140fa-239">Define new departments</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="140fa-240">Ciclos de pagamento e períodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="140fa-240">Pay cycles and pay periods</span></span>

<span data-ttu-id="140fa-241">Um ciclo de pagamento determina a frequência com que a folha de pagamento é executada e os dias específicos em que os trabalhadores são pagos.</span><span class="sxs-lookup"><span data-stu-id="140fa-241">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="140fa-242">Por exemplo, um ciclo de pagamento pode ser mensal e os funcionários podem ser pagos no último dia do mês.</span><span class="sxs-lookup"><span data-stu-id="140fa-242">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="140fa-243">Como alternativa, um ciclo de pagamento pode ser semanal e os funcionários podem ser pagos na terça-feira após o término do período de pagamento.</span><span class="sxs-lookup"><span data-stu-id="140fa-243">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="140fa-244">Ciclos de pagamento são atribuídos a posições para controlar quando os trabalhadores nessas posições são pagos.</span><span class="sxs-lookup"><span data-stu-id="140fa-244">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="140fa-245">Após a criação dos ciclos de pagamento, você pode gerar períodos de pagamento para cada ciclo.</span><span class="sxs-lookup"><span data-stu-id="140fa-245">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="140fa-246">Cada período de pagamento inclui uma data de pagamento padrão baseada nas informações que você fornece.</span><span class="sxs-lookup"><span data-stu-id="140fa-246">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="140fa-247">No entanto, você pode modificar a data de pagamento padrão em um período de pagamento para permitir exceções (por exemplo, quando a data de pagamento cai em um feriado).</span><span class="sxs-lookup"><span data-stu-id="140fa-247">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="140fa-248">As seguintes informações são usadas no Dayforce:</span><span class="sxs-lookup"><span data-stu-id="140fa-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="140fa-249">Ciclo de pagamento (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-249">Pay cycle (required)</span></span>
- <span data-ttu-id="140fa-250">Frequência do ciclo de pagamento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-250">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="140fa-251">Data de início do período (primeiro período de pagamento obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-251">Period start date (first pay period required)</span></span>
- <span data-ttu-id="140fa-252">Data de pagamento padrão (primeiro período de pagamento obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-252">Default payment date (first pay period required)</span></span>

<span data-ttu-id="140fa-253">Essas informações são integradas ao Dayforce como grupos de pagamento e são separadas por país ou região para cada ciclo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="140fa-253">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="140fa-254">Pelo menos um período de pagamento deve ser gerado antes da integração.</span><span class="sxs-lookup"><span data-stu-id="140fa-254">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="140fa-255">O Dayforce gera datas de pagamento e calendários do grupo de pagamento, com base na data de início do primeiro período de pagamento e na data de pagamento padrão configurada no Talent.</span><span class="sxs-lookup"><span data-stu-id="140fa-255">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="140fa-256">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="140fa-256">Earning codes</span></span>

<span data-ttu-id="140fa-257">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="140fa-257">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="140fa-258">Os códigos têm vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="140fa-258">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="140fa-259">As seguintes informações são usadas no Dayforce:</span><span class="sxs-lookup"><span data-stu-id="140fa-259">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="140fa-260">Código de ganhos (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-260">Earning Code (required)</span></span>
- <span data-ttu-id="140fa-261">descrição</span><span class="sxs-lookup"><span data-stu-id="140fa-261">Description</span></span>
- <span data-ttu-id="140fa-262">Unidade de medida</span><span class="sxs-lookup"><span data-stu-id="140fa-262">Unit of measure</span></span>
- <span data-ttu-id="140fa-263">Produtivo</span><span class="sxs-lookup"><span data-stu-id="140fa-263">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="140fa-264">Dados do trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-264">Worker data</span></span>

<span data-ttu-id="140fa-265">Os registros dos vários tipos de trabalhadores que você tem são importantes para o RH e sistemas de folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="140fa-265">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="140fa-266">As informações inseridas podem ser usadas para rastrear trabalhadores e informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="140fa-266">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="140fa-267">Você pode manter estas informações para trabalhadores:</span><span class="sxs-lookup"><span data-stu-id="140fa-267">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="140fa-268">**Básicas** – mantenha informações básicas do trabalhador, como informações de contato, demográficas, de identificação, sobre a família, o status de serviço militar, informações de exilado, contatos pessoais e de emergência.</span><span class="sxs-lookup"><span data-stu-id="140fa-268">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="140fa-269">**Emprego** – mantenha informações sobre o emprego dos trabalhadores, como a afiliação da empresa ou organização, a atribuição de posição, as datas inicial e final, a qualificação para trabalho, o contrato de trabalho, a pensão, férias e as informações de mudança.</span><span class="sxs-lookup"><span data-stu-id="140fa-269">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="140fa-270">**Licença e ausência** – mantenha informações sobre as ausências dos trabalhadores, como o calendário de trabalho, as transações de ausência e a configuração de ausência.</span><span class="sxs-lookup"><span data-stu-id="140fa-270">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="140fa-271">**Remuneração e folha de pagamento** – mantenha informações sobre os planos de remuneração e as informações de folha de pagamento de trabalhadores, como o registro do plano, prêmios, o desempenho, a comissão, informações sobre impostos, aposentadoria e deduções do salário.</span><span class="sxs-lookup"><span data-stu-id="140fa-271">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="140fa-272">Ao inserir informações do trabalhador, tenha em mente os dados e configurações a seguir usados no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="140fa-272">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="140fa-273">Informações gerais</span><span class="sxs-lookup"><span data-stu-id="140fa-273">General information</span></span>

- <span data-ttu-id="140fa-274">Número de equipe (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-274">Personnel number (required)</span></span>
- <span data-ttu-id="140fa-275">Nome (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-275">First name (required)</span></span>
- <span data-ttu-id="140fa-276">Sobrenome (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-276">Last name (required)</span></span>
- <span data-ttu-id="140fa-277">Nome do meio</span><span class="sxs-lookup"><span data-stu-id="140fa-277">Middle name</span></span>
- <span data-ttu-id="140fa-278">Aniversário de tempo de serviço</span><span class="sxs-lookup"><span data-stu-id="140fa-278">Seniority date</span></span>
- <span data-ttu-id="140fa-279">Conhecido como</span><span class="sxs-lookup"><span data-stu-id="140fa-279">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="140fa-280">Informações pessoais</span><span class="sxs-lookup"><span data-stu-id="140fa-280">Personal information</span></span>

- <span data-ttu-id="140fa-281">Estado civil (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-281">Marital status (required)</span></span>
- <span data-ttu-id="140fa-282">Data de nascimento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-282">Birth date (required)</span></span>
- <span data-ttu-id="140fa-283">Sexo (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-283">Gender (required)</span></span>
- <span data-ttu-id="140fa-284">Pessoa portadora de deficiências</span><span class="sxs-lookup"><span data-stu-id="140fa-284">Person with disabilities</span></span>
- <span data-ttu-id="140fa-285">Região do país de nacionalidade (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="140fa-285">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="140fa-286">Informações de endereço</span><span class="sxs-lookup"><span data-stu-id="140fa-286">Address information</span></span>

- <span data-ttu-id="140fa-287">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-287">Primary (required)</span></span>
- <span data-ttu-id="140fa-288">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-288">Country/region (required)</span></span>
- <span data-ttu-id="140fa-289">CEP (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-289">Postal code (required)</span></span>
- <span data-ttu-id="140fa-290">Número da rua (obrigatório) (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="140fa-290">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="140fa-291">Complemento do edifício (somente para o México)</span><span class="sxs-lookup"><span data-stu-id="140fa-291">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="140fa-292">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-292">City (required)</span></span>
- <span data-ttu-id="140fa-293">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-293">State (required)</span></span>
- <span data-ttu-id="140fa-294">Município (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-294">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="140fa-295">Informações de contato</span><span class="sxs-lookup"><span data-stu-id="140fa-295">Contact information</span></span> 

- <span data-ttu-id="140fa-296">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-296">Primary (required)</span></span>
- <span data-ttu-id="140fa-297">Número de contato (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-297">Contact number (required)</span></span>
- <span data-ttu-id="140fa-298">Extensão</span><span class="sxs-lookup"><span data-stu-id="140fa-298">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="140fa-299">Informações sobre folha de pagamento e códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="140fa-299">Payroll information and earning codes</span></span>

<span data-ttu-id="140fa-300">Os funcionários podem receber ganhos específicos com uma determinada frequência de pagamento e ter um método de pagamento preferencial.</span><span class="sxs-lookup"><span data-stu-id="140fa-300">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="140fa-301">Os campos a seguir são usados no Dayforce para ajudar a garantir que essas preferências e configurações sejam usadas.</span><span class="sxs-lookup"><span data-stu-id="140fa-301">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="140fa-302">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="140fa-302">Earning codes</span></span>

- <span data-ttu-id="140fa-303">Posição (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-303">Position (required)</span></span>
- <span data-ttu-id="140fa-304">Código de ganhos (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-304">Earning Code (required)</span></span>
- <span data-ttu-id="140fa-305">Frequência (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-305">Frequency (required)</span></span>
- <span data-ttu-id="140fa-306">Valor (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-306">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="140fa-307">Informações da folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="140fa-307">Payroll information</span></span>

- <span data-ttu-id="140fa-308">Método de Pagamento</span><span class="sxs-lookup"><span data-stu-id="140fa-308">Payment Method</span></span>
- <span data-ttu-id="140fa-309">Região econômica (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-309">Economic Region (required)</span></span>
- <span data-ttu-id="140fa-310">ID de Benefícios do Funcionário</span><span class="sxs-lookup"><span data-stu-id="140fa-310">Employee Benefits ID</span></span>
- <span data-ttu-id="140fa-311">Número de ID nacional (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-311">National ID Number (required)</span></span>
- <span data-ttu-id="140fa-312">Número de serviço militar</span><span class="sxs-lookup"><span data-stu-id="140fa-312">Military Service Number</span></span>
- <span data-ttu-id="140fa-313">ID de turno (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-313">Shift ID (required)</span></span>
- <span data-ttu-id="140fa-314">Número fiscal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-314">Tax Number (required)</span></span>
- <span data-ttu-id="140fa-315">ID do sindicato (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-315">Union ID (required)</span></span>
- <span data-ttu-id="140fa-316">ID do dia útil (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-316">Work Day ID (required)</span></span>
- <span data-ttu-id="140fa-317">Número de autorização de trabalho</span><span class="sxs-lookup"><span data-stu-id="140fa-317">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="140fa-318">Para o método de pagamento, o México permite **Pagamento à vista**, **Cheque** (o cheque físico da empresa) e **Pagamento Eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="140fa-318">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="140fa-319">Se nenhum método de pagamento for especificado, **Cheque** é usado por padrão.</span><span class="sxs-lookup"><span data-stu-id="140fa-319">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="140fa-320">Detalhes do emprego</span><span class="sxs-lookup"><span data-stu-id="140fa-320">Employment details</span></span>

<span data-ttu-id="140fa-321">O histórico de detalhes de emprego é usado como principal informação para derivar os status de contratação, rescisão e recontratação de um funcionário no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="140fa-321">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="140fa-322">O Dayforce suporta apenas um registro de emprego ativo de cada vez.</span><span class="sxs-lookup"><span data-stu-id="140fa-322">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="140fa-323">Data de início do emprego (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-323">Employment start date (required)</span></span>
- <span data-ttu-id="140fa-324">Data final do emprego</span><span class="sxs-lookup"><span data-stu-id="140fa-324">Employment end date</span></span>
- <span data-ttu-id="140fa-325">Data de início</span><span class="sxs-lookup"><span data-stu-id="140fa-325">Start date</span></span>
- <span data-ttu-id="140fa-326">Data inicial ajustada</span><span class="sxs-lookup"><span data-stu-id="140fa-326">Adjusted start date</span></span>
- <span data-ttu-id="140fa-327">Data de rescisão (obrigatória após a rescisão)</span><span class="sxs-lookup"><span data-stu-id="140fa-327">Termination date (required upon termination)</span></span>
- <span data-ttu-id="140fa-328">Motivo da rescisão (obrigatória após a rescisão)</span><span class="sxs-lookup"><span data-stu-id="140fa-328">Termination reason (required upon termination)</span></span>

<span data-ttu-id="140fa-329">As principais datas de um funcionário são derivadas usando-se as informações a seguir.</span><span class="sxs-lookup"><span data-stu-id="140fa-329">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="140fa-330">Talent</span><span class="sxs-lookup"><span data-stu-id="140fa-330">Talent</span></span>                | <span data-ttu-id="140fa-331">Dayforce</span><span class="sxs-lookup"><span data-stu-id="140fa-331">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="140fa-332">Data de contratação mais recente</span><span class="sxs-lookup"><span data-stu-id="140fa-332">Most recent hire date</span></span> | <span data-ttu-id="140fa-333">Início de emprego do registro histórico de emprego atual não terminado</span><span class="sxs-lookup"><span data-stu-id="140fa-333">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="140fa-334">Data da rescisão</span><span class="sxs-lookup"><span data-stu-id="140fa-334">Termination date</span></span>      | <span data-ttu-id="140fa-335">Data de rescisão do registro histórico de emprego atual não terminado</span><span class="sxs-lookup"><span data-stu-id="140fa-335">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="140fa-336">Data de início</span><span class="sxs-lookup"><span data-stu-id="140fa-336">Start date</span></span>            | <span data-ttu-id="140fa-337">Data de início ajustada, data de início ou início de emprego do registro histórico de emprego não ativo atual</span><span class="sxs-lookup"><span data-stu-id="140fa-337">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="140fa-338">Data original de contratação</span><span class="sxs-lookup"><span data-stu-id="140fa-338">Original hire date</span></span>    | <span data-ttu-id="140fa-339">Início de emprego do registro histórico de emprego mais antigo</span><span class="sxs-lookup"><span data-stu-id="140fa-339">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="140fa-340">Remuneração</span><span class="sxs-lookup"><span data-stu-id="140fa-340">Compensation</span></span>

<span data-ttu-id="140fa-341">Um plano de remuneração fixa deve estar associado à posição principal de cada funcionário durante um período de emprego.</span><span class="sxs-lookup"><span data-stu-id="140fa-341">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="140fa-342">Esse período tem início na data em que o funcionário foi contratado (ou na data de início do emprego) e continua até a rescisão.</span><span class="sxs-lookup"><span data-stu-id="140fa-342">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="140fa-343">Data de vigência (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-343">Effective Date (required)</span></span>
- <span data-ttu-id="140fa-344">Data de validade</span><span class="sxs-lookup"><span data-stu-id="140fa-344">Expiration date</span></span>
- <span data-ttu-id="140fa-345">Taxa de pagamento (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-345">Pay Rate (required)</span></span>
- <span data-ttu-id="140fa-346">Conversões de taxa de pagamento (obrigatórias)</span><span class="sxs-lookup"><span data-stu-id="140fa-346">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="140fa-347">Equivalente anual (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-347">Annual equivalent (required)</span></span>
- <span data-ttu-id="140fa-348">Equivalente por hora (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-348">Hourly equivalent (required)</span></span>

<span data-ttu-id="140fa-349">Se um funcionário por hora tiver várias posições, a remuneração fixa da posição principal é importada para o Dayforce como a taxa base/salário do nível do funcionário.</span><span class="sxs-lookup"><span data-stu-id="140fa-349">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="140fa-350">Para posições não principais, a taxa por hora é salva na posição correspondente no Dayforce.</span><span class="sxs-lookup"><span data-stu-id="140fa-350">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="140fa-351">Se um funcionário assalariado tiver várias posições, a taxa acumulada de horas e o salário anual em todas as posições ativas serão derivados e usados como a taxa base/salário do nível do funcionário.</span><span class="sxs-lookup"><span data-stu-id="140fa-351">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="140fa-352">Números de identificação</span><span class="sxs-lookup"><span data-stu-id="140fa-352">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="140fa-353">Cadastro de Pessoa Física (CPF)</span><span class="sxs-lookup"><span data-stu-id="140fa-353">Social Security identifier</span></span> 

<span data-ttu-id="140fa-354">Todos os funcionários devem ter um identificador principal.</span><span class="sxs-lookup"><span data-stu-id="140fa-354">Every employee must have one primary identifier.</span></span> <span data-ttu-id="140fa-355">Esse identificador deve ser o tipo de identificação **CPF**.</span><span class="sxs-lookup"><span data-stu-id="140fa-355">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="140fa-356">No Dayforce, ele é derivado automaticamente como o identificador de pessoa física do funcionário necessário para a contratação.</span><span class="sxs-lookup"><span data-stu-id="140fa-356">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="140fa-357">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-357">Primary (required)</span></span>
- <span data-ttu-id="140fa-358">Tipo de identificação = "CPF"</span><span class="sxs-lookup"><span data-stu-id="140fa-358">Identification Type = "SSN"</span></span>
- <span data-ttu-id="140fa-359">Data da emissão</span><span class="sxs-lookup"><span data-stu-id="140fa-359">Issued Date</span></span>
- <span data-ttu-id="140fa-360">Data de Vencimento</span><span class="sxs-lookup"><span data-stu-id="140fa-360">Expiration Date</span></span>

<span data-ttu-id="140fa-361">Os funcionários podem declarar vários números de identificação do tipo de identificação **CPF**.</span><span class="sxs-lookup"><span data-stu-id="140fa-361">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="140fa-362">No entanto, somente o registro marcado como **Principal** será integrado ao Dayforce, independentemente de o número estar ativo ou expirado.</span><span class="sxs-lookup"><span data-stu-id="140fa-362">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="140fa-363">Contas bancárias e pagamentos</span><span class="sxs-lookup"><span data-stu-id="140fa-363">Bank accounts and disbursements</span></span>

<span data-ttu-id="140fa-364">Informações de conta bancária válidas devem ser inseridas para qualquer funcionário que opte por ser pago por meio de transferências bancárias.</span><span class="sxs-lookup"><span data-stu-id="140fa-364">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="140fa-365">Talent</span><span class="sxs-lookup"><span data-stu-id="140fa-365">Talent</span></span>                         | <span data-ttu-id="140fa-366">Dayforce</span><span class="sxs-lookup"><span data-stu-id="140fa-366">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="140fa-367">Número da conta bancária (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-367">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="140fa-368">Código SWIFT (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-368">SWIFT code (required)</span></span>          | <span data-ttu-id="140fa-369">Campo **ID do banco** usado no processamento da folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="140fa-369">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="140fa-370">Número da agência (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-370">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="140fa-371">Tipo de conta bancária (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-371">Bank account type (required)</span></span>   | <span data-ttu-id="140fa-372">Campo **Tipo de conta** usado no processamento da folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="140fa-372">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="140fa-373">Os valores com suporte incluem **Movimento** e **Folha de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="140fa-373">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="140fa-374">Os funcionários que optarem por serem pagos por meio de transferências bancárias deverão fornecer um link para uma conta de pendência em uma entidade legal que tenha seu endereço principal no México e esteja associada a uma conta bancária válida de um banco mexicano.</span><span class="sxs-lookup"><span data-stu-id="140fa-374">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="140fa-375">Todas as outras contas que não são de pendência são ignoradas.</span><span class="sxs-lookup"><span data-stu-id="140fa-375">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="140fa-376">Informações de endereço</span><span class="sxs-lookup"><span data-stu-id="140fa-376">Address information</span></span>

<span data-ttu-id="140fa-377">Todos os funcionários devem ter um local principal.</span><span class="sxs-lookup"><span data-stu-id="140fa-377">Every employee must have one primary location.</span></span> <span data-ttu-id="140fa-378">No Dayforce, esse local é usado para determinar a residência principal do funcionário para fins fiscais.</span><span class="sxs-lookup"><span data-stu-id="140fa-378">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="140fa-379">Principal (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-379">Primary (required)</span></span>
- <span data-ttu-id="140fa-380">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-380">Country/region (required)</span></span>
- <span data-ttu-id="140fa-381">CEP (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-381">Zip/postal code (required)</span></span>
- <span data-ttu-id="140fa-382">Rua (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-382">Street (required)</span></span>
- <span data-ttu-id="140fa-383">Número da rua (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-383">Street Number (required)</span></span>
- <span data-ttu-id="140fa-384">Complemento do edifício</span><span class="sxs-lookup"><span data-stu-id="140fa-384">Building Complement</span></span>
- <span data-ttu-id="140fa-385">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-385">City (required)</span></span>
- <span data-ttu-id="140fa-386">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-386">State (required)</span></span>
- <span data-ttu-id="140fa-387">Município (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-387">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="140fa-388">Configurar seus dados para gerar folha de pagamento nos Estados Unidos e no Canadá</span><span class="sxs-lookup"><span data-stu-id="140fa-388">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="140fa-389">Se você está gerando pagamento para funcionários nos Estados Unidos e no Canadá, os seguintes elementos devem ser configurados:</span><span class="sxs-lookup"><span data-stu-id="140fa-389">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="140fa-390">Departamentos são necessários em posições.</span><span class="sxs-lookup"><span data-stu-id="140fa-390">Departments are required on positions.</span></span>
- <span data-ttu-id="140fa-391">Os centros de custo devem ser definidos como dimensões financeiras e ser o primeiro elemento na sequência de dimensão financeira padrão.</span><span class="sxs-lookup"><span data-stu-id="140fa-391">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="140fa-392">Você pode configurar o Talent para exigir que Posições especifique um Departamento.</span><span class="sxs-lookup"><span data-stu-id="140fa-392">You can configure Talent to require that Positions specify a Department.</span></span> <span data-ttu-id="140fa-393">Para isso, acesse **Posições Compartilhadas de Recursos Humanos > Posições > Exigir departamentos nas posições**.</span><span class="sxs-lookup"><span data-stu-id="140fa-393">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="140fa-394">Recomendamos que esta configuração seja imposta para a integração.</span><span class="sxs-lookup"><span data-stu-id="140fa-394">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="140fa-395">Tipos de trabalho</span><span class="sxs-lookup"><span data-stu-id="140fa-395">Job types</span></span>

<span data-ttu-id="140fa-396">Os tipos de trabalho são usados para agrupar trabalhos semelhantes em categorias.</span><span class="sxs-lookup"><span data-stu-id="140fa-396">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="140fa-397">Os tipos de trabalho são necessários para processar a folha de pagamento nos Estados Unidos e no Canadá.</span><span class="sxs-lookup"><span data-stu-id="140fa-397">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="140fa-398">Os exemplos de tipos de trabalho incluem horário integral e meio período ou salário e pagamento por hora.</span><span class="sxs-lookup"><span data-stu-id="140fa-398">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="140fa-399">Os tipos de trabalho são mapeados para o Dayforce como tipos de pagamento que indicam se um funcionário é pago por hora ou assalariado.</span><span class="sxs-lookup"><span data-stu-id="140fa-399">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="140fa-400">Os seguintes tipos de trabalho e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="140fa-400">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="140fa-401">Tipo de trabalho</span><span class="sxs-lookup"><span data-stu-id="140fa-401">Job type</span></span>   | <span data-ttu-id="140fa-402">descrição</span><span class="sxs-lookup"><span data-stu-id="140fa-402">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="140fa-403">Por hora</span><span class="sxs-lookup"><span data-stu-id="140fa-403">Hourly</span></span>     | <span data-ttu-id="140fa-404">Por hora</span><span class="sxs-lookup"><span data-stu-id="140fa-404">Hourly</span></span>      |
| <span data-ttu-id="140fa-405">Assalariado</span><span class="sxs-lookup"><span data-stu-id="140fa-405">Salaried</span></span>   | <span data-ttu-id="140fa-406">Assalariado</span><span class="sxs-lookup"><span data-stu-id="140fa-406">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="140fa-407">Tipos de posição</span><span class="sxs-lookup"><span data-stu-id="140fa-407">Position types</span></span> 

<span data-ttu-id="140fa-408">Você usa os tipos de posição para descrever se a posição é de tempo integral, meio período ou de outra natureza.</span><span class="sxs-lookup"><span data-stu-id="140fa-408">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="140fa-409">Os tipos de posição são mapeados para o Dayforce como classes de pagamento que indicam se um funcionário é de tempo integral ou meio período.</span><span class="sxs-lookup"><span data-stu-id="140fa-409">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="140fa-410">Os seguintes tipos de posição e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="140fa-410">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="140fa-411">Tipo de posição</span><span class="sxs-lookup"><span data-stu-id="140fa-411">Position type</span></span>   | <span data-ttu-id="140fa-412">descrição</span><span class="sxs-lookup"><span data-stu-id="140fa-412">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="140fa-413">Horário integral</span><span class="sxs-lookup"><span data-stu-id="140fa-413">Full-time</span></span>       | <span data-ttu-id="140fa-414">Funcionário de tempo integral</span><span class="sxs-lookup"><span data-stu-id="140fa-414">Full time employee</span></span> |
| <span data-ttu-id="140fa-415">Meio período</span><span class="sxs-lookup"><span data-stu-id="140fa-415">Part-time</span></span>       | <span data-ttu-id="140fa-416">Funcionário de meio período</span><span class="sxs-lookup"><span data-stu-id="140fa-416">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="140fa-417">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="140fa-417">Reason codes</span></span>

<span data-ttu-id="140fa-418">Códigos de motivo fornecem informações sobre o status de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="140fa-418">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="140fa-419">Os códigos de motivo são mapeados para o Dayforce como motivos de status que indicam o motivo das alterações na posição de um funcionário ou no status de um emprego.</span><span class="sxs-lookup"><span data-stu-id="140fa-419">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="140fa-420">Os seguintes códigos de motivo e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="140fa-420">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="140fa-421">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="140fa-421">Reason code</span></span>    | <span data-ttu-id="140fa-422">descrição</span><span class="sxs-lookup"><span data-stu-id="140fa-422">Description</span></span>      | <span data-ttu-id="140fa-423">Cenários aplicáveis</span><span class="sxs-lookup"><span data-stu-id="140fa-423">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="140fa-424">DEMISSÃO</span><span class="sxs-lookup"><span data-stu-id="140fa-424">RESIGNATION</span></span>    | <span data-ttu-id="140fa-425">Demissão</span><span class="sxs-lookup"><span data-stu-id="140fa-425">Resignation</span></span>      | <span data-ttu-id="140fa-426">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-426">Terminate worker</span></span>     |
| <span data-ttu-id="140fa-427">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="140fa-427">TERMINATION</span></span>    | <span data-ttu-id="140fa-428">Finalização</span><span class="sxs-lookup"><span data-stu-id="140fa-428">Termination</span></span>      | <span data-ttu-id="140fa-429">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-429">Terminate worker</span></span>     |
| <span data-ttu-id="140fa-430">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="140fa-430">RETIREMENT</span></span>     | <span data-ttu-id="140fa-431">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="140fa-431">Retirement</span></span>       | <span data-ttu-id="140fa-432">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-432">Terminate worker</span></span>     |
| <span data-ttu-id="140fa-433">OTHER</span><span class="sxs-lookup"><span data-stu-id="140fa-433">OTHER</span></span>          | <span data-ttu-id="140fa-434">Outros motivos</span><span class="sxs-lookup"><span data-stu-id="140fa-434">Other Reasons</span></span>    | <span data-ttu-id="140fa-435">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-435">Terminate worker</span></span>     |
| <span data-ttu-id="140fa-436">DEATH</span><span class="sxs-lookup"><span data-stu-id="140fa-436">DEATH</span></span>          | <span data-ttu-id="140fa-437">Morte</span><span class="sxs-lookup"><span data-stu-id="140fa-437">Death</span></span>            | <span data-ttu-id="140fa-438">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-438">Terminate worker</span></span>     |
| <span data-ttu-id="140fa-439">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="140fa-439">LEAVEOFABSENCE</span></span> | <span data-ttu-id="140fa-440">Licença</span><span class="sxs-lookup"><span data-stu-id="140fa-440">Leave of Absence</span></span> | <span data-ttu-id="140fa-441">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-441">Terminate worker</span></span>     |
| <span data-ttu-id="140fa-442">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="140fa-442">CONTRACTEND</span></span>    | <span data-ttu-id="140fa-443">Fim do contrato</span><span class="sxs-lookup"><span data-stu-id="140fa-443">End of Contract</span></span>  | <span data-ttu-id="140fa-444">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-444">Terminate worker</span></span>     |
| <span data-ttu-id="140fa-445">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="140fa-445">SALARYCHANGE</span></span>   | <span data-ttu-id="140fa-446">Alteração de salário</span><span class="sxs-lookup"><span data-stu-id="140fa-446">Change of Salary</span></span> | <span data-ttu-id="140fa-447">Remuneração</span><span class="sxs-lookup"><span data-stu-id="140fa-447">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="140fa-448">Estado civil</span><span class="sxs-lookup"><span data-stu-id="140fa-448">Marital status</span></span>

<span data-ttu-id="140fa-449">Os valores do estado civil são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="140fa-449">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="140fa-450">A tabela a seguir mostra como os valores do estado civil são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="140fa-450">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="140fa-451">Talent</span><span class="sxs-lookup"><span data-stu-id="140fa-451">Talent</span></span>                 | <span data-ttu-id="140fa-452">Dayforce</span><span class="sxs-lookup"><span data-stu-id="140fa-452">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="140fa-453">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="140fa-453">Married</span></span>                | <span data-ttu-id="140fa-454">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="140fa-454">Married</span></span>              |
| <span data-ttu-id="140fa-455">Única</span><span class="sxs-lookup"><span data-stu-id="140fa-455">Single</span></span>                 | <span data-ttu-id="140fa-456">Única</span><span class="sxs-lookup"><span data-stu-id="140fa-456">Single</span></span>               |
| <span data-ttu-id="140fa-457">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="140fa-457">Widowed</span></span>                | <span data-ttu-id="140fa-458">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="140fa-458">Widowed</span></span>              |
| <span data-ttu-id="140fa-459">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="140fa-459">Divorced</span></span>               | <span data-ttu-id="140fa-460">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="140fa-460">Divorced</span></span>             |
| <span data-ttu-id="140fa-461">Parceria Registrada</span><span class="sxs-lookup"><span data-stu-id="140fa-461">Registered Partnership</span></span> | <span data-ttu-id="140fa-462">Parceiro doméstico</span><span class="sxs-lookup"><span data-stu-id="140fa-462">Domestic Partnership</span></span> |
| <span data-ttu-id="140fa-463">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="140fa-463">None</span></span>                   | <span data-ttu-id="140fa-464">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="140fa-464">None</span></span>                 |
| <span data-ttu-id="140fa-465">Coabitando</span><span class="sxs-lookup"><span data-stu-id="140fa-465">Cohabiting</span></span>             | <span data-ttu-id="140fa-466">Coabitando</span><span class="sxs-lookup"><span data-stu-id="140fa-466">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="140fa-467">Sexo</span><span class="sxs-lookup"><span data-stu-id="140fa-467">Gender</span></span>

<span data-ttu-id="140fa-468">As designações de gênero são mapeadas para o Dayforce e convertidas, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="140fa-468">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="140fa-469">A tabela a seguir mostra como as designações de gênero são mapeadas para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="140fa-469">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="140fa-470">Talent</span><span class="sxs-lookup"><span data-stu-id="140fa-470">Talent</span></span>       | <span data-ttu-id="140fa-471">Dayforce</span><span class="sxs-lookup"><span data-stu-id="140fa-471">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="140fa-472">Masculino</span><span class="sxs-lookup"><span data-stu-id="140fa-472">Male</span></span>         | <span data-ttu-id="140fa-473">Masculino</span><span class="sxs-lookup"><span data-stu-id="140fa-473">Male</span></span>            |
| <span data-ttu-id="140fa-474">Feminino</span><span class="sxs-lookup"><span data-stu-id="140fa-474">Female</span></span>       | <span data-ttu-id="140fa-475">Feminino</span><span class="sxs-lookup"><span data-stu-id="140fa-475">Female</span></span>          |
| <span data-ttu-id="140fa-476">Não específico</span><span class="sxs-lookup"><span data-stu-id="140fa-476">Non-specific</span></span> | <span data-ttu-id="140fa-477">*Sem suporte*</span><span class="sxs-lookup"><span data-stu-id="140fa-477">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="140fa-478">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="140fa-478">Earning codes</span></span>

<span data-ttu-id="140fa-479">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="140fa-479">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="140fa-480">Os códigos abordam vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="140fa-480">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="140fa-481">Se uma frequência sem suporte for usada, a frequência **Cada pagamento** é usada por padrão para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="140fa-481">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="140fa-482">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="140fa-482">Supported frequencies</span></span>

- <span data-ttu-id="140fa-483">Todas</span><span class="sxs-lookup"><span data-stu-id="140fa-483">All</span></span>
- <span data-ttu-id="140fa-484">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="140fa-484">EVERYPAY</span></span>
- <span data-ttu-id="140fa-485">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="140fa-485">EACHPAYPERIOD</span></span>
- <span data-ttu-id="140fa-486">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="140fa-486">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="140fa-487">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="140fa-487">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="140fa-488">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-488">1OFMTH</span></span>
- <span data-ttu-id="140fa-489">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-489">LASTOFMTH</span></span>
- <span data-ttu-id="140fa-490">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-490">2OFMTH</span></span>
- <span data-ttu-id="140fa-491">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-491">3OFMTH</span></span>
- <span data-ttu-id="140fa-492">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-492">4OFMTH</span></span>
- <span data-ttu-id="140fa-493">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-493">5OFMTH</span></span>
- <span data-ttu-id="140fa-494">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-494">1N2OFMTH</span></span>
- <span data-ttu-id="140fa-495">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-495">3N4OFMTH</span></span>
- <span data-ttu-id="140fa-496">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-496">1N3OFMTH</span></span>
- <span data-ttu-id="140fa-497">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-497">1N4OFMTH</span></span>
- <span data-ttu-id="140fa-498">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-498">2N3OFMTH</span></span>
- <span data-ttu-id="140fa-499">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-499">2N4OFMTH</span></span>
- <span data-ttu-id="140fa-500">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-500">1N2N3OFMTH</span></span>
- <span data-ttu-id="140fa-501">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-501">1N2N4OFMTH</span></span>
- <span data-ttu-id="140fa-502">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-502">1N3N4OFMTH</span></span>
- <span data-ttu-id="140fa-503">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-503">2N3N4OFMTH</span></span>
- <span data-ttu-id="140fa-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="140fa-505">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="140fa-505">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="140fa-506">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="140fa-506">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="140fa-507">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="140fa-507">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="140fa-508">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="140fa-508">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="140fa-509">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="140fa-509">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="140fa-510">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="140fa-510">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="140fa-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="140fa-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="140fa-512">Endereços</span><span class="sxs-lookup"><span data-stu-id="140fa-512">Addresses</span></span>

<span data-ttu-id="140fa-513">A identificação de códigos específicos de país ou região, estado e município (municipalidade) exige formatos específicos que o Dayforce e os provedores no país/na região possam reconhecer.</span><span class="sxs-lookup"><span data-stu-id="140fa-513">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="140fa-514">Embora o formato das cidades seja flexível, todas as cidades devem estar associadas a um estado.</span><span class="sxs-lookup"><span data-stu-id="140fa-514">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="140fa-515">Talent</span><span class="sxs-lookup"><span data-stu-id="140fa-515">Talent</span></span>          | <span data-ttu-id="140fa-516">Dayforce</span><span class="sxs-lookup"><span data-stu-id="140fa-516">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="140fa-517">País/Região</span><span class="sxs-lookup"><span data-stu-id="140fa-517">Country/Region</span></span>  | <span data-ttu-id="140fa-518">Código do País</span><span class="sxs-lookup"><span data-stu-id="140fa-518">Country Code</span></span>          |
| <span data-ttu-id="140fa-519">CEP</span><span class="sxs-lookup"><span data-stu-id="140fa-519">Zip/Postal Code</span></span> | <span data-ttu-id="140fa-520">CEP</span><span class="sxs-lookup"><span data-stu-id="140fa-520">Postal Code</span></span>           |
| <span data-ttu-id="140fa-521">Estadual</span><span class="sxs-lookup"><span data-stu-id="140fa-521">State</span></span>           | <span data-ttu-id="140fa-522">Código de estado</span><span class="sxs-lookup"><span data-stu-id="140fa-522">State Code</span></span>            |
| <span data-ttu-id="140fa-523">Cidade</span><span class="sxs-lookup"><span data-stu-id="140fa-523">City</span></span>            | <span data-ttu-id="140fa-524">Cidade</span><span class="sxs-lookup"><span data-stu-id="140fa-524">City</span></span>                  |
| <span data-ttu-id="140fa-525">Região</span><span class="sxs-lookup"><span data-stu-id="140fa-525">County</span></span>          | <span data-ttu-id="140fa-526">Município (municipalidade)</span><span class="sxs-lookup"><span data-stu-id="140fa-526">County (Municipality)</span></span> |
| <span data-ttu-id="140fa-527">Rua</span><span class="sxs-lookup"><span data-stu-id="140fa-527">Street</span></span>          | <span data-ttu-id="140fa-528">Linha de endereço 1</span><span class="sxs-lookup"><span data-stu-id="140fa-528">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="140fa-529">Regiões fiscais</span><span class="sxs-lookup"><span data-stu-id="140fa-529">Tax regions</span></span>

<span data-ttu-id="140fa-530">Regiões fiscais são usadas para determinar os impostos apropriados a serem aplicados durante a geração da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="140fa-530">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="140fa-531">As regiões fiscais são mapeadas para o Dayforce como endereços de localização.</span><span class="sxs-lookup"><span data-stu-id="140fa-531">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="140fa-532">A região fiscal padrão deve estar associada à posição ativa do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="140fa-532">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="140fa-533">Região fiscal (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-533">Tax region (required)</span></span>
- <span data-ttu-id="140fa-534">País/região (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-534">Country/Region (required)</span></span>
- <span data-ttu-id="140fa-535">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="140fa-535">State (required)</span></span>
- <span data-ttu-id="140fa-536">Região</span><span class="sxs-lookup"><span data-stu-id="140fa-536">County</span></span> 
- <span data-ttu-id="140fa-537">Cidade (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="140fa-537">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="140fa-538">Configurar seus dados para gerar folha de pagamento no México</span><span class="sxs-lookup"><span data-stu-id="140fa-538">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="140fa-539">Se você está gerando pagamento para funcionários no México, os seguintes elementos devem ser configurados:</span><span class="sxs-lookup"><span data-stu-id="140fa-539">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="140fa-540">Departamentos são necessários em posições.</span><span class="sxs-lookup"><span data-stu-id="140fa-540">Departments are required on positions.</span></span>
- <span data-ttu-id="140fa-541">Os centros de custo devem ser definidos como dimensões financeiras e ser o primeiro elemento na sequência de dimensão financeira padrão.</span><span class="sxs-lookup"><span data-stu-id="140fa-541">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="140fa-542">Tipos de trabalho</span><span class="sxs-lookup"><span data-stu-id="140fa-542">Job types</span></span>

<span data-ttu-id="140fa-543">Os tipos de trabalho são usados para agrupar trabalhos semelhantes em categorias.</span><span class="sxs-lookup"><span data-stu-id="140fa-543">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="140fa-544">Tipos de trabalho são necessários para processar a folha de pagamento no México.</span><span class="sxs-lookup"><span data-stu-id="140fa-544">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="140fa-545">Os exemplos de tipos de trabalho incluem horário integral e meio período ou salário e pagamento por hora.</span><span class="sxs-lookup"><span data-stu-id="140fa-545">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="140fa-546">Os tipos de trabalho são mapeados para o Dayforce como tipos de pagamento que indicam se um funcionário é pago por hora ou assalariado.</span><span class="sxs-lookup"><span data-stu-id="140fa-546">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="140fa-547">Os seguintes tipos de trabalho e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="140fa-547">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="140fa-548">Tipo de trabalho</span><span class="sxs-lookup"><span data-stu-id="140fa-548">Job type</span></span>   | <span data-ttu-id="140fa-549">descrição</span><span class="sxs-lookup"><span data-stu-id="140fa-549">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="140fa-550">Por hora</span><span class="sxs-lookup"><span data-stu-id="140fa-550">Hourly</span></span>     | <span data-ttu-id="140fa-551">MX por hora</span><span class="sxs-lookup"><span data-stu-id="140fa-551">MX Hourly</span></span>   |
| <span data-ttu-id="140fa-552">Assalariado</span><span class="sxs-lookup"><span data-stu-id="140fa-552">Salaried</span></span>   | <span data-ttu-id="140fa-553">MX assalariado</span><span class="sxs-lookup"><span data-stu-id="140fa-553">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="140fa-554">Tipos de posição</span><span class="sxs-lookup"><span data-stu-id="140fa-554">Position types</span></span> 

<span data-ttu-id="140fa-555">Você usa os tipos de posição para descrever se a posição é de tempo integral, meio período ou de outra natureza.</span><span class="sxs-lookup"><span data-stu-id="140fa-555">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="140fa-556">Os tipos de posição são mapeados para o Dayforce como classes de pagamento que indicam se um funcionário é de tempo integral ou meio período.</span><span class="sxs-lookup"><span data-stu-id="140fa-556">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="140fa-557">Os seguintes tipos de posição e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="140fa-557">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="140fa-558">Tipo de posição</span><span class="sxs-lookup"><span data-stu-id="140fa-558">Position type</span></span>   | <span data-ttu-id="140fa-559">descrição</span><span class="sxs-lookup"><span data-stu-id="140fa-559">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="140fa-560">Horário integral</span><span class="sxs-lookup"><span data-stu-id="140fa-560">Full-time</span></span>       | <span data-ttu-id="140fa-561">Funcionário de tempo integral</span><span class="sxs-lookup"><span data-stu-id="140fa-561">Full time employee</span></span> |
| <span data-ttu-id="140fa-562">Meio período</span><span class="sxs-lookup"><span data-stu-id="140fa-562">Part-time</span></span>       | <span data-ttu-id="140fa-563">Funcionário de meio período</span><span class="sxs-lookup"><span data-stu-id="140fa-563">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="140fa-564">Códigos de motivos</span><span class="sxs-lookup"><span data-stu-id="140fa-564">Reason codes</span></span>

<span data-ttu-id="140fa-565">Códigos de motivo fornecem informações sobre o status de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="140fa-565">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="140fa-566">Os códigos de motivo são mapeados para o Dayforce como motivos de status que indicam o motivo das alterações na posição de um funcionário ou no status de um emprego.</span><span class="sxs-lookup"><span data-stu-id="140fa-566">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="140fa-567">Os seguintes códigos de motivo e descrições são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="140fa-567">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="140fa-568">Código de motivo</span><span class="sxs-lookup"><span data-stu-id="140fa-568">Reason code</span></span>            | <span data-ttu-id="140fa-569">descrição</span><span class="sxs-lookup"><span data-stu-id="140fa-569">Description</span></span>                    | <span data-ttu-id="140fa-570">Cenários aplicáveis</span><span class="sxs-lookup"><span data-stu-id="140fa-570">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="140fa-571">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="140fa-571">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="140fa-572">Partida antes da primeira folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="140fa-572">Departure before first payroll</span></span> | <span data-ttu-id="140fa-573">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-573">Terminate worker</span></span>     |
| <span data-ttu-id="140fa-574">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="140fa-574">RESIGNATION</span></span>            | <span data-ttu-id="140fa-575">Demissão</span><span class="sxs-lookup"><span data-stu-id="140fa-575">Resignation</span></span>                    | <span data-ttu-id="140fa-576">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-576">Terminate worker</span></span>     |
| <span data-ttu-id="140fa-577">PENSION</span><span class="sxs-lookup"><span data-stu-id="140fa-577">PENSION</span></span>                | <span data-ttu-id="140fa-578">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="140fa-578">Pension</span></span>                        | <span data-ttu-id="140fa-579">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-579">Terminate worker</span></span>     |
| <span data-ttu-id="140fa-580">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="140fa-580">TERMINATION</span></span>            | <span data-ttu-id="140fa-581">Finalização</span><span class="sxs-lookup"><span data-stu-id="140fa-581">Termination</span></span>                    | <span data-ttu-id="140fa-582">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-582">Terminate worker</span></span>     |
| <span data-ttu-id="140fa-583">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="140fa-583">RETIREMENT</span></span>             | <span data-ttu-id="140fa-584">Aposentadoria</span><span class="sxs-lookup"><span data-stu-id="140fa-584">Retirement</span></span>                     | <span data-ttu-id="140fa-585">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-585">Terminate worker</span></span>     |
| <span data-ttu-id="140fa-586">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="140fa-586">ABSENTEE</span></span>               | <span data-ttu-id="140fa-587">Absentista</span><span class="sxs-lookup"><span data-stu-id="140fa-587">Absentee</span></span>                       | <span data-ttu-id="140fa-588">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-588">Terminate worker</span></span>     |
| <span data-ttu-id="140fa-589">OTHER</span><span class="sxs-lookup"><span data-stu-id="140fa-589">OTHER</span></span>                  | <span data-ttu-id="140fa-590">Outros motivos</span><span class="sxs-lookup"><span data-stu-id="140fa-590">Other Reasons</span></span>                  | <span data-ttu-id="140fa-591">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-591">Terminate worker</span></span>     |
| <span data-ttu-id="140fa-592">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="140fa-592">CLOSURE</span></span>                | <span data-ttu-id="140fa-593">Fechamento da empresa</span><span class="sxs-lookup"><span data-stu-id="140fa-593">Business Closure</span></span>               | <span data-ttu-id="140fa-594">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-594">Terminate worker</span></span>     |
| <span data-ttu-id="140fa-595">DEATH</span><span class="sxs-lookup"><span data-stu-id="140fa-595">DEATH</span></span>                  | <span data-ttu-id="140fa-596">Morte</span><span class="sxs-lookup"><span data-stu-id="140fa-596">Death</span></span>                          | <span data-ttu-id="140fa-597">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-597">Terminate worker</span></span>     |
| <span data-ttu-id="140fa-598">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="140fa-598">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="140fa-599">Licença</span><span class="sxs-lookup"><span data-stu-id="140fa-599">Leave of Absence</span></span>               | <span data-ttu-id="140fa-600">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-600">Terminate worker</span></span>     |
| <span data-ttu-id="140fa-601">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="140fa-601">CONTRACTEND</span></span>            | <span data-ttu-id="140fa-602">Fim do contrato</span><span class="sxs-lookup"><span data-stu-id="140fa-602">End of Contract</span></span>                | <span data-ttu-id="140fa-603">Demitir trabalhador</span><span class="sxs-lookup"><span data-stu-id="140fa-603">Terminate worker</span></span>     |
| <span data-ttu-id="140fa-604">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="140fa-604">SALARYCHANGE</span></span>           | <span data-ttu-id="140fa-605">Alteração de salário</span><span class="sxs-lookup"><span data-stu-id="140fa-605">Change of Salary</span></span>               | <span data-ttu-id="140fa-606">Remuneração</span><span class="sxs-lookup"><span data-stu-id="140fa-606">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="140fa-607">Contrato de trabalho</span><span class="sxs-lookup"><span data-stu-id="140fa-607">Terms of employment</span></span>

<span data-ttu-id="140fa-608">Termos de emprego são usados para criar categorias de termos de emprego.</span><span class="sxs-lookup"><span data-stu-id="140fa-608">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="140fa-609">Os termos são mapeados para o Dayforce como valores de indicador de emprego.</span><span class="sxs-lookup"><span data-stu-id="140fa-609">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="140fa-610">Os termos de emprego e as descrições a seguir são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="140fa-610">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="140fa-611">Contrato de trabalho</span><span class="sxs-lookup"><span data-stu-id="140fa-611">Terms of employment</span></span>   | <span data-ttu-id="140fa-612">descrição</span><span class="sxs-lookup"><span data-stu-id="140fa-612">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="140fa-613">Normal</span><span class="sxs-lookup"><span data-stu-id="140fa-613">Regular</span></span>               | <span data-ttu-id="140fa-614">Normal</span><span class="sxs-lookup"><span data-stu-id="140fa-614">Regular</span></span>     |
| <span data-ttu-id="140fa-615">Direto</span><span class="sxs-lookup"><span data-stu-id="140fa-615">Direct</span></span>                | <span data-ttu-id="140fa-616">Direto</span><span class="sxs-lookup"><span data-stu-id="140fa-616">Direct</span></span>      |
| <span data-ttu-id="140fa-617">Estágio</span><span class="sxs-lookup"><span data-stu-id="140fa-617">Internship</span></span>            | <span data-ttu-id="140fa-618">Estágio</span><span class="sxs-lookup"><span data-stu-id="140fa-618">Internship</span></span>  |
| <span data-ttu-id="140fa-619">Permanente</span><span class="sxs-lookup"><span data-stu-id="140fa-619">Permanent</span></span>             | <span data-ttu-id="140fa-620">Permanente</span><span class="sxs-lookup"><span data-stu-id="140fa-620">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="140fa-621">Estado civil</span><span class="sxs-lookup"><span data-stu-id="140fa-621">Marital status</span></span>

<span data-ttu-id="140fa-622">Os valores do estado civil são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="140fa-622">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="140fa-623">A tabela a seguir mostra como os valores do estado civil são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="140fa-623">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="140fa-624">Talent</span><span class="sxs-lookup"><span data-stu-id="140fa-624">Talent</span></span>                 | <span data-ttu-id="140fa-625">Dayforce</span><span class="sxs-lookup"><span data-stu-id="140fa-625">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="140fa-626">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="140fa-626">Married</span></span>                | <span data-ttu-id="140fa-627">Casado(a)</span><span class="sxs-lookup"><span data-stu-id="140fa-627">Married</span></span>                   |
| <span data-ttu-id="140fa-628">Única</span><span class="sxs-lookup"><span data-stu-id="140fa-628">Single</span></span>                 | <span data-ttu-id="140fa-629">Única</span><span class="sxs-lookup"><span data-stu-id="140fa-629">Single</span></span>                    |
| <span data-ttu-id="140fa-630">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="140fa-630">Widowed</span></span>                | <span data-ttu-id="140fa-631">Viúvo(a)</span><span class="sxs-lookup"><span data-stu-id="140fa-631">Widowed</span></span>                   |
| <span data-ttu-id="140fa-632">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="140fa-632">Divorced</span></span>               | <span data-ttu-id="140fa-633">Divorciado(a)</span><span class="sxs-lookup"><span data-stu-id="140fa-633">Divorced</span></span>                  |
| <span data-ttu-id="140fa-634">Parceria Registrada</span><span class="sxs-lookup"><span data-stu-id="140fa-634">Registered Partnership</span></span> | <span data-ttu-id="140fa-635">Parceiro doméstico</span><span class="sxs-lookup"><span data-stu-id="140fa-635">Domestic Partnership</span></span>      |
| <span data-ttu-id="140fa-636">Nenhum(a)</span><span class="sxs-lookup"><span data-stu-id="140fa-636">None</span></span>                   | <span data-ttu-id="140fa-637">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="140fa-637">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="140fa-638">Coabitando</span><span class="sxs-lookup"><span data-stu-id="140fa-638">Cohabiting</span></span>             | <span data-ttu-id="140fa-639">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="140fa-639">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="140fa-640">Sexo</span><span class="sxs-lookup"><span data-stu-id="140fa-640">Gender</span></span>

<span data-ttu-id="140fa-641">As designações de gênero são mapeadas para o Dayforce e convertidas, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="140fa-641">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="140fa-642">A tabela a seguir mostra como as designações de gênero são mapeadas para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="140fa-642">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="140fa-643">Talent</span><span class="sxs-lookup"><span data-stu-id="140fa-643">Talent</span></span>       | <span data-ttu-id="140fa-644">Dayforce</span><span class="sxs-lookup"><span data-stu-id="140fa-644">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="140fa-645">Masculino</span><span class="sxs-lookup"><span data-stu-id="140fa-645">Male</span></span>         | <span data-ttu-id="140fa-646">Masculino</span><span class="sxs-lookup"><span data-stu-id="140fa-646">Male</span></span>                      |
| <span data-ttu-id="140fa-647">Feminino</span><span class="sxs-lookup"><span data-stu-id="140fa-647">Female</span></span>       | <span data-ttu-id="140fa-648">Feminino</span><span class="sxs-lookup"><span data-stu-id="140fa-648">Female</span></span>                    |
| <span data-ttu-id="140fa-649">Não específico</span><span class="sxs-lookup"><span data-stu-id="140fa-649">Non-specific</span></span> | <span data-ttu-id="140fa-650">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="140fa-650">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="140fa-651">Forma de pagamento</span><span class="sxs-lookup"><span data-stu-id="140fa-651">Payment method</span></span>

<span data-ttu-id="140fa-652">Os métodos de pagamento dão ao funcionário e à empresa uma maneira de descrever como os funcionários serão pagos.</span><span class="sxs-lookup"><span data-stu-id="140fa-652">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="140fa-653">Os métodos de pagamento são mapeados para o Dayforce e convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="140fa-653">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="140fa-654">A tabela a seguir mostra como os métodos de pagamento são mapeados para o Dayforce.</span><span class="sxs-lookup"><span data-stu-id="140fa-654">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="140fa-655">Talent</span><span class="sxs-lookup"><span data-stu-id="140fa-655">Talent</span></span>             | <span data-ttu-id="140fa-656">Dayforce</span><span class="sxs-lookup"><span data-stu-id="140fa-656">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="140fa-657">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="140fa-657">Cash</span></span>               | <span data-ttu-id="140fa-658">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="140fa-658">Cash</span></span>                      |
| <span data-ttu-id="140fa-659">Pagamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="140fa-659">Electronic Payment</span></span> | <span data-ttu-id="140fa-660">Transferência</span><span class="sxs-lookup"><span data-stu-id="140fa-660">Transfer</span></span>                  |
| <span data-ttu-id="140fa-661">Verificação</span><span class="sxs-lookup"><span data-stu-id="140fa-661">Check</span></span>              | <span data-ttu-id="140fa-662">Cheque</span><span class="sxs-lookup"><span data-stu-id="140fa-662">Cheque</span></span>                    |
| <span data-ttu-id="140fa-663">Boleto bancário</span><span class="sxs-lookup"><span data-stu-id="140fa-663">Bank Draft</span></span>         | <span data-ttu-id="140fa-664">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="140fa-664">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="140fa-665">Outros</span><span class="sxs-lookup"><span data-stu-id="140fa-665">Other</span></span>              | <span data-ttu-id="140fa-666">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="140fa-666">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="140fa-667">Tipo de conta bancária</span><span class="sxs-lookup"><span data-stu-id="140fa-667">Bank account type</span></span>

<span data-ttu-id="140fa-668">Os tipos de conta bancária são usados para pagamentos eletrônicos aos funcionários.</span><span class="sxs-lookup"><span data-stu-id="140fa-668">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="140fa-669">Os tipos de conta bancária são mapeados para o Dayforce como informações da conta de transferência.</span><span class="sxs-lookup"><span data-stu-id="140fa-669">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="140fa-670">Os tipos de conta bancária são convertidos, conforme apropriado, nos valores aceitos após a integração.</span><span class="sxs-lookup"><span data-stu-id="140fa-670">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="140fa-671">Talent</span><span class="sxs-lookup"><span data-stu-id="140fa-671">Talent</span></span>            | <span data-ttu-id="140fa-672">Dayforce</span><span class="sxs-lookup"><span data-stu-id="140fa-672">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="140fa-673">Conta corrente</span><span class="sxs-lookup"><span data-stu-id="140fa-673">Checking Account</span></span>  | <span data-ttu-id="140fa-674">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="140fa-674">CheckingAccount</span></span>           |
| <span data-ttu-id="140fa-675">Conta-salário</span><span class="sxs-lookup"><span data-stu-id="140fa-675">Payroll Account</span></span>   | <span data-ttu-id="140fa-676">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="140fa-676">PayrollAccount</span></span>            |
| <span data-ttu-id="140fa-677">Conta de poupança</span><span class="sxs-lookup"><span data-stu-id="140fa-677">Savings Account</span></span>   | <span data-ttu-id="140fa-678">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="140fa-678">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="140fa-679">Conta BankGirot</span><span class="sxs-lookup"><span data-stu-id="140fa-679">BankGirot account</span></span> | <span data-ttu-id="140fa-680">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="140fa-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="140fa-681">Conta PlusGirot</span><span class="sxs-lookup"><span data-stu-id="140fa-681">PlusGirot account</span></span> | <span data-ttu-id="140fa-682">*Não há suporte para o México*</span><span class="sxs-lookup"><span data-stu-id="140fa-682">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="140fa-683">Códigos de ganhos</span><span class="sxs-lookup"><span data-stu-id="140fa-683">Earning codes</span></span>

<span data-ttu-id="140fa-684">Os códigos de ganhos identificam de forma exclusiva cada tipo de ganho que os trabalhadores recebem.</span><span class="sxs-lookup"><span data-stu-id="140fa-684">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="140fa-685">Os códigos abordam vários parâmetros relacionados a ganhos, como regras contábeis, leis tributárias, requisitos de relatório e capacidade de montante bruto.</span><span class="sxs-lookup"><span data-stu-id="140fa-685">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="140fa-686">Se uma frequência sem suporte for usada, a frequência **Cada pagamento** é usada por padrão para o cálculo.</span><span class="sxs-lookup"><span data-stu-id="140fa-686">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="140fa-687">Frequências com suporte</span><span class="sxs-lookup"><span data-stu-id="140fa-687">Supported frequencies</span></span>

- <span data-ttu-id="140fa-688">Todas</span><span class="sxs-lookup"><span data-stu-id="140fa-688">All</span></span>
- <span data-ttu-id="140fa-689">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="140fa-689">EVERYPAY</span></span>
- <span data-ttu-id="140fa-690">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="140fa-690">EACHPAYPERIOD</span></span>
- <span data-ttu-id="140fa-691">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="140fa-691">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="140fa-692">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="140fa-692">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="140fa-693">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-693">1OFMTH</span></span>
- <span data-ttu-id="140fa-694">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-694">LASTOFMTH</span></span>
- <span data-ttu-id="140fa-695">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-695">2OFMTH</span></span>
- <span data-ttu-id="140fa-696">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-696">3OFMTH</span></span>
- <span data-ttu-id="140fa-697">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-697">4OFMTH</span></span>
- <span data-ttu-id="140fa-698">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-698">5OFMTH</span></span>
- <span data-ttu-id="140fa-699">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-699">1N2OFMTH</span></span>
- <span data-ttu-id="140fa-700">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-700">3N4OFMTH</span></span>
- <span data-ttu-id="140fa-701">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-701">1N3OFMTH</span></span>
- <span data-ttu-id="140fa-702">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-702">1N4OFMTH</span></span>
- <span data-ttu-id="140fa-703">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-703">2N3OFMTH</span></span>
- <span data-ttu-id="140fa-704">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-704">2N4OFMTH</span></span>
- <span data-ttu-id="140fa-705">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-705">1N2N3OFMTH</span></span>
- <span data-ttu-id="140fa-706">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-706">1N2N4OFMTH</span></span>
- <span data-ttu-id="140fa-707">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-707">1N3N4OFMTH</span></span>
- <span data-ttu-id="140fa-708">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-708">2N3N4OFMTH</span></span>
- <span data-ttu-id="140fa-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="140fa-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="140fa-710">2N3N4N5OFMth - 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="140fa-710">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="140fa-711">1OFQTR - 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="140fa-711">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="140fa-712">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="140fa-712">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="140fa-713">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="140fa-713">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="140fa-714">1OFYEAR - 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="140fa-714">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="140fa-715">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="140fa-715">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="140fa-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="140fa-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="140fa-717">Endereços</span><span class="sxs-lookup"><span data-stu-id="140fa-717">Addresses</span></span>

<span data-ttu-id="140fa-718">A identificação de códigos específicos de país ou região, estado e município (municipalidade) exige formatos específicos que o Dayforce e os provedores no país/na região possam reconhecer.</span><span class="sxs-lookup"><span data-stu-id="140fa-718">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="140fa-719">Embora o formato das cidades seja flexível, todas as cidades devem estar associadas a um estado.</span><span class="sxs-lookup"><span data-stu-id="140fa-719">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="140fa-720">Talent</span><span class="sxs-lookup"><span data-stu-id="140fa-720">Talent</span></span>              | <span data-ttu-id="140fa-721">Dayforce</span><span class="sxs-lookup"><span data-stu-id="140fa-721">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="140fa-722">País/Região</span><span class="sxs-lookup"><span data-stu-id="140fa-722">Country/Region</span></span>      | <span data-ttu-id="140fa-723">Código do País</span><span class="sxs-lookup"><span data-stu-id="140fa-723">Country Code</span></span>          |
| <span data-ttu-id="140fa-724">CEP</span><span class="sxs-lookup"><span data-stu-id="140fa-724">Zip/Postal Code</span></span>     | <span data-ttu-id="140fa-725">CEP</span><span class="sxs-lookup"><span data-stu-id="140fa-725">Postal Code</span></span>           |
| <span data-ttu-id="140fa-726">Estadual</span><span class="sxs-lookup"><span data-stu-id="140fa-726">State</span></span>               | <span data-ttu-id="140fa-727">Código de estado</span><span class="sxs-lookup"><span data-stu-id="140fa-727">State Code</span></span>            |
| <span data-ttu-id="140fa-728">Cidade</span><span class="sxs-lookup"><span data-stu-id="140fa-728">City</span></span>                | <span data-ttu-id="140fa-729">Cidade</span><span class="sxs-lookup"><span data-stu-id="140fa-729">City</span></span>                  |
| <span data-ttu-id="140fa-730">Região</span><span class="sxs-lookup"><span data-stu-id="140fa-730">County</span></span>              | <span data-ttu-id="140fa-731">Município (municipalidade)</span><span class="sxs-lookup"><span data-stu-id="140fa-731">County (Municipality)</span></span> |
| <span data-ttu-id="140fa-732">Rua</span><span class="sxs-lookup"><span data-stu-id="140fa-732">Street</span></span>              | <span data-ttu-id="140fa-733">Linha de endereço 1</span><span class="sxs-lookup"><span data-stu-id="140fa-733">Address Line 1</span></span>        |
| <span data-ttu-id="140fa-734">Número</span><span class="sxs-lookup"><span data-stu-id="140fa-734">Street Number</span></span>       | <span data-ttu-id="140fa-735">Linha de endereço 2</span><span class="sxs-lookup"><span data-stu-id="140fa-735">Address Line 2</span></span>        |
| <span data-ttu-id="140fa-736">Complemento do edifício</span><span class="sxs-lookup"><span data-stu-id="140fa-736">Building Complement</span></span> | <span data-ttu-id="140fa-737">Linha de endereço 5</span><span class="sxs-lookup"><span data-stu-id="140fa-737">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="140fa-738">Número do passaporte</span><span class="sxs-lookup"><span data-stu-id="140fa-738">Passport number</span></span>

<span data-ttu-id="140fa-739">Os funcionários podem declarar as informações do passaporte.</span><span class="sxs-lookup"><span data-stu-id="140fa-739">Employees can declare passport information.</span></span> <span data-ttu-id="140fa-740">Essas informações são do tipo de identificação **Passaporte** e estão integradas ao Dayforce como parte das informações específicas do México de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="140fa-740">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="140fa-741">Tipo de identificação = "Passaporte"</span><span class="sxs-lookup"><span data-stu-id="140fa-741">Identification Type = "Passport"</span></span>
- <span data-ttu-id="140fa-742">Data da emissão</span><span class="sxs-lookup"><span data-stu-id="140fa-742">Issued Date</span></span>
- <span data-ttu-id="140fa-743">Data de Vencimento</span><span class="sxs-lookup"><span data-stu-id="140fa-743">Expiration Date</span></span>

<span data-ttu-id="140fa-744">Os funcionários podem declarar vários números de identificação do tipo de identificação **Passaporte**.</span><span class="sxs-lookup"><span data-stu-id="140fa-744">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="140fa-745">No entanto, apenas a entrada atual do passaporte ativo é integrada ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="140fa-745">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="140fa-746">Se todas as entradas do passaporte expirarem, o passaporte emitido mais recentemente será integrado ao Dayforce.</span><span class="sxs-lookup"><span data-stu-id="140fa-746">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
