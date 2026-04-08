# Research Notes & AI Conversation Transcript

## 📝 Quá Trình Tìm Hiểu

### Initial Brainstorming
- **Vấn đề cần giải quyết:** Làm thế nào để quan sát khi nào AI sai?
- **Phương pháp:** Tham gia AI conversation để capture real failures
- **Insight:** Lỗi của AI không phải bug, mà là gap trong design

### Deep Dive Vào Path Analysis

#### Path 1 (Happy):
- Điều kiện: Clear request + Complete data
- AI Logic: Intent Recognition → Data Query → Formatting
- Success Rate: 95%+

#### Path 2 (Wrong Logic):
- Điều kiện: Ambiguous/Unclear request
- AI Logic: Keyword matching → Empty result → Return 0
- **Problem:** Lack of semantic understanding
- **Fix:** Add intent classifier (NLU model)

#### Path 3 (Wrong Interpretation):
- Điều kiện: Request similar to different intent
- AI Logic: Wrong intent matched → Wrong data retrieved
- **Problem:** Lack of context/confirmation
- **Fix:** Add confirmation step when confidence < threshold

#### Path 4 (Crisis):
- Điều kiện: Correct result BUT no explanation
- AI Logic: Data retrieved → Result shown → No reasoning
- **Problem:** Black box AI → User can't verify → Don't trust
- **Fix:** Add explainability layer (show why)

---

## 🤖 AI Conversation Insights

### Chat Dengan Claude:
```
Q: How would you design AI that users trust?
A: 
1. Be right (correctness)
2. Be clear (explainability)
3. Be humble (show uncertainty)
4. Be learnable (from user feedback)
```

### Key Takeaway:
> **Trust = Correctness + Transparency + Consistency**

---

## 📊 Screenshots & Evidence

### Screenshot 1: Path 1 Success
- User requests XYZ → AI returns correct breakdown ✅

### Screenshot 2: Path 2 Failure
- User uses "linh tính" → AI returns 0 ❌
- But should include data from "misc" category

### Screenshot 3: Path 4 Crisis  
- User: "Tại sao khoản này ở đây?"
- AI: Returns total (no explanation) 😕
- User: "Không hiểu, không trust" ❌

---

## 🎓 Lessons Learned

1. **NLU is hard** - Even simple synonyms are tricky
2. **Explainability matters** - Can't delegate AI without trust
3. **Users forgive mistakes if explained** - Transparency builds trust
4. **Feedback loops are essential** - AI learns from user corrections

---

## ⏰ Time Investment

- Analysis: 2 hours
- Research: 1.5 hours  
- Documentation: 1 hour
- **Total: 4.5 hours**

---

## 📌 Future Work

- [ ] Design interactive demo showing all 4 paths
- [ ] Prototype improved AI with explanations
- [ ] User test with 5-10 Moni users
- [ ] Iterate based on feedback
