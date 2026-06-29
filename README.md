# Memorium

##담당 영할
### 장비
- [`EquipmentInventoryModule.cs`]()
- [`EquipmentHandler.cs`](https://github.com/Yanghyeonyong/Memorium/blob/main/Assets/00.%20Scripts/Equipment/EquipmentHandler.cs) : 장비 자동 장착, 자동 합성, 강화 연동, 장비 UI 갱신 요청을 관리하는 장비 시스템의 진입점입니다.
- `PlayerEquipment.cs` : 현재 장착 중인 장비 테이블 데이터를 보관하고, 장착 변경 시 스탯 슬롯과 저장 데이터를 함께 갱신합니다.
- `ReinforecementEquipmentStat.cs` : 강화 수치에 따라 장비별 기본 스탯과 보너스 스탯 증가량을 계산해 캐싱합니다.
  
### 스테이지/맵
- `StageManager.cs` : 스테이지 정보 로드, 현재 스테이지 상태 전환, 킬 카운트 기반 진행도 계산, 보스 소환 조건, 클리어/실패 저장을 함께 관리합니다.
- `MapManager.cs` : 층별 맵 프리팹 그룹과 BGM을 `StageType` 기준으로 선택하고, 현재 층의 맵 조각과 위치 정보를 런타임에 구성합니다.
- `InfinityMap.cs` : 징검다리 형태의 무한 맵을 재배치하고, 목표 지점과 플레이어 이동 경로를 다음 맵 조각 기준으로 갱신합니다.
- `MonsterSpawner.cs` : 맵 조각별 소환 트리거 위치를 이동시키고, 현재 스테이지 테이블에 맞는 일반 몬스터 또는 보스를 오브젝트 풀에서 꺼내 배치합니다.
  
### 데이터 저장
- `AutoDataSaveManager.cs` : 각 시스템의 `SaveData` 객체를 수집한 뒤, 주기 저장과 앱 일시정지·종료 시 저장을 수행하며 `Dirty` 상태만 골라 저장합니다.
- `JSONService.cs` : 동기/비동기 JSON 저장, 임시 파일 작성 후 교체, 제네릭 로드/삭제를 제공하는 공용 저장 서비스입니다.
- `SaveData.cs` 계열 : 기능별 저장 데이터 구조를 분리해 각 시스템이 독립적으로 세이브/로드를 관리할 수 있도록 구성합니다.
  - `SaveAbilityStoneData.cs`
  - `SaveBingoData.cs`
  - `SaveCurrencyData.cs`
  - `SaveEquipmentData.cs`
  - `SaveGachaData.cs`
  - `SaveGemData.cs`
  - `SavePixieData.cs`
  - `SavePlayerData.cs`
  - `SaveQuestData.cs`
  - `SaveSkillData.cs`
  - `SaveStageData.cs`
