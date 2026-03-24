import { useState, useCallback } from "react";
import { AnimatePresence } from "framer-motion";
import forestBg from "@/assets/forest-bg.jpg";
import ForestParticles from "@/components/ForestParticles";
import WelcomeScreen from "@/components/WelcomeScreen";
import QuizScreen from "@/components/QuizScreen";
import ResultScreen from "@/components/ResultScreen";
import { quizQuestions } from "@/data/quizData";
import type { Player } from "@/data/quizData";

type Phase = "welcome" | "quiz" | "result";

const RANKING_KEY = "iara-quiz-ranking";

const loadRanking = (): Player[] => {
  try {
    return JSON.parse(localStorage.getItem(RANKING_KEY) || "[]");
  } catch {
    return [];
  }
};

const saveRanking = (ranking: Player[]) => {
  localStorage.setItem(RANKING_KEY, JSON.stringify(ranking));
};

const Index = () => {
  const [phase, setPhase] = useState<Phase>("welcome");
  const [playerName, setPlayerName] = useState("");
  const [playerTurma, setPlayerTurma] = useState("");
  const [currentPlayer, setCurrentPlayer] = useState<Player | null>(null);
  const [ranking, setRanking] = useState<Player[]>(loadRanking);

  const handleStart = useCallback((name: string, turma: string) => {
    setPlayerName(name);
    setPlayerTurma(turma);
    setPhase("quiz");
  }, []);

  const handleComplete = useCallback(
    (score: number) => {
      const player: Player = {
        name: playerName,
        turma: playerTurma,
        score,
        timestamp: Date.now(),
      };
      setCurrentPlayer(player);
      const updated = [...loadRanking(), player];
      saveRanking(updated);
      setRanking(updated);
      setPhase("result");
    },
    [playerName, playerTurma]
  );

  const handleRestart = useCallback(() => {
    setPhase("welcome");
    setCurrentPlayer(null);
    setPlayerName("");
    setPlayerTurma("");
  }, []);

  return (
    <div className="relative min-h-screen overflow-hidden">
      {/* Background image */}
      <div
        className="fixed inset-0 bg-cover bg-center bg-no-repeat z-0"
        style={{ backgroundImage: `url(${forestBg})` }}
      />
      {/* Dark overlay for readability */}
      <div className="fixed inset-0 bg-background/70 z-[1]" />

      {/* Animated forest particles */}
      <ForestParticles />

      {/* Content */}
      <AnimatePresence mode="wait">
        {phase === "welcome" && (
          <WelcomeScreen key="welcome" onStart={handleStart} />
        )}
        {phase === "quiz" && (
          <QuizScreen
            key="quiz"
            questions={quizQuestions}
            onComplete={handleComplete}
          />
        )}
        {phase === "result" && currentPlayer && (
          <ResultScreen
            key="result"
            player={currentPlayer}
            ranking={ranking}
            totalQuestions={quizQuestions.length}
            onRestart={handleRestart}
          />
        )}
      </AnimatePresence>
    </div>
  );
};

export default Index;
