# Checkpoint Alpha: Arquitectura Neuro-Simbólica con Guardrails Deterministas para Agentes en Videojuegos

Repositorio oficial de artefactos experimentales del artículo **"Arquitectura Neuro-Simbólica con Guardrails Deterministas para Agentes en Videojuegos"**, desarrollado en el **Grupo de Investigación en Tecnologías Interactivas (GTI)** — Facultad de Ingeniería, Universidad Nacional de Mar del Plata (UNMdP), Argentina.

## Estructura del Repositorio

* **`parser_neuronal.py`**: Parser semántico estructurado basado en esquemas Pydantic y decodificación restringida ($T = 0.0$) sobre Qwen 2.5 7B.
* **`dominio_checkpoint.py`**: Definición del dominio de control fronterizo orbital, generación estocástica por semillas, barrera determinista de invariantes (`INV_00` a `INV_05`) y motor de reglas ECA con trazabilidad XAI.
* **`checkpoint_alpha.py`**: Integración de las tres capas de la arquitectura neuro-simbólica propuesta.
* **`baseline_llm_puro.py`**: Implementación del grupo control monolítico (LLM puro con estado completo y reglas en lenguaje natural).
* **`orquestador_ablacion.py`**: Ejecución del estudio de ablación pareado (guion adversarial de 8 turnos) y oráculo auditor independiente.
* **`ejecutar_pipeline_paper.py`**: Script maestro de ejecución experimental end-to-end.
* **`analisis_paper.py`**: Cálculo de métricas de integridad lógica (RVR), resolución efectiva, latencias (media, mediana, P95, speedup) y pruebas estadísticas (Fisher exacta bilateral y $U$ de Mann-Whitney).
* **`check_setup.py`**: Verificación de dependencias locales y disponibilidad del modelo en Ollama.
* **`resultados_ablacion_final_raw.json`**: Registros crudos de la evaluación adversarial final ($N = 15$ episodios, semillas `101..115`, 120 turnos por arquitectura).
* **`desglose_violaciones_final.csv`**: Desglose de violaciones por código de invariante (`INV_00` a `INV_05`).

## Requisitos e Instalación

1. **Python 3.10+** y entorno virtual:
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   pip install -r requirements.txt
