# Debugging Skill

Systematic approach to finding and fixing bugs.

## Debugging Methodology

### 1. Reproduce
- Get exact steps to reproduce
- Document environment/conditions
- Determine if deterministic or intermittent

### 2. Isolate
- Binary search through code
- Remove components until bug disappears
- Use logging to trace execution flow

### 3. Identify Root Cause
- Don't fix symptoms, find the cause
- Ask "why" multiple times
- Verify hypothesis with evidence

### 4. Fix
- Make minimal change to fix
- Write test that would have caught it
- Verify no regressions

## Debugging Commands

### View Logs
```bash
tail -f /var/log/app.log
```

### Check Process
```bash
ps aux | grep <process>
lsof -i :<port>
```

### Network Debugging
```bash
curl -v <url>
netstat -tlnp
```

### Git Bisect
```bash
git bisect start
git bisect bad HEAD
git bisect good <commit>
```

## Common Bug Patterns

| Pattern | Symptoms | Investigation |
|---------|----------|---------------|
| Race condition | Intermittent failures | Add logging with timestamps |
| Memory leak | Gradual slowdown | Monitor memory over time |
| Off-by-one | Edge case failures | Check loop boundaries |
| Null reference | Crashes on specific input | Trace data flow |
| State corruption | Inconsistent behavior | Check state mutations |

## Questions to Ask

- What changed recently?
- Can it be reproduced?
- What's in the logs?
- What's the smallest test case?
- Where does the data come from?
