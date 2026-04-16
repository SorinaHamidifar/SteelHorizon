# ==========================================
# Project: HorizonForge
# Description:
# A repository dedicated to building strong, reliable code
# while exploring new development horizons and innovative solutions.
# ==========================================


# ---------- main.py ----------
"""
Main entry point for HorizonForge.
"""

from core.reliability import ReliabilityEngine
from core.innovation import HorizonExplorer


def run():
    print("🌅 HorizonForge Initialized")
    print("🧱 Reliable Code | 🚀 New Horizons | 💡 Innovation\n")

    reliability = ReliabilityEngine()
    explorer = HorizonExplorer()

    data = [5, 10, 15, 20]

    # Reliability demonstration
    print("🧱 Reliability Score:", reliability.stability_index(data))

    # Innovation exploration
    print("🚀 Horizon Ideas:", explorer.expand_ideas(["automation", "ai", "scalability"]))

    # Combined system check
    print("⚙️ Safe Execution:", reliability.safe_execute(lambda x: x * 2, data))


if __name__ == "__main__":
    run()


# ---------- core/reliability.py ----------
"""
Module focused on strong, reliable system behavior.
"""

import statistics


class Reliability:
    """Handles stability checks and safe execution of code."""

    def stability_index(self, values):
        """Calculate a stability score based on variance."""
        if not values:
            return 0
        variance = statistics.pvariance(values)
        return round(100 / (1 + variance), 2)

    def safe_execute(self, func, values):
        """Execute a function safely across a dataset."""
        results = []
        for v in values:
            try:
                results.append(func(v))
            except Exception:
                results.append(None)
        return results


# ---------- core/innovation.py ----------
"""
Module exploring innovative ideas and new development horizons.
"""

class HorizonExplorer:
    """Generates and expands innovative development concepts."""

    def expand_ideas(self, ideas):
        """Transform basic ideas into exploratory concepts."""
        return [f"{idea}_next_gen" for idea in ideas]

    def prototype(self, func, values):
        """Quick prototype runner for experimental features."""
        return [func(v) for v in values]


# ---------- tests/test_reliability.py ----------
"""
Tests for reliability module.
"""

from core.reliability import ReliabilityEngine


def test_stability_index():
    engine = ReliabilityEngine()
    assert engine.stability_index([10, 10, 10]) > 90


def test_safe_execute():
    engine = ReliabilityEngine()
    result = engine.safe_execute(lambda x: x + 1, [1, 2, 3])
    assert result == [2, 3, 4]


# ---------- tests/test_innovation.py ----------
"""
Tests for innovation module.
"""

from core.innovation import HorizonExplorer


def test_expand_ideas():
    explorer = HorizonExplorer()
    ideas = explorer.expand_ideas(["ai"])
    assert "ai_next_gen" in ideas
