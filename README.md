1) Wersja jednorazowa (zakończy się "Completed") -> Plik loop-pod.yaml

**Tworzenie i weryfikacja:**

```bash
kubectl apply -f loop-pod.yaml
kubectl get pods
kubectl logs loop
```

**Oczekiwany rezultat:**

- Status Poda: "Completed"
- Logi:
  ```
  1 - A piece of cake !
  2 - A piece of cake !
  3 - A piece of cake !
  4 - A piece of cake !
  5 - A piece of cake !
  ```

---

2) Wersja utrzymująca stan "Running" -> Plik loop-pod-running.yaml

**Uruchomienie (najpierw usuwamy poprzedniego Poda):**

```bash
kubectl delete pod loop
kubectl apply -f loop-pod-running.yaml
kubectl get pods
kubectl describe pod loop
kubectl logs loop
```

**Oczekiwany rezultat:**

- Status Poda: "Running"
- Logi zawierają te same 5 linii, a kontener dalej działa dzięki "sleep infinity".

---

## Sprzątanie

```bash
kubectl delete pod loop --ignore-not-found
```

---
