# Lessons Learned

## Enumeration Results Must Be Reviewed Carefully

The enumeration output already indicated that anonymous login was allowed.

The correct step would have been testing FTP authentication directly.

---

## Automated Tools Are Helpful but Not Always Necessary

The mirroring approach using `wget` worked, but it introduced unnecessary complexity.

Sometimes the simplest method is the best one.

---

## Methodology Matters

A structured workflow should be followed:

1. Enumeration
2. Verification
3. Access testing
4. File retrieval
5. Analysis

Following this process helps avoid unnecessary steps.

---

## Practical Takeaway

Always review service enumeration output carefully before moving to automated tools or advanced techniques.
