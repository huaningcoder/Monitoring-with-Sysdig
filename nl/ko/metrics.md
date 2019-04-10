---

copyright:
  years:  2018, 2019
lastupdated: "2019-03-06"

keywords: Sysdig, IBM Cloud, monitoring, metrics

subcollection: Sysdig

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:download: .download}
{:important: .important}
{:note: .note}

# 메트릭 관련 작업
{: #metrics}

{{site.data.keyword.Bluemix}}에서 {{site.data.keyword.mon_full_notm}} 서비스의 인스턴스를 프로비저닝하고 메트릭 소스에 대한 Sysdig 에이전트를 구성한 후에는 {{site.data.keyword.mon_full_notm}} 웹 UI를 통해 메트릭을 보고 모니터하며 관리할 수 있습니다. 메트릭을 사용하여 숫자 값을 지닌 데이터를 통계적으로 분석할 수 있습니다. 
{:shortdesc}


**메트릭은 해당 특성을 정의하기 위한 하나 이상의 레이블을 지닌 정량적 측정입니다.**

메트릭은 시계열에 의해 표시됩니다. 

시계열은 일정 기간 동안의 숫자 데이터 점의 세트입니다. 

메트릭은 두 개의 그룹으로 분류됩니다. 

* 기본 메트릭 
* 사용자 정의 메트릭


## 레이블
{: #metrics_labels}

**레이블은 메트릭의 특성을 정의합니다. **

레이블은 인프라 레이블 및 메트릭 디스크립터 레이블로 분류됩니다. 각 메트릭에는 사전 정의된 레이블 세트가 있습니다. 사용자 정의 메트릭의 경우에는 추가 레이블을 구성할 수 있습니다. 

레이블을 사용하여 메트릭의 특성을 식별하고 구분할 수 있습니다, 예를 들어, 다음을 수행할 수 있습니다.
* 인프라 오브젝트를 논리 계층 구조로 그룹화할 수 있습니다. 
* 데이터를 필터링하여 걸러낼 수 있습니다. 
* 집계된 데이터를 세그먼트로 분할할 수 있습니다. 


## 기본 메트릭 
{: #metrics_default}

**기본 메트릭은 시스템, 오케스트레이터 및 네트워크 인프라에 대해 보고합니다. **

모니터링 서비스는 자동으로 레이블을 각 메트릭에 추가합니다.


## 사용자 정의 메트릭
{: #metrics_custom}

**사용자 정의 메트릭은 모니터하는 애플리케이션 및 인프라의 유형에 따라 서로 다릅니다. JMX, Prometheus 및 StatsD 등이 일부 예입니다. **

이러한 메트릭에는 사전 정의된 레이블 세트가 있습니다. 사용자 정의 레이블을 더 추가할 수 있습니다.

모니터링 서비스는 지난 14일 동안 데이터를 보고한 모든 사용자 정의 메트릭 및 사용자 정의 레이블의 색인을 유지보수합니다. 이러한 메트릭을 사용하여 대시보드, 범위 및 경보를 구성할 수 있습니다.

모니터링 서비스가 색인 항목을 관리하는 방법에 대한 다음 정보를 고려하십시오.
*  메트릭은 모니터링 서비스 색인에서 자동으로 제거되며 다음 조건이 발생하면 누락으로 표시됩니다.
    
    * 모니터링 서비스가 14일 넘게 메트릭 또는 레이블에 대한 데이터를 수신하지 않습니다.
    
    * 메트릭 또는 레이블에 보고된 데이터가 없습니다.

* 누락된 메트릭 또는 누락된 레이블로는 새 아티팩트를 구성할 수 없습니다. 
* 누락된 메트릭 및 레이블이 현재 구성에서 제거될 때까지는 기존 아티팩트를 업데이트할 수 없습니다.
* 데이터 조회 및 차트에서 누락된 메트릭 또는 누락된 레이블을 사용할 수 있습니다. 
* 누락된 메트릭 또는 누락된 레이블이 포함된 경우, 기존 아티팩트는 영향을 받지 않습니다.
* 누락된 메트릭 또는 레이블에 대해 데이터를 수신하면 메트릭 또는 레이블이 다시 색인에 추가됩니다.


