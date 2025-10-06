flowchart LR
  subgraph Sede1[Equipo A - Mac]
    GC[(Gestor de Carga)]
    DEV[Actor Devolución]
    REN[Actor Renovación]
  end
  subgraph Sede2[Equipo B - VM Linux]
    PS[Proceso Solicitante]
  end

  PS -- REQ/REP tcp://IP:5555 --> GC
  GC -- PUB topic DEV tcp://IP:5556 --> DEV
  GC -- PUB topic REN tcp://IP:5556 --> REN
