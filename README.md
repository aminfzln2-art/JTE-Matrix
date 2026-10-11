import numpy as np

class MaterialistLanguageOS:
    def __init__(self):
        # لایه اول: هسته آنالوگ مشترک جهانی (بقا و غارنشینی)
        self.M_analog = {
            'mother': 'Biological Survival: Genetic Anchor',
            'father': 'Biological Survival: Genetic Anchor',
            'water': 'Resource: Hydration Survival',
            'cow': 'Primary Asset: Protein/Fat Resource',
            'house': 'Physical Shelter: Cave/Protection',
            'cave': 'Physical Shelter: Cave/Protection'
        }
        
        # لایه دوم: پوسته الگوریتمی ملل (کدهای شغلی اجدادی)
        self.M_algorithmic = {
            'Aryan': {
                'keywords': ['iron', 'ingot', 'anvil', 'hammer', 'chariot', 'sound', 'rhythm', 'metallurgy', 'aryan'],
                'os_type': 'Algorithmic Sonic OS',
                'description': 'Metallurgical frequency calibrating inflective grammar.'
            },
            'Altaic': {
                'keywords': ['herd', 'wool', 'sheep', 'damghan', 'fodder', 'pasture', 'hissar'],
                'os_type': 'Modular Agglutinative OS',
                'description': 'Abacus-like suffix chains for livestock inventory.'
            },
            'Semitic': {
                'keywords': ['customs', 'barter', 'token', 'grain', 'debt', 'tax', 'shamat', 'trade'],
                'os_type': 'Logistics/Transaction OS',
                'description': 'Triliteral radical codes for ledgering trade deficits.'
            },
            'Sinitic': {
                'keywords': ['silk', 'cocoon', 'fabric', 'ledger', 'grid', 'river', 'china'],
                'os_type': 'Isolating Grid OS',
                'description': 'Positional matrix for square-block fabric accounting.'
            }
        }

    def analyze_word(self, word: str):
        word_clean = word.lower().strip()
        
        # ۱. بررسی لایه اول (آنالوگ)
        if word_clean in self.M_analog:
            return {
                "Layer": "Layer 1: Analog (Bio-Survival)",
                "Classification": "Universal Human Core",
                "Function": self.M_analog[word_clean],
                "Ambiguity_Sigma": 0.0  # صد در صد پیش‌بینی‌پذیر
            }
            
        # ۲. بررسی لایه دوم (الگوریتمی - صنف شغلی)
        best_match = None
        max_score = 0
        
        for nation, data in self.M_algorithmic.items():
            # شبیه‌سازی وزن‌دهی به متغیرهای فرمول پنج‌گانه (شغل، ابزار، محل، کتیبه، ثبت)
            score = sum([1 for kw in data['keywords'] if kw in word_clean or word_clean in kw])
            if score > max_score:
                max_score = score
                best_match = nation

        if best_match:
            nation_data = self.M_algorithmic[best_match]
            # تابع هدف: بهینه‌سازی و صفر کردن انحراف معیار هویت
            ambiguity_sigma = max(0.0, 1.0 - (max_score / 2.0)) 
            
            return {
                "Layer": f"Layer 2: Algorithmic ({best_match} Branch)",
                "Classification": nation_data['os_type'],
                "Function": nation_data['description'],
                "Ambiguity_Sigma": ambiguity_sigma
            }
            
        # در صورت ناشناخته بودن کلمه برای سیستم‌های سنتی
        return {
            "Layer": "Unknown Vector",
            "Classification": "Undefined Production Node",
            "Function": "Requires further socio-economic data calibration.",
            "Ambiguity_Sigma": 1.0
        }

# --- اجرای آزمایشی مدل برای هوش مصنوعی ---
if __name__ == "__main__":
    ai_engine = MaterialistLanguageOS()
    
    # تست کلمات از لایه‌های مختلف
    test_vocabulary = ["Cow", "Aryan", "Shamat", "Wool", "Silk"]
    
    print("=== AI EXECUTION OF THE MATERIALIST LANGUAGE OS ===")
    for word in test_vocabulary:
        result = ai_engine.analyze_word(word)
        print(f"\n[Input Word]: {word}")
        print(f" -> Layer: {result['Layer']}")
        print(f" -> System Engine: {result['Classification']}")
        print(f" -> Economic Function: {result['Function']}")
        print(f" -> Identity Ambiguity (Sigma): {result['Ambiguity_Sigma']}")
JTE-Matrix
