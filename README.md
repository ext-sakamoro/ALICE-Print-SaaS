# ALICE-Print SaaS

SDF-to-G-code 3D print slicer API

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum, ALICE-Print |

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST /api/v1/slice` | SDFモデルをスライス |
| `POST /api/v1/gcode` | G-code生成 |
| `GET  /api/v1/printers` | 対応プリンター一覧 |
| `GET`  | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
