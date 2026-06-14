cloud-vpc-compute-platform/
├── pb/                              # gRPC контракты: CreateServer, ProvisionNetwork, AttachVolume
├── internal/chassis/                # Переиспользуем наше готовое Go 1.26 шасси конфигов и OTel-метрик!
└── services/
    ├── vpc-api-gateway/             # Принимает прикладные запросы, проверяет лимиты пользователя
    ├── hypervisor-orchestrator/     # Мозг Compute Plane. Управляет пулами CPU/RAM, симулирует KVM/QEMU аллокацию
    ├── block-storage-service/       # Симулирует Ceph/EBS. Нарезает диски, вычисляет IOPS деградацию
    ├── hourly-billing-engine/       # Финтех-воркер. Списывает деньги за каждую секунду аптайма сервера (sync/atomic)
    └── vpc-network-controller/      # Настраивает Software-Defined Networking (SDN) и приватные подсети
